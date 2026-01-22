# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

A single-file flashcard editor for creating and printing flashcards. The entire application is contained in `flashcard-editor.html` - a self-contained HTML file with embedded CSS and JavaScript that runs entirely in the browser with no server required.

## Architecture

- **Single file app**: All code (HTML structure, CSS styles, JavaScript logic) lives in `flashcard-editor.html`
- **No build system**: Open the HTML file directly in a browser to use
- **State management**: Global `state` object holds all application state (card dimensions, fields, data, UI state)
- **LocalStorage**: Templates are saved to browser localStorage, also supports JSON file export/import

## Key Components (in flashcard-editor.html)

- **Settings Panel** (lines ~730-761): Card dimensions and background colors
- **Toolbar** (lines ~764-820): Field styling controls (font, size, color, dimensions)
- **Card Editors** (lines ~823-845): Draggable field placement on front/back card canvases
- **Data Table** (lines ~848-870): CSV/TSV import, data entry for card content
- **Print System** (lines ~1669-1869): Duplex and manual double-sided printing with proper mirroring

## State Structure

```javascript
state = {
  cardWidth, cardHeight,           // Card dimensions in px
  frontBgColor, backBgColor,       // Background colors
  frontBgTransparent, backBgTransparent,
  fields: [],                       // Field definitions with position, style
  data: [],                         // Row data for cards
  selectedField, activeCard,
  nextFieldId, showPreview
}
```

## Development

No commands needed - just open `flashcard-editor.html` in a browser. For development, use browser DevTools.
