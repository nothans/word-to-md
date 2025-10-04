# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a single-page web application that converts Microsoft Word document content to Markdown. The entire application is contained in `index.html` with no build process, dependencies, or server required.

## Running the Application

Simply open `index.html` in a web browser. No build, install, or server commands needed.

## Architecture

**Single-file design**: All HTML, CSS, and JavaScript are in `index.html` (~700 lines total)

**Key processing pipeline** (in index.html:504-598):
1. `cleanWordHTML()` - Strips Word-specific markup (mso- classes, inline styles, XML tags, o:p tags)
2. `turndownService.turndown()` - Converts cleaned HTML to Markdown via Turndown.js
3. `cleanBulletPoints()` - Post-processes to handle various bullet characters (•, ●, ○, –, etc.)
4. `updatePreview()` - Renders Markdown as HTML via Marked.js

**Paste event handling** (index.html:659-676):
- Intercepts paste event with `e.preventDefault()`
- Extracts HTML from clipboard via `clipboardData.getData('text/html')`
- This preserves Word's formatting as HTML instead of plain text

**Tab switching** (index.html:600-617):
- Two views: raw Markdown textarea and rendered HTML preview
- Uses absolute positioning with opacity transitions
- Both views exist in DOM simultaneously; visibility toggled via `.active` class

## External Dependencies (CDN)

- **Turndown.js** - HTML to Markdown conversion
- **Marked.js** - Markdown to HTML rendering (for preview)
- **Material Icons** - Footer icons

## Styling Notes

The app uses a purple gradient theme (`#667eea` to `#764ba2`) matching the NotHans brand. Footer follows the if.nothans.com pattern: icons + text + version + link.

## Version

Current version: v1.0.0 (hardcoded in footer)
