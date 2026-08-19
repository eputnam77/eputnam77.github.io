# eputnam77.github.io

Source for <https://eputnam77.github.io/> — a portfolio hub for six open-source
projects covering document review and approval workflows, federal writing-standards
validation, authoring tooling, and public-data dashboards.

Static HTML and one stylesheet. No build step, no dependencies, no JavaScript required
to render the content.

## Structure

```
index.html                              Hub: bio + project index
404.html                                Not-found page
assets/site.css                          Shared stylesheet
projects/<slug>/index.html               One landing page per project
robots.txt                               Crawl rules (search + AI agents)
sitemap.xml                              All seven URLs
llms.txt                                 Plain-text digest for AI agents
.nojekyll                                Serve files as-is, skip Jekyll
```

## Projects listed

| Project | Page | Repository |
| --- | --- | --- |
| DocReview360 | [/projects/docreview360/](https://eputnam77.github.io/projects/docreview360/) | [repo](https://github.com/eputnam77/DocReview360) |
| FedStyleValidator | [/projects/fedstylevalidator/](https://eputnam77.github.io/projects/fedstylevalidator/) | [repo](https://github.com/eputnam77/FedStyleValidator) |
| SimpleDocReview | [/projects/simpledocreview/](https://eputnam77.github.io/projects/simpledocreview/) | [repo](https://github.com/eputnam77/SimpleDocReview) |
| DocEditorPlayground | [/projects/doceditorplayground/](https://eputnam77.github.io/projects/doceditorplayground/) | [repo](https://github.com/eputnam77/DocEditorPlayground) |
| TopStateHeatmap | [/projects/topstateheatmap/](https://eputnam77.github.io/projects/topstateheatmap/) | [repo](https://github.com/eputnam77/TopStateHeatmap) |
| SellingPriceEstimator | [/projects/sellingpriceestimator/](https://eputnam77.github.io/projects/sellingpriceestimator/) | [repo](https://github.com/eputnam77/SellingPriceEstimator) |

## Discoverability notes

Each page carries a `<title>`, a `meta description`, a canonical URL, Open Graph tags,
and JSON-LD structured data. The hub declares a `Person` plus an `ItemList` of all six
projects; each project page declares a `SoftwareApplication`, a `BreadcrumbList`, and —
where it answers real questions — a `FAQPage`.

`robots.txt` explicitly allows the major search and AI crawlers. `llms.txt` gives agents
a single plain-text digest of every project so they do not have to reconstruct it from
the HTML.

Project paths intentionally live under `/projects/<slug>/` rather than at the repository
name, so a repository can later publish its own GitHub Pages site at
`eputnam77.github.io/<RepoName>/` without colliding with this one.

## Local preview

```bash
python -m http.server 8000
```

Then open <http://localhost:8000>. Root-relative paths (`/assets/site.css`) require
serving from the repository root rather than opening files directly.

## Deployment

GitHub Pages serves `main` at the repository root. Pushing to `main` publishes.
