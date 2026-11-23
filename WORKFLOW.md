# Updating danielbrent.com

The site is built and published from **this one repo** (`dbrentecon/danielbrent`).
GitHub Pages serves the `docs/` folder on the `main` branch at www.danielbrent.com.
No copying to any other repo.

## Every update

1. Open `danielbrent.Rproj` in RStudio.
2. Edit the right file (table below) and save.
3. Preview: in the **Terminal** tab run `quarto preview`
   (opens in your browser and refreshes as you save; Ctrl+C to stop).
4. Build: in the Terminal run `quarto render`  (rebuilds `docs/`).
5. Git pane: tick all changes (including `docs/`) -> Commit -> Push.
6. Live in 1-2 minutes. Hard-refresh (Ctrl+F5 / Cmd+Shift+R) if you see the old version.

Don't use RStudio's Build button. It runs the old R Markdown builder and fails on this Quarto site.

## Where things live

| To change...                  | Edit                                                |
|-------------------------------|-----------------------------------------------------|
| Bio, headshot, links at top   | `index.qmd` (top section)                           |
| Working papers                | `_working-papers.qmd`                               |
| Published articles            | `_publications.qmd` (also feeds the CV page)        |
| Work in progress              | `_in-progress.qmd`                                  |
| Reports & other publications  | `_reports.qmd`                                      |
| Teaching                      | `index.qmd` (Teaching section)                      |
| CV page text                  | `cv.qmd`                                            |
| CV PDF (Download buttons)     | replace `assets/cv/DanielBrentCV.pdf`, keep the name |
| Paper PDFs                    | add to `assets/papers/`, link as `assets/papers/name.pdf` |
| Colors / fonts                | `theme.scss`; layout and spacing: `styles.css`      |
| Menu bar                      | `_quarto.yml` (navbar)                              |

Only files that a page links to are published. Anything else in `assets/` stays private.
A new photo used as a background banner must also be listed under `resources:` in `_quarto.yml`.

## Copy-paste templates

Working paper:

    - [**Paper title**](https://link-to-paper) (with Coauthor One; Coauthor Two - Revise & Resubmit *Journal*)
    <details class="wp-abstract">
    <summary>Abstract</summary>
    Abstract text here.
    </details>

Published article (newest at top of `_publications.qmd`):

    - Brent, D. A., & Coauthor, X. (2026). **[Title](https://doi.org/...)** *Journal*, vol(issue), pages.  
      [Working paper](assets/papers/filename.pdf)

(The two spaces after `pages.` force the line break.)

Paper accepted? Cut it from `_working-papers.qmd`, reformat with the published template,
paste at the top of `_publications.qmd`.

## Gotchas

- Close a file's RStudio tab before someone else (or Claude) edits it on disk; otherwise
  RStudio can save its stale copy over the change.
- If a render complains about a missing file, check the path spelling and case (`assets/papers/...`).
- `_archive-pre-redesign-2026-11-20/` holds the pre-redesign files; nothing uses it.

## If the site breaks

- GitHub repo -> **Actions** tab: the latest "pages build and deployment" run should be green.
- GitHub repo -> **Settings -> Pages**: Branch `main`, folder `/docs`, custom domain `www.danielbrent.com`.
- To roll back a bad change: Git pane -> History, or ask Claude to restore the previous version of a file.
