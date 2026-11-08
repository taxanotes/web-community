# Taxanotes community

The theme of [taxanotes.org](https://taxanotes.org), the Taxanotes community
site. It is derived from the `customsolent` theme of The Solent Metropolitan
(same author): the expanding main menu and its accessibility work are kept,
everything specific to that site (its content types, paragraphs, colours,
fonts, logos and images) is dropped, and the Taxanotes mark, wordmark and
palette are added. No base theme: the markup is core's module templates with
this theme's overrides.

| Part | Where |
|---|---|
| the header band: the Taxanotes mark (inline SVG, `currentColor`) and the wordmark "taxanotes" in Cabin, both a link home | `templates/block/block--system-branding-block.html.twig`, `css/content.css` (`.txn-brand`) |
| the main menu bar; each section opens a drawer under the bar (desktop, 800px and up) or an accordion row (phones); a section whose parent has no page of its own (`route:<nolink>`) leads its panel with a heading, one with a page leads it with a link; the Search item is appended by the template when the Search module is on and opens the search form placed in the `search` region | `templates/navigation/menu--main.html.twig`, `js/taxanotes_community.js`, `css/menu-common.css`, `css/menu-desktop.css`, `css/menu-mobile.css` |
| the current section and page marked in the menu (bold, bottom line on desktop; left border on phones; the page in the accent colour) | `js/menu-state.js` |
| keyboard focus (orange marker, `:focus-visible` only), Escape closes panels, the phone menu's focus management | `css/menu-focus.css`, `js/taxanotes_community.js` |
| without JavaScript: a `<details>` menu on phones, hover/focus-within drawers on desktop, a plain link to the search page | `templates/navigation/menu--main.html.twig`, `css/menu-common.css` |
| the content column, account links, breadcrumb, messages, tabs, forms, tables (the forum), comments, the footer | `css/content.css`, `templates/layout/page.html.twig` |
| Drupal's bare pages (log in, register, reset password, 404, 403) given a heading, an intro and a box | `taxanotes_community.theme` (`_taxanotes_community_system_page()`), `css/system-pages.css` |
| the Cabin typeface (SIL Open Font License 1.1, `fonts/Cabin/OFL.txt`), variable weight 400–700, one file per script subset, named by the `--font-family` token | `css/fonts.css`, `fonts/Cabin/` |
| the colours as tokens: `--brand` (header, footer, menu bar), `--brand-light` (the mark's green), `--accent` (current page, link underlines), `--hover-tint` | `css/elements.css` |
| the favicon set (ICO, SVG, PNG, Apple touch icon), all the mark | `favicon.ico`, `favicon.svg`, `images/`, `taxanotes_community_page_attachments_alter()` |

The mark's source and generator are in the web-explorer repository
(`docs/planning/drafts/logo/`, not published); the final files are copied here.

Regions follow Olivero's names where the role is the same, so switching the
default theme from Olivero carried its blocks over; the blocks are in
`config/sync/block.block.taxanotes_community_*.yml`.
