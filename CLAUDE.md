# deploylogs.com

The public site for DeployLogs. The parent `CLAUDE.md` (how we work) still
applies, including branching. Product decisions, the backlog and anything
unannounced live in the private `DeployLogs/App` repo, not here.

## This repo is public

Everything committed here, including history, is visible to anyone. No keys,
no internal notes, and nothing from a work org: every example on the site is
the made-up sample deploy from `App/Sample.gs`.

## How it's built

- Plain HTML and one `styles.css`. Merging to `main` is publishing:
  `.github/workflows/pages.yml` copies **only the site's files** into the
  published bundle and deploys it with GitHub Actions. Decided 19 Oct, after
  the built-in Jekyll builder published this file as /CLAUDE.html and stalled
  during a GitHub incident. **A new kind of file (a new folder, a font) must
  be added to the workflow's copy list**, or it will not appear on the site.
- **Nothing inline.** No `style=` attributes and no `<style>` blocks; the logo
  is `brand/logo.svg`, not SVG pasted into a page. Decided 18 Oct.
- **Every page carries its own copy of the top bar and footer.** Changing the
  navigation means changing every `.html` file, including `guides/`.
- Root `favicon.ico`, `favicon.svg`, `apple-touch-icon.png` and `og-image.png`
  are where browsers and link previews look for them. `brand/` holds the logo.
  Bump `?v=` when an icon changes.
- Contrast for every colour pair is measured and written at the top of
  `styles.css`. Re-measure if a colour changes.

## Examples look like the sheet

The tables on `examples.html` are drawn to match the sheet DeployLogs builds:
its headings, column letters and row numbers, number formats, header colours
and whole-cell fills (`.gs` in `styles.css`, taken from `Main.gs`), and the
sample deploy's exact values. Anything made up to show a state the sample
does not have is labelled under the table. Decided 18 Oct: Saasy Logs' site
once looked better than its sheet and had to be trued up, because that reads
as false advertising. When the app's columns, colours or sample change, the
examples change with them.

## No cookies, so no cookie banner

The site sets no cookies and loads no fonts, embeds or widgets from another
company (checked 18 Oct, including the live response headers). That is why it
needs no consent banner. Adding web fonts from a service, an embed or a chat
widget changes that: decide it deliberately, and update the privacy policy at
the same time.

Decided 24 Nov: visits are counted with GoatCounter (no cookies, no personal
data, Country and Region turned off), so tagged links (`utm_campaign`) show
which posts bring people here. It is the site's only script.

- `count.js` at the root is GoatCounter's own script (ISC licence), copied so
  the page runs a pinned copy; its count goes to `deploylogs.goatcounter.com`.
  To update it, replace the file from `https://gc.zgo.at/count.js`, read the
  diff, and bump `?v=` on every page.
- Every page gets the script line before `</body>`. A new page without it
  simply isn't counted.
- The privacy page's "This website" section says what is counted. Keep it in
  step with the GoatCounter site settings.

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
