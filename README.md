# ai-tutor-cards-landing

Static landing page for the **AI Tutor Card** specification — the EdTech extension to the [Kinetic Gain Protocol Suite](https://github.com/mizcausevic-dev?q=spec).

Deployed at **[tutor.kineticgain.com](https://tutor.kineticgain.com)**.

## What's here

```
.
├── index.html              # the landing page
├── style.css               # styles
├── .github/workflows/
│   └── deploy.yml          # manual GitHub Actions upload (currently unverified)
└── README.md
```

No build step. The page is hand-written HTML + CSS so it boots instantly and degrades cleanly without JS.

## Local preview

```bash
python3 -m http.server 8080
# open http://localhost:8080
```

## Deployment

Merging to `main` does not deploy. The GitHub Actions upload runs only on `workflow_dispatch`; its FTPS path is unverified. For a release, use the reviewed local Hostinger SSH/SFTP route with a pinned host key, exact file backups and hashes, hosted checks, and a tested restore.

The manually dispatched Actions upload needs three repo secrets:

| Secret | Description |
|---|---|
| `FTP_HOST` | Hostinger FTP server hostname |
| `FTP_USER` | Hostinger FTP username |
| `FTP_PASS` | Hostinger FTP password |

After a manual release, verify the hosted page, DNS, and TLS. The existing `tutor.kineticgain.com` document root is `/tutor/`.

## Related repositories

- **[ai-tutor-card-spec](https://github.com/mizcausevic-dev/ai-tutor-card-spec)** — the specification, JSON Schema, and canonical examples.
- **[kinetic-gain-visualizer](https://github.com/mizcausevic-dev/kinetic-gain-visualizer)** — visualizer for supported Suite documents, including AI Tutor Cards.
- **[mcp-kinetic-gain](https://github.com/mizcausevic-dev/mcp-kinetic-gain)** — v0.10.0 unified MCP server with 75 tools for twelve Suite specs, DefenseTech checks, and implementation previews.

## License

Apache-2.0 for this site. The underlying specification is MIT-licensed; reference implementations carry their own licenses.
