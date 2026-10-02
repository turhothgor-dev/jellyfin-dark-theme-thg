# Merge Theme CSS Skill

## Purpose

Merge all individual CSS source files into a single `theme.css` file, you should replace all existing contenct inside theme.css, preserving the correct section order and ensuring the theme header is always at the top.

## Required Header

The following header block MUST be the very first content in `theme.css` (before any CSS rules):

```css
/* =========================================================
Jellyfin Dark Theme THG
Version: 1.0.0
Author:  turhothgor-dev
License: MIT
Use: @import url(https://cdn.jsdelivr.net/gh/turhothgor-dev/jellyfin-dark-theme-thg@main/theme.css);
========================================================= */
```

## Source Files

The following CSS files in the project root are the sources to merge:

| File | Contains Sections |
|------|-------------------|
| `variables.css` | 1. COLOR PALETTE & VARIABLES |
| `main.css` | 2. GLOBAL BACKGROUNDS & TEXT, 3. BACKDROP ANIMATIONS, 4. BUTTONS & CONTROLS, 5. TOP HEADER & NAVIGATION & MENU |
| `cards.css` | 6. MEDIA CARDS, 7. CARD INDICATORS, MEDIA INFO AND RATINGS |
| `itemDetails.css` | 8. ITEM DETAILS |
| `login.css` | 9. LOGIN SCREEN |
| `scrollBars.css` | 10. SCROLLBARS |
| `modals.css` | 11. MODALS & DIALOGS, 12. TOASTS / NOTIFICATIONS, 13. CONTEXT / OPTIONS MENU |
| `player.css` | 14. PLAYER OVERLAY |

## Correct Section Order

The merged `theme.css` must contain sections in this exact order:

1. **COLOR PALETTE & VARIABLES** (from `variables.css`)
2. **GLOBAL BACKGROUNDS & TEXT** (from `main.css`)
3. **BACKDROP ANIMATIONS** (from `main.css`)
4. **BUTTONS & CONTROLS** (from `main.css`)
5. **TOP HEADER & NAVIGATION & MENU** (from `main.css`)
6. **MEDIA CARDS** (from `cards.css`)
7. **CARD INDICATORS** (from `cards.css`)
8. **MEDIA INFO AND RATINGS** (from `cards.css`)
9. **ITEM DETAILS** (from `itemDetails.css`)
10. **LOGIN SCREEN** (from `login.css`)
11. **SCROLLBARS** (from `scrollBars.css`)
12. **MODALS & DIALOGS** (from `modals.css`)
13. **TOASTS / NOTIFICATIONS** (from `modals.css`)
14. **CONTEXT / OPTIONS MENU** (from `modals.css`)
15. **PLAYER OVERLAY** (from `player.css`)

## Merge Instructions

1. **Start with the header block** — copy the required header exactly as shown above.

2. **Include the base banner** — After the header, include the banner comment from `main.css`:
   ```css
   /* ==========================================================================
      CUSTOM JELLYFIN THEME - BASE
      ========================================================================== */
   ```

3. **Merge each source file in order** — For each file listed in the "Source Files" table (in the order shown), copy its CSS content into `theme.css`. Preserve all section comment headers (the `/* --- N. SECTION NAME --- */` blocks) exactly as they appear in the source files.

4. **Preserve section comments** — Each section's comment header (e.g. `/* --------------------------------------------------------------------------\n   1. COLOR PALETTE & VARIABLES\n   ... */`) must be kept intact. Do not renumber or rename sections.

5. **Do not duplicate content** — If a rule or selector appears in multiple source files, include it only once (from the first file in the merge order that contains it).

6. **Do not modify CSS rules** — Copy rules verbatim. Do not reformat, reorder properties within rules, or change values.

7. **Separate sections with a blank line** — Ensure there is at least one blank line between sections for readability.

8. **Do NOT include the header block from individual files** — The theme header at the top of `theme.css` replaces any per-file headers. Only the section-level comments are preserved.

## Validation Checklist

After merging, verify:

- [ ] The file starts with the exact header block (Jellyfin Dark Theme THG / Version / Author / License)
- [ ] All 15 sections are present in the correct order
- [ ] No CSS rules are missing compared to the source files
- [ ] No duplicate selectors/rules exist
- [ ] All section comment headers are preserved
- [ ] The file is valid CSS (no syntax errors from concatenation)

## Commnad in Windows
cd G:\desarrollo\jellyfin-server\jellyfin-dark-theme-thg; $ErrorActionPreference = 'Stop'; $header = "/* =========================================================`nJellyfin Dark Theme THG`nVersion: 1.0.0`nAuthor:  turhothgor-dev`nLicense: MIT`nUse: @import url(https://cdn.jsdelivr.net/gh/turhothgor-dev/jellyfin-dark-theme-thg@main/theme.css);`n========================================================= */`n"; $content = $header + (Get-Content variables.css -Raw) + "`n`n" + (Get-Content main.css -Raw) + "`n`n" + (Get-Content cards.css -Raw) + "`n`n" + (Get-Content itemDetails.css -Raw) + "`n`n" + (Get-Content login.css -Raw) + "`n`n" + (Get-Content scrollBars.css -Raw) + "`n`n" + (Get-Content modals.css -Raw) + "`n`n" + (Get-Content player.css -Raw); Set-Content -Path theme.css -Value $content -Encoding UTF8 -NoNewline; Write-Output "Done. Lines:"; (Get-Content theme.css).Count

## Command for linux
cd G:\desarrollo\jellyfin-server\jellyfin-dark-theme-thg && $header = @"
/* =========================================================
Jellyfin Dark Theme THG
Version: 1.0.0
Author:  turhothgor-dev
License: MIT
Use: @import url(https://cdn.jsdelivr.net/gh/turhothgor-dev/jellyfin-dark-theme-thg@main/theme.css);
========================================================= */
"@; $content = $header + "`n" + (Get-Content variables.css -Raw) + "`n`n" + (Get-Content main.css -Raw) + "`n`n" + (Get-Content cards.css -Raw) + "`n`n" + (Get-Content itemDetails.css -Raw) + "`n`n" + (Get-Content login.css -Raw) + "`n`n" + (Get-Content scrollBars.css -Raw) + "`n`n" + (Get-Content player.css -Raw) + "`n`n" + (Get-Content modals.css -Raw); Set-Content -Path theme.css -Value $content -Encoding UTF8
