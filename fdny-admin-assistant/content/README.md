# Content folder — your official forms & directives

The app ships with **generic** report templates. Replace them with your department's official
forms in two ways:

1. **Rebuild the templates in-app** — open **Templates**, then rename/add/remove sections and
   fields (or duplicate a starter) so each form matches your official AAR, inspection report,
   memo, etc. Templates are stored in the browser and used by the Reports view.
2. **Link official reference PDFs** — drop authorized files here and list them in
   `manifest.json`; they appear in the app's **Reference** view when hosted.

```json
{
  "references": [
    { "title": "Official AAR form + instructions", "file": "content/aar-official.pdf" },
    { "title": "Inspection SOP", "url": "https://your-access-controlled-host/insp-sop.pdf" }
  ]
}
```

> ⚠️ FDNY forms and directives are internal/copyrighted. Only add copies you're authorized to
> use, and **do not commit them to a public repository** — keep the repo private, or link to an
> access-controlled location.
