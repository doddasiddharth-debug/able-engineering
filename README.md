# ABLE Engineering · Free courses

Free, self-paced engineering courses from ABLE Engineering, the engineering branch of
[ABLE Initiatives](https://ableinitiatives.com), a student-run 501(c)(3)
nonprofit. Live at **https://engineering.ableinitiatives.com**.

Static site, no build step, no accounts. GitHub Pages deploys it on every push
to `main` (`.github/workflows/static.yml`). It shares its app shell, script
and components with the other ABLE course sites (business., health.ableinitiatives.com,
prep.ableinitiatives.com).

## Courses

| Course | Views | Progress key |
|---|---|---|
| **Engineering Foundations: How Things Get Designed and Built**: the design process; fields and careers; measurement, units and estimation; forces, structures and materials; electricity and circuits; code, data and testing | `#ef`, `#ef-lesson-1`…`6`, `#ef-certificate` | `able.engineering.ef.v1` |
| **Aerospace Engineering: How Things Fly**: what aerospace engineers do; the four forces of flight; wings and lift; stability and control; rockets and propulsion; reaching space and orbit | `#ae`, `#ae-lesson-1`…`6`, `#ae-certificate` | `able.engineering.ae.v1` |

Each course has a dashboard, six lessons (goals, worked example, common
mistake, key idea, key terms, "try it yourself", a five-question quiz where
four right completes the lesson) and its own certificate. Shared views: **All
courses** (`#home`), **Calculators** (`#tools`: percent error, lever, Ohm's
law, glide ratio, lift, rocket liftoff) and **Glossary** (`#glossary`).

## Files

```
index.html               every view of every course (edit lessons here), and
                         <script id="site-config">: this site's name, colours,
                         logo, domain and courses
assets/css/engineering.css the shared course-site stylesheet with ABLE Engineering's
                         colour tokens (teals from the mark; gold swoosh accent)
assets/js/app.js         router, progress, quizzes, calculators, glossary,
                         certificates; identical on every ABLE course site
assets/js/analytics.js   anonymous GoatCounter visit and event counts
assets/images/           ABLE Engineering mark, ABLE mark (certificate seal), favicon
CNAME                    engineering.ableinitiatives.com
```

To add a course, copy an existing course's views in `index.html` (dashboard,
lessons, certificate, sidebar group, catalog tile) with a new id prefix, and
add it to `courses` in the site config.

## Content rules

- Every number is computed, not estimated; SI units first, US customary
  alongside. Standard, stable science only; no salaries, statistics or
  rankings. Licensure (FE, PE) described generally, as varying by state.
- **Safety first**: electricity stays with small batteries (about 1.5–9 V) and
  low-power parts, never wall outlets or household wiring; safety glasses and
  adult supervision with tools. Every page footer says so.
- No brands, kits, products or companies; example students are made up.
- An ABLE Engineering officer (ideally with a teacher) should review any new or
  changed lesson before it goes live.

## Visitor analytics

Anonymous visitor counts come from [GoatCounter](https://www.goatcounter.com)
(`assets/js/analytics.js`): no cookies, no personal data, nothing that
identifies a visitor, so no cookie banner is needed. One GoatCounter site
(code `siddo`, dashboard at https://siddo.goatcounter.com)
covers every ABLE site: ableinitiatives.com, prep. and business.ableinitiatives.com,
and Strands of Life. Each path is prefixed with its host to keep them apart.
The same `analytics.js` is copied into each repo; keep the copies in step.

Besides page views it records, as events: clicks on email links
(`email/…`) and on links to other sites (`outbound/…`), and in the course apps
`window.ableTrack(...)` calls (quizzes passed or failed, calculators used,
courses completed, certificates made, downloaded or printed; SAT sessions
finished). Visits from localhost are not counted.
