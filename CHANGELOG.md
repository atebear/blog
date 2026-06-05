This is the **Backup site** for [**ʕ•ᴥ•ʔ Ate Bear Blog**](https://ate.bearblog.dev)

Site Information:
- Repository: [github.com/atebear/atebear](https://github.com/atebear/atebear)
- Deployment: [atebear.pages.dev](https://atebear.pages.dev)
    - Deployed on [CloudFlare Pages](https://pages.dev)
- Contact: [atebearblog@proton.me](mailto:atebearblog@proton.me)
- Theme: [Hugo-BearBlog](https://github.com/janraasch/hugo-bearblog)
    - Based on [BearBlog.dev](https://bearblog.dev)
    - Powered by [Hugo](https://gohugo.io/)

# Changelog

## Backup - 2026-06-04
#### Added
- Uploaded the 2026/05/30 version of the site

---

## Backup - 2026-06-05
- Uploaded the 2026/06/01 version of the site

## New Features Added - 2026-06-05

### Feature: Dynamic LastMod
#### Added
- **Dynamic "Last Edited" Timestamps**: 
  - Introduced `showlastmod.html` partial to auto-display "Last edited: X time ago" in the post header.
  - Introduced `lastmod.html` shortcode for manual placement within content.
  - Supports real-time updates (seconds/minutes/hours/days) via client-side JavaScript.
  - Automatically detects file-specific Git commit dates.

- **Cloudflare Pages Optimization**: 
  - Updated build command to fetch full Git history, ensuring accurate per-page modification dates: `git fetch --unshallow --prune && hugo --gc --minify`

#### Changed
- Refactored timestamp rendering to use a hybrid Hugo/JavaScript approach for live updates.
- Added `showLastMod` front matter parameter (default: `false`) to toggle visibility per page.

#### Fixed
- Resolved issue where timestamps were static and showed the build time instead of the actual last edit time.
- Fixed bug where all pages displayed the repository's latest commit date instead of individual file dates.

#### Technical Details
- Enabled `unsafe` attributes in `hugo.toml` under `[markup.goldmark.renderer]`.

### Feature: Alerts/Callouts/Admonition
#### Added
- **Native GitHub-style Alerts/Callouts**: Implemented support for Markdown blockquote alerts (e.g., `> [!NOTE]`, `> [!WARNING]`) using Hugo's Goldmark render hooks.
  - Added `layouts/_markup/render-blockquote-alert.html` to handle alert rendering.
  - Added CSS styles for `alert-note`, `alert-tip`, `alert-warning`, `alert-caution`, and `alert-important`.
  - Supports custom titles and emojis/icons via configuration in the render hook.
  - Compatible with GitHub, Obsidian, and Typora syntax.

#### Changed
- Replaced manual HTML blocks/shortcodes for callouts with native Goldmark render hooks for cleaner Markdown syntax.

#### Technical Details
- Requires Hugo v0.132.0 or later.
- Enabled `block` attributes in `hugo.toml` under `[markup.goldmark.parser.attribute]`.

.
