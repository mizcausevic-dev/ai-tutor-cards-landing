# ai-tutor-cards-landing

Static landing page for the **AI Tutor Card** specification — the EdTech extension to the [Kinetic Gain Protocol Suite](https://github.com/mizcausevic-dev?q=spec).

Deployed at **[tutor.kineticgain.com](https://tutor.kineticgain.com)**.

## What's here

```
.
├── index.html              # the landing page
├── style.css               # styles
├── .github/workflows/
│   └── deploy.yml          # auto-sync to Hostinger over FTPS on push to main
└── README.md
```

No build step. The page is hand-written HTML + CSS so it boots instantly and degrades cleanly without JS.

## Local preview

```bash
python3 -m http.server 8080
# open http://localhost:8080
```

## Deployment

Pushes to `main` trigger a GitHub Actions workflow that FTP-syncs the site root to `/tutor/` on Hostinger.

The workflow needs three repo secrets:

| Secret | Description |
|---|---|
| `FTP_HOST` | Hostinger FTP server hostname |
| `FTP_USER` | Hostinger FTP username |
| `FTP_PASS` | Hostinger FTP password |

After the first push:

1. Confirm the workflow succeeded under **Actions**.
2. In Hostinger, create the subdomain `tutor.kineticgain.com` pointing at `/tutor/` as its document root.
3. Verify DNS resolution and SSL provisioning.

## Related repositories

- **[ai-tutor-card-spec](https://github.com/mizcausevic-dev/ai-tutor-card-spec)** — the specification, JSON Schema, and canonical examples.
- **[kinetic-gain-visualizer](https://github.com/mizcausevic-dev/kinetic-gain-visualizer)** — one visualizer for all six specs in the Kinetic Gain Protocol Suite, including AI Tutor Cards.
- **[mcp-kinetic-gain](https://github.com/mizcausevic-dev/mcp-kinetic-gain)** — unified MCP server exposing 24 tools across six specs.

## License

Apache-2.0. The underlying specification is AGPL-3.0; implementations and supporting sites like this one are unrestricted.
