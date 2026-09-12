# TODO Improvements

### Add a test framework and unit tests for lib/diff.ts
- **Category:** Test
- **What:** No test runner exists in the project (no vitest/jest, no `test` script, CI doesn't run tests). `lib/diff.ts` is pure, easily-testable logic (`computeDiff`, `diffToText`, `diffToHTML`, `normalizeText`) that ships to every user with zero coverage today — the line-number regression fixed in this pass would have been caught immediately by a basic test.
- **Where:** lib/diff.ts; new test setup; .github/workflows/ci.yml (to run tests)
- **Why:** Deliberately not added in this pass — introducing a new dependency (vitest/jest) and a CI change is outside the "no new dependencies / no restructuring" scope of this pass.
- **Risk:** Low risk, but touches package.json, CI config, and repo structure.
- **Effort:** Low

### Localize the textarea placeholder copy
- **What:** `components/TextInputs.tsx` hardcodes `placeholder="Enter or paste text here..."` in English on both textareas, even though the app is fully bilingual (en/pt) via `lib/i18n.ts` and `i18n/*.json`. Portuguese users see English placeholder text.
- **Where:** components/TextInputs.tsx:79, components/TextInputs.tsx:113; i18n/en.json, i18n/pt.json
- **Why:** Not fixed directly — adding new user-facing copy should go through a proper text-writing pass rather than being written ad hoc as part of a bug-fix/cleanup pass.
- **Category:** UI-UX
- **Risk:** Low
- **Effort:** Low

### Toast auto-dismiss timer doesn't reset on rapid consecutive toasts
- **Category:** UI-UX
- **What:** `app/page.tsx` renders a single `<Toast>` (no `key`) driven by `toastMessage` state. `components/Toast.tsx`'s dismiss timer only depends on `onClose` (stable), not on `message`, so if a second toast fires while the first is still showing, the displayed text updates but the 3s countdown does not restart — the new message can disappear sooner than 3s after it appeared.
- **Where:** components/Toast.tsx:12-18, app/page.tsx:118
- **Why:** Minor UX edge case, not a functional bug; fixing it (e.g. keying Toast by message, or adding `message` to the effect deps) is a small behavior change better left as a deliberate UX call.
- **Risk:** Low
- **Effort:** Low
