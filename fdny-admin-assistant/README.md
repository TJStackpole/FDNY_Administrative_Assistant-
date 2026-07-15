# FDNY Officer Administrative Assistant

A single-file, zero-install dashboard that helps FDNY officers (Lt / Capt / Chief) handle the
paperwork side of the tour: draft tone-controlled email and fill out reports (AARs, inspection
reports, memos, and more). Built to host free on GitHub Pages and to connect later to the FDNY
cloud/intranet.

> **Not affiliated with, or endorsed by, the FDNY.** The report templates are **generic
> starters**, not official FDNY forms (which are internal). Customize them in **Templates** to
> match your official paperwork.

## Features

- **Dashboard** — tasks done today, draft/total documents, pending sync, quick actions.
- **Email Composer** — enter recipient, purpose, key points, and a requested action, then dial
  two sliders: **Professionalism** (less ↔ more) and **Directness** (less ↔ more), plus length
  and quick presets (Professional / Casual / More direct / Softer). Generates the draft offline;
  edit it directly, copy, open in your mail app, or save. Optional **Improve with AI** appears
  when an AI endpoint is configured.
- **Reports** — pick a form (After Action Report, Company Inspection, Apparatus Out-of-Service,
  Drill/Training Record, Tour Roster, Memo), fill it out with a live preview, then copy,
  print-to-PDF, export, save, or queue to the cloud. Headers auto-fill from your profile.
- **My Documents** — every saved email/report with status (draft / final / submitted), reopen
  to edit, export, or queue.
- **Templates** — fully customize forms: rename, add/remove sections & fields, duplicate, or
  build new ones. This is how you turn the generic starters into official paperwork.
- **Daily Tasks** — a customizable officer admin checklist that resets each day.
- **Settings & Integrations** — officer profile & signature, default tone, and endpoints for
  the intranet (email/memos), cloud (reports), and an optional AI writing service. Export/import
  everything as JSON.
- **Reference** — public sources plus a slot for your official forms via `content/manifest.json`.

## How the writing works (honestly)

Email drafting and report assembly are **rule-based and run fully offline** — no network, no keys,
works on GitHub Pages. The tone engine adjusts greeting, phrasing, hedging, contractions, and
sign-off from the two sliders. For a full generative rewrite, set an **AI endpoint** in Settings
(your intranet LLM or the Anthropic API via a proxy) — it POSTs `{system,prompt}` and expects
`{text}` back. Left blank, the app still produces usable drafts.

## How the integrations work (honestly)

FDNY's cloud/intranet are internal and a static page can't hold secret keys, so the app uses an
**adapter**: everything is saved locally first, and in **Settings** you set POST endpoints for the
intranet (emails/memos) and cloud (reports). When set, the queue POSTs each item as
`{ kind, data }`. Point them at your agency's API — or a proxy that adds authentication — and the
paperwork flows automatically. Until then, use **Export** (JSON) and **Print/PDF**.

## Run it

- **Locally:** open `index.html`. "Open in mail" uses your default mail app; Print/PDF uses the
  browser. The reference manifest auto-loader needs http(s) — host it or run
  `python3 -m http.server`.
- **GitHub Pages:** push the repo → Settings → Pages → deploy from `main` / root.

## Data & privacy

Profile, settings, documents, templates, and tasks are stored in your browser (`localStorage`);
nothing leaves the device until you configure an endpoint and push. Use **Export/Import JSON** to
move your setup between devices.

## Notes

- The header emblem is a **generic placeholder** (the FDNY logo is a City of New York trademark) —
  swap the inline `<svg>` in the top bar.
- Templates are generic until you customize them; treat generated documents as drafts to review.

## License

MIT — see [LICENSE](LICENSE). Covers the application code only, not FDNY publications, trademarks,
forms, or data you add.
