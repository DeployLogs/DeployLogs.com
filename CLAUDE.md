# deploylogs.com

The public site for DeployLogs. The parent `CLAUDE.md` (how we work) still
applies, including branching. Product decisions, the backlog and anything
unannounced live in the private `DeployLogs/App` repo, not here.

## This repo is public

Everything committed here, including history, is visible to anyone. No keys,
no internal notes, and nothing from a work org: every example on the site is
the made-up sample deploy from `App/Sample.gs`.

## How it's built

- Plain HTML and one `styles.css`, served by GitHub Pages from `main`. No build
  step. Merging to `main` is publishing.
- **Nothing inline.** No `style=` attributes and no `<style>` blocks; the logo
  is `brand/logo.svg`, not SVG pasted into a page. Decided 18 Oct.
- **Every page carries its own copy of the top bar and footer.** Changing the
  navigation means changing every `.html` file, including `guides/`.
- Root `favicon.ico`, `favicon.svg`, `apple-touch-icon.png` and `og-image.png`
  are where browsers and link previews look for them. `brand/` holds the logo.
  Bump `?v=` when an icon changes.
- Contrast for every colour pair is measured and written at the top of
  `styles.css`. Re-measure if a colour changes.

## Voice

- Plain words, standard labels. Readers are smart and literal.
- Say what it does. Nothing defensive, nothing arguing with a doubt nobody had.
- No invented numbers. Example figures come from the sample deploy and are
  labelled as made up.
- Guides use the exact menu, tab and column names from the app. When the app
  renames something, the guides change with it.

## Before it goes live

- `support@deploylogs.com` must exist (forwarding at the registrar).
- GitHub Pages on, `CNAME` is `deploylogs.com`, DNS at the registrar, HTTPS.
- The legal notice names the maker as "salesforcegirl". Some countries require
  a legal notice to name a person or company and an address; decide before
  launch.
