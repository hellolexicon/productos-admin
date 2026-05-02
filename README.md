# ProductOS admin

Static admin console + public changelog/roadmap for
[hellolexicon/ProductOS](https://github.com/hellolexicon/ProductOS).

Live at: https://hellolexicon.github.io/productos-admin/

The Changelog and Roadmap pages render without auth — they just fetch
`changelog.json` and `roadmap.json` from this same Pages origin.

The Settings tab (Flags · Changelog editor · Runs · Trigger) is gated by
a GitHub fine-grained PAT entered at runtime, scoped to
`hellolexicon/ProductOS` only, with these repository permissions:

- `Metadata: Read`
- `Actions: Read & write`
- `Variables: Read & write`
- `Contents: Read & write` — needed to author changelog entries

The PAT is stored only in the browser's localStorage; sent only to
`api.github.com`. The HTML itself contains no secrets.
