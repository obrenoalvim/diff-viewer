# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

## [Unreleased]

### Fixed
- Line numbers were never displayed in the diff view or HTML export because the app called `computeDiff`, which never populated `hunk.lineNumber` (only the unused `computeLineDiff` did). Line-number tracking is now built into `computeDiff` itself.
- `diffToText` dropped legitimate blank lines in the middle of a hunk when the hunk's value didn't end with a newline.
