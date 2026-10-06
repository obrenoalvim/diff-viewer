<div align="center">

<img src="app/icon.png" alt="Diff Viewer logo" width="120" height="120">

# Diff Viewer

**Compare two pieces of text and see exactly what changed, right in your browser.**<br>
Unified or side-by-side, by line, word or character, with HTML export. 100% client-side: nothing is uploaded.

[![Live demo](https://img.shields.io/badge/Live_demo-open-3B82F6?style=for-the-badge&logo=vercel&logoColor=white)](https://diff-viewer-olive.vercel.app)

[![CI](https://github.com/obrenoalvim/diff-viewer/actions/workflows/ci.yml/badge.svg)](https://github.com/obrenoalvim/diff-viewer/actions/workflows/ci.yml)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![GitHub stars](https://img.shields.io/github/stars/obrenoalvim/diff-viewer?style=flat&logo=github&color=3b82f6)](https://github.com/obrenoalvim/diff-viewer/stargazers)
[![PWA](https://img.shields.io/badge/PWA-offline-5A0FC8?logo=pwa&logoColor=white)](#features)

**English** · [Português](README.pt.md)

[Features](#features) · [Getting started](#getting-started) · [Usage](#usage) · [Browser support](#browser-support) · [FAQ](#faq)

</div>

---

A modern, 100% client-side web application for comparing text differences in real-time. Built with Next.js 13 (App Router), TypeScript, and Tailwind CSS, featuring unified and side-by-side diff views with multiple customization options.

## Features

### Core Functionality
- **Real-time Diff Calculation**: See differences instantly as you type or paste text
- **Dual View Modes**:
  - Unified view (Git-style single column)
  - Side-by-Side view (two column comparison)
- **Multiple Granularities**: Compare by lines, words, or characters
- **Smart Normalization**: Optional case-insensitive and whitespace-ignoring comparisons
- **Line Numbers**: Toggle line number display for easier navigation
- **Collapse Unchanged**: Automatically collapse large blocks of unchanged content

### User Experience
- **Debounced Updates**: 200ms debouncing prevents lag during typing
- **Persistent State**: All inputs and settings saved to localStorage
- **Clipboard Integration**: Quick paste buttons for both text inputs
- **Swap Function**: Instantly swap left and right content
- **Toast Notifications**: User-friendly feedback for all actions

### Export & Share
- **Copy as Text**: Export diff in unified text format
- **HTML Export**: Download fully-styled HTML file with embedded diff
- **Offline Support**: Progressive Web App (PWA) functionality

### Internationalization
- **Multi-language Support**: English and Portuguese (Brazil)
- **Persistent Language Selection**: Your language choice is remembered

## Technology Stack

- **Framework**: Next.js 13+ with App Router
- **Language**: TypeScript
- **Styling**: Tailwind CSS with dark theme
- **Diff Engine**: `diff` library for accurate comparison
- **UI Components**: Custom components with Radix UI primitives
- **Icons**: Lucide React

## Getting Started

### Prerequisites
- Node.js 18+
- npm or yarn

### Installation

1. Clone the repository:
```bash
git clone https://github.com/obrenoalvim/diff-viewer.git
cd diff-viewer
```

2. Install dependencies:
```bash
npm install
```

3. Run the development server:
```bash
npm run dev
```

4. Open [http://localhost:3000](http://localhost:3000) in your browser

### Build for Production

```bash
npm run build
npm run start
```

The application will be optimized and ready to deploy.

## Usage

1. **Enter Text**: Type or paste text into the left and right input areas
2. **Configure Options**:
   - Choose between Unified or Side-by-Side view
   - Select granularity (Lines, Words, or Characters)
   - Enable normalization options (Ignore case, Ignore whitespace)
   - Toggle line numbers and collapsed sections
3. **View Diff**: The comparison updates automatically as you type
4. **Export**: Use toolbar buttons to copy diff as text or export as HTML

### Keyboard Shortcuts
- Use Tab key to navigate between inputs
- Paste directly into inputs with Ctrl+V (Cmd+V on Mac)

### Diff Computation
The application uses the industry-standard `diff` library to compute differences between texts. It supports:
- Line-by-line comparison (default)
- Word-by-word comparison
- Character-by-character comparison

### Normalization Options
- **Ignore Case**: Treats uppercase and lowercase letters as identical
- **Ignore Whitespace**: Normalizes multiple spaces and trims lines before comparison

### Visual Indicators
- **Green background**: Added content
- **Red background**: Removed content
- **Gray/neutral**: Unchanged content
- **Border accent**: Color-coded left border for quick scanning

### Export Formats
- **Text**: Unified diff format with +/- prefixes
- **HTML**: Self-contained HTML file with inline styles, perfect for sharing or archiving

## Performance Considerations

- **Debouncing**: 200ms delay prevents excessive recalculations during typing
- **Memoization**: React hooks optimize re-renders
- **Lazy Calculation**: Diff only computed when inputs or options change
- **Efficient Rendering**: Virtual DOM minimizes actual DOM updates

### Known Limitations
- Very large texts (>100,000 lines) may impact performance
- Side-by-Side view automatically switches to Unified on mobile devices
- Browser clipboard API requires HTTPS in production (or localhost in development)

## Browser Support

- Chrome/Edge 90+
- Firefox 88+
- Safari 14+
- Mobile browsers (iOS Safari, Chrome Android)

PWA features require modern browser support for Service Workers.

## Contributing

Contributions are welcome! Please feel free to submit issues or pull requests.

## Acknowledgments

- Built with [Next.js](https://nextjs.org/)
- Diff calculation by [jsdiff](https://github.com/kpdecker/jsdiff)
- Icons from [Lucide](https://lucide.dev/)
- UI components inspired by [shadcn/ui](https://ui.shadcn.com/)

---

## FAQ

**Is my text sent anywhere?**
No. The comparison runs 100% in your browser, and there is no backend.

**Can I compare by word or by character?**
Yes. Pick Lines, Words or Characters, and optionally ignore case and whitespace.

**Does it work offline?**
Yes. It is a Progressive Web App, and it needs a browser with Service Worker support.

**How do I share a diff?**
Copy it as unified text, or export a self-contained HTML file with inline styles.

**Why does the side-by-side view switch to unified on my phone?**
It switches automatically on mobile devices to keep the columns readable.

## More web tools by the same author

- [**pdf-metadata-editor**](https://github.com/obrenoalvim/pdf-metadata-editor): edit a PDF's title, author and other details in your browser.
- [**custom-cpf**](https://github.com/obrenoalvim/custom-cpf): generate and validate Brazilian CPF numbers in the browser.
- [**status-hub**](https://github.com/obrenoalvim/status-hub): one grid for every status page you check.

## License

[MIT](LICENSE)

---

<div align="center">

If Diff Viewer saved you a trip to a diff tool, a ⭐ helps other people find it.

<sub>**Topics:** diff · text-diff · diff-viewer · text-comparison · jsdiff · client-side · pwa · nextjs · react · typescript · developer-tools</sub>

</div>
