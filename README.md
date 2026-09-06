# Three Hundred Days

A public learning tracker, and the plan behind it. Three hundred days of cloud
and DevOps study, run as three hundred-day blocks with real breaks between them.

**Live tracker → https://pareshzawar.github.io/three-hundred-days/**

I have written this plan twice before. Both times I got to day one and stopped.
So this time the tracker is public before the plan is — logged days in green,
missed days in red, and a consistency percentage calculated from both. Nothing
here gets quietly deleted.

---

## The plan

Two to three hours on weekdays, four to five at weekends. Roughly 760 hours of
material across eleven certification exams — eight Oracle OCI paths plus GitHub
Foundations, GitHub Actions, and Terraform Associate.

| Part | Window | Focus | Exams |
|---|---|---|---|
| 1 | 7 Sep – 15 Dec 2026 | GitHub, OCI Networking, Migration Architect, Terraform, Ansible | GH-900 · 1Z0-1124-26 · 1Z0-1123-26 · Terraform Associate |
| 2 | 4 Jan – 13 Apr 2027 | Containers, GitHub Actions, Kubernetes, OCI DevOps, Cloud Operations, Observability | GH-200 · 1Z0-1109-26 · 1Z0-1067-26 · 1Z0-1111-26 |
| 3 | 26 Apr – 3 Aug 2027 | OCI Cloud Security, Autonomous AI Database, Architect Professional, Integration, Fusion, capstone | 1Z0-1104-26 · 1Z0-931-26 · 1Z0-997-26 |

The breaks between parts are scheduled, not slippage. Two earlier attempts had no
margin and neither survived a bad week.

The order is deliberate. OCI Networking sits early because it overlaps four later
certification paths; Cloud Operations precedes Cloud Security because two of its
modules repeat verbatim; Architect Professional goes last because three of its
seven modules arrive as revision by then. Sequenced differently, you study the
same material twice.

## Why it is public

An accountability tracker that only shows wins is theatre. This one shows the
missed days in red and folds them into the percentage, so a bad week is a data
point rather than something to hide. The whole point is that the number stays
honest even when it is bad.

## How progress is recorded

`progress.json` is the public record:

```json
{
  "updated": "2026-09-07",
  "logged": [1, 2, 3]
}
```

Day numbers are absolute across all three parts: 1–100 is part one, 101–200 part
two, 201–300 part three.

To update: open the tracker, click the days you completed, press
**Export progress.json**, and commit the downloaded file. Local browser edits
layer on top of the committed file, so nothing is lost between commits.

From part two onward this becomes a GitHub Actions job — reading the file,
computing the streak, and opening a pull request with a drafted progress post.
That is one of the labs in the plan, not a shortcut around it.

## Editing the plan

The tracker is editable in the browser. Press **Edit plan** to reorder modules
or change their priority; the day ranges recompute automatically and always sum
to 100 per part. Priorities run P1 (protected) to P4 (awareness only). Learning
in public means the plan responds to what the market asks for, so the structure
is meant to move.

## Deployment

Static site, no build step. GitHub Pages deploys from `main` via
`.github/workflows/pages.yml`. Enable it once under
**Settings → Pages → Source → GitHub Actions**.

## Files

| File | Purpose |
|---|---|
| `index.html` | The tracker. Self-contained, editable, no dependencies. |
| `progress.json` | Public record of completed days. |
| `GUIDE.md` | Operating guide: hosting, updating, publishing. |
| `.github/workflows/pages.yml` | Pages deployment. |

## Follow along

- Blog — [cloudexplorers.club](https://cloudexplorers.club), the *Clouding Up* series
- Progress posts on LinkedIn, tied to shipped work rather than day counts

## Credits

Planned and sequenced with [Claude](https://claude.ai) (Anthropic) — including
the overlap analysis across all eleven certification paths, and the parts where
it argued the plan was too big. The tracker was then built by hand as the first
lab of part one.

## Licence

The plan, tracker, and structure are free to copy and adapt — MIT. The linked
courses belong to their respective authors.
