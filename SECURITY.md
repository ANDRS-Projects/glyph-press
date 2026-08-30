# Security

## Scope

Glyph Press is a static, single-page web app with no server, no build
step, and no third-party npm/pip/etc. dependencies — everything runs
client-side from `index.html`. The only network calls the page makes are
to Google Fonts (for display type) and, on iOS/Mac Safari, reading its
own `manifest.json`/icon files.

That keeps the attack surface small, but this repo still follows the
standard ANDRS-Projects security scanning stack:

| Check | Workflow | Runs on |
|---|---|---|
| **Trivy** — CVE / IaC scan | `.github/workflows/trivy.yml` | every push/PR to `main`, plus weekly |
| **Gitleaks** — secret scan | `.github/workflows/gitleaks.yml` | every push/PR to `main` |

Both fail the build on findings. There's no `package.json`/lockfile in
this repo, so there's no dependency-lockfile policy or `npm audit` step
to enforce — nothing here to go stale.

## Reporting a vulnerability

This is a small personal/hobby project, not a service handling user
data. If you find something worth flagging anyway (e.g. an XSS vector
in the text-conversion logic), please open an issue or reach out
directly rather than a public PR with exploit details.
