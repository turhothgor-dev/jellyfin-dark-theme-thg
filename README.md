# jellyfin-dark-theme-thg

A base dark theme for [Jellyfin](https://jellyfin.org/) Media Server.

## Preview

The theme applies a dark color palette with a blue accent (`#00a4dc`) across all major Jellyfin UI components, including:

- Navigation drawer and header
- Media cards and library views
- Dialogs, menus, and context menus
- Playback / OSD controls
- Detail pages and backdrops
- Forms, inputs, and buttons

## Installation

### Method 1 — Dashboard (Recommended)

1. Open your Jellyfin dashboard: **Admin → Dashboard → General**
2. Scroll to the **Custom CSS** section
3. Paste the contents of [`theme.css`](./theme.css) into the text area
4. Click **Save**

### Method 2 — Self-hosted URL

If you host this repository (or a raw copy of `theme.css`) on a web server:

1. Open your Jellyfin dashboard: **Admin → Dashboard → General**
2. Scroll to the **Custom CSS** section
3. Add the following import at the top of the field, replacing `<URL>` with the raw URL to `theme.css`:

```css
@import url("<URL>/theme.css");
```

4. Click **Save**

## Customization

All colors are defined as CSS custom properties at the top of `theme.css`. Edit the `:root` block to adjust the theme to your preference:

```css
:root {
    --accent-color: #00a4dc;          /* Primary accent / interactive color */
    --background-color: #101010;      /* Page background */
    --surface-color: #181818;         /* Cards, sidebar */
    --surface-raised-color: #202020;  /* Inputs, raised surfaces */
    --surface-highlight-color: #282828; /* Hover states */
    --text-color-primary: #e0e0e0;    /* Main text */
    --text-color-secondary: #a0a0a0;  /* Subtitles, labels */
    --text-color-muted: #606060;      /* Disabled / placeholder text */
}
```

## License

MIT
