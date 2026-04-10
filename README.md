# Personal academic site

A Jekyll site designed to start as a personal page and grow into a research
group site without throwing anything away. Built for GitHub Pages — no
build step you need to maintain yourself.

## Quick start

1. Create a new repo on GitHub named `your-handle.github.io`.
2. Drop the contents of this folder into it and push.
3. In repo **Settings → Pages**, set source to `Deploy from branch` →
   `main` / `/ (root)`. Within a minute your site is live at
   `https://your-handle.github.io`.

To preview locally:

```bash
bundle install
bundle exec jekyll serve
# open http://localhost:4000
```

## What to edit first

| File | What it controls |
| --- | --- |
| `_config.yml` | Your name, email, ORCID, Scholar, GitHub handle, affiliation |
| `index.html` | Hero copy on the homepage |
| `pages/research.md` | The research statement (the page that matters most) |
| `_data/publications.yml` | Add new papers here — newest at the top |
| `_data/talks.yml` | Add new talks/posters here |
| `pages/cv.md` | Education, awards, teaching |
| `assets/cv.pdf` | Drop your CV PDF here so the link works |

Adding a paper is a single block in `_data/publications.yml` — no HTML.

## Design notes

- Type: Supreme (sans) + JetBrains Mono for metadata, via Fontshare.
- Color: warm paper background, deep ink text, UW purple as a single
  restrained accent. Subtle hexagonal lattice motif in the homepage hero
  as a quiet nod to condensed matter — remove `.hero::before` in
  `assets/css/main.scss` if you'd rather not have it.
- Layout is a single readable column on a 12-column max width with
  asymmetric headers.

## Custom domain (optional)

When you're ready, add a `CNAME` file containing your domain (e.g.
`yourname.physics`) and configure DNS per
[GitHub's docs](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site).

## Migrating to a research group site later

The structure is intentionally set up so the transition is mostly
content, not code:

1. **Rename the repo** to `groupname.github.io` (or move to a new repo and
   keep this one as a personal redirect).
2. **Repurpose `index.html`** as the group landing page. Move the
   personal hero to `/pages/people/your-name.md`.
3. **Add a `_data/people.yml`** with one entry per group member (name,
   role, photo, bio, links). Create `/pages/people.html` that loops over
   it the same way `publications.html` loops over papers.
4. **Promote `_data/publications.yml`** to a group-wide list — the
   `authors` field already supports bolding individual names with
   `**Name**`, so you can highlight whoever the relevant member is.
5. **Add `/pages/openings.md`** for prospective students and postdocs.
6. **Update `_data/nav.yml`** to swap "CV" for "People" and "Openings".

Because everything lives in YAML data files and Markdown, none of the
existing content needs to be rewritten — only re-categorized.

## License

Content is yours. Code is MIT.
