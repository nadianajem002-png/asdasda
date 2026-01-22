# CLAUDE.md - AI Assistant Guide

## What This Is

Single-page web app: **GI Disorders Study Guide** for BIOL 253 at Camosun College (Winter 2026).

**Purpose**: Interactive study resource covering Chapters 36-38 on gastrointestinal disorders.

## Files

```
/
├── index.html    # The entire app (766 lines)
└── CLAUDE.md     # This guide
```

**index.html** = Everything in one file:
- HTML content
- CSS styles (lines 7-44)
- JavaScript (lines 741-763)
- No external dependencies
- Works offline

## Tech Stack

- Pure HTML5, CSS3, vanilla JavaScript
- No frameworks, no build tools, no npm
- Self-contained single file

## App Structure

**3 Tabs**:
1. **All Disorders** (lines 62-335): Searchable grid of disorder cards
2. **Comparisons** (lines 337-422): Side-by-side tables (Crohn's vs UC, Hep A/B/C, etc.)
3. **Quick Reference** (lines 424-737): Study tips, stats, mechanisms

**JavaScript** (lines 741-763):
- `switchTab()` - handles tab switching
- `filterAll()` - real-time search filter

## Content Overview

**~35 disorders organized by location**: Esophagus, Stomach, Intestines, Liver, Gallbladder, Pancreas, etc.

## Key CSS Classes

- `.disorder-card` - disorder cards with hover effects
- `.location-badge` - anatomical location tags
- `.comparison-table` - comparison tables
- `.key-point`, `.warning-box`, `.info-box`, `.success-box` - colored info blocks
- `.searchable` - cards that can be filtered by search

**Colors**: Purple gradient theme (`#667eea` → `#764ba2`), colored boxes for different info types

## How to Make Changes

### Add a Disorder Card

Add in `<div id="allDisordersGrid">` (line 66+):
```html
<div class="disorder-card searchable" data-name="keywords here">
    <h3>Disorder Name</h3>
    <p>Brief description (1-2 sentences)</p>
    <span class="location-badge">📍 Location</span>
</div>
```

### Add a Comparison Table

Add in `<div id="compare">`:
```html
<table class="comparison-table">
    <tr><th>Feature</th><th>Condition A</th><th>Condition B</th></tr>
    <tr><td><strong>Attribute</strong></td><td>Value A</td><td>Value B</td></tr>
</table>
```

### Add Content Blocks

Use: `.key-point` (tips), `.warning-box` (complications), `.info-box` (general), `.success-box` (treatments)

### Testing

Open `index.html` in browser. Check:
- Tabs switch
- Search works
- Styling looks right
- No console errors

## Rules for AI Assistants

### Content Rules

- Keep medical info accurate
- Descriptions: 1-2 sentences max
- Use standard medical abbreviations
- Maintain consistent style

### Code Rules

- Keep everything in one HTML file
- Use vanilla JavaScript only (no frameworks)
- 4-space indentation
- Follow existing color scheme
- Don't add external dependencies

### DO ✅

- Keep single-file architecture
- Maintain visual consistency
- Test search after changes
- Preserve mobile responsiveness

### DON'T ❌

- Add external libraries/frameworks
- Create separate CSS/JS files
- Introduce build tools
- Remove content without permission

## Git Workflow

**Branches**: Use `claude/` prefix for feature branches

**Commit Format**:
```
<type>: <description>
```

Types: `feat`, `fix`, `docs`, `style`, `content`

**Before Committing**:
- Test in browser
- Check search works
- Verify all tabs function
- No console errors

## Troubleshooting

**Search not working?**
- Check cards have `class="disorder-card searchable"`
- Check `data-name` attributes exist
- Verify `filterAll()` function (line 749)

**Tabs not switching?**
- Check `switchTab()` function (line 742)
- Verify `onclick="switchTab('tab-id')"`
- Check CSS `.tab-content.active { display: block; }`

**Styling broken?**
- Verify `<style>` block intact (lines 7-44)
- Check for unclosed tags
- Validate class names match CSS

## Course Info

- **Course**: BIOL 253, Camosun College, Winter 2026
- **Chapters**: 36, 37, 38 (GI pathophysiology)

## Quick Reference for AI

**Add disorder**: Copy existing card in `allDisordersGrid`, update content, test search

**Update styling**: Edit CSS in `<style>` block (lines 7-44), maintain existing patterns

**Key principle**: This is a student study resource - accuracy and clarity are critical
