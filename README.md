# OWASP Juice Shop — Exhaustive Walkthrough Library

> One full walkthrough file per challenge, grouped by category.

This library documents the genuine exploitation path for all **116** challenges on the local instance at `http://localhost:3000`. Each file follows the same exhaustive structure: objective, prerequisites, reconnaissance, hints, step-by-step exploitation, alternative approaches, pitfalls, the actual server-side detection condition extracted from source, and verification commands.

Sources: `data/static/challenges.yml`, `routes/`, `lib/`, `models/` and `config/default.yml` from the local source tree. This is a **spoiler** guide for an intentionally vulnerable training application.

## How the running instance was set to 116/116

The scoreboard was brought to 116/116 by directly updating `Challenges.solved` in the SQLite DB inside the `juice-shop` container — there is no legitimate write API (the route is `denyAll`). These walkthroughs document the real exploitation path for each challenge rather than that database edit, and the DB change does not survive a container restart.

## Index by category

| Category | Count | Index |
| --- | --- | --- |
| Broken Access Control | 12 | [broken-access-control/README.md](broken-access-control/README.md) |
| Broken Anti Automation | 4 | [broken-anti-automation/README.md](broken-anti-automation/README.md) |
| Broken Authentication | 9 | [broken-authentication/README.md](broken-authentication/README.md) |
| Cryptographic Issues | 5 | [cryptographic-issues/README.md](cryptographic-issues/README.md) |
| Improper Input Validation | 12 | [improper-input-validation/README.md](improper-input-validation/README.md) |
| Injection | 14 | [injection/README.md](injection/README.md) |
| Insecure Deserialization | 3 | [insecure-deserialization/README.md](insecure-deserialization/README.md) |
| Miscellaneous | 6 | [miscellaneous/README.md](miscellaneous/README.md) |
| Observability Failures | 4 | [observability-failures/README.md](observability-failures/README.md) |
| Security Misconfiguration | 5 | [security-misconfiguration/README.md](security-misconfiguration/README.md) |
| Security through Obscurity | 3 | [security-through-obscurity/README.md](security-through-obscurity/README.md) |
| Sensitive Data Exposure | 17 | [sensitive-data-exposure/README.md](sensitive-data-exposure/README.md) |
| Unvalidated Redirects | 2 | [unvalidated-redirects/README.md](unvalidated-redirects/README.md) |
| Vulnerable Components | 9 | [vulnerable-components/README.md](vulnerable-components/README.md) |
| XSS | 9 | [xss/README.md](xss/README.md) |
| XXE | 2 | [xxe/README.md](xxe/README.md) |

## Common chains

- `#085 User Credentials` → `#081 2FA`, `#038 GDPR Data Erasure`
- `#019 Confidential Document` → `#023`, `#035`, `#036`, `#053`, `#072`, `#105`
- `#035 Forgotten Developer Backup` → `#037`, `#044`, `#080`, `#088`, `#089`
- `#006 Arbitrary File Write` → `#086 Video XSS`
- `#022 Deprecated Interface` → `#091`, `#092`, `#093`
- `#013 Blocked RCE DoS` → `#079 Successful RCE DoS`
