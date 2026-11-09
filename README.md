# WLVArch.AI website

Source for the WLVArch.AI student club site. It is built with Jekyll and hosted on GitHub Pages. Contributors should read `contribute.md` (the **Contribute** page on the live site).

## Structure

```
_config.yml          Site settings, club meeting details, navigation
index.html           Homepage
sessions.md          Sessions index (lists _posts)
workflows.md         Workflows index (lists _workflows)
showcase.md          Showcase index (lists _showcase)
tools.md             Tools register (reads _data/tools.yml)
ethics.md            Ethics & Practice, including posting rules
reading.md           Research & Reading list
contribute.md        Contributor guide

_posts/              Session write-ups: YYYY-MM-DD-short-title.md
_workflows/          Workflow write-ups
_showcase/           Showcase entries
_data/tools.yml      Tools register entries
_templates/          Copy-from templates (not published)
_layouts/            Page templates (default, page, post)
_includes/           Header, footer, post list
assets/css/main.css  Styles; colour tokens at the top
assets/images/       Images, filed by year and post
.github/             Pull request checklist
```

## One-time setup (staff)

1. Create a GitHub organisation called `wlvarch-ai`. Add at least two staff as owners.
2. Create a public repository named `wlvarch-ai.github.io` in that organisation and upload these files. With that name the site is served at `https://wlvarch-ai.github.io`. If you use a different repository name, set `baseurl` in `_config.yml` to `/repository-name`.
3. In **Settings → Pages**, set the source to **Deploy from a branch**, branch `main`, folder `/ (root)`.
4. In **Settings → Branches**, add a protection rule for `main` that requires one approving review before merging. This makes the editorial review step mandatory.
5. Create an `editors` team for the student editorial group and give it write access.
6. Fill in `club:` in `_config.yml` (meeting day, time, room, optional contact email).

## Decisions still open

- Content licence: choose one (for example, CC BY 4.0 for text) and add a `LICENSE` file, so contributors know how their work may be reused.
- Consent: agree how consent for names and images is recorded.

## Design

The layout follows the STEAM Academy 2026 site. The colours are tokens at the top of `assets/css/main.css`: UoW navy (`--navy`), with the club poster's yellow (`--yellow`) and magenta (`--magenta`). The University and WLV Architecture logos in `assets/images/` were taken from the STEAM site. The club logo (`wlvarch-ai-logo.png`, plus `favicon.png`) is cut from the original artwork to a transparent circle. Headings use Barlow Condensed and body text uses Roboto, both from Google Fonts.

## Local preview

```bash
bundle install
bundle exec jekyll serve
```
