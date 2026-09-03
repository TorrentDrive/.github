# Security Policy

## Reporting a vulnerability

**Please do not open a public issue.**

Use GitHub's private vulnerability reporting on the affected repository:
open its **Security** tab, then **Report a vulnerability**. That opens a private
thread visible only to maintainers.

- [backend](https://github.com/TorrenClou/backend/security/advisories/new)
- [frontend](https://github.com/TorrenClou/frontend/security/advisories/new)
- [deploy](https://github.com/TorrenClou/deploy/security/advisories/new)
- [website](https://github.com/TorrenClou/website/security/advisories/new)

Please include what you found, how to reproduce it, and what an attacker could
do with it. You will get an acknowledgement, and credit in the advisory when the
fix ships, unless you would rather not be named.

## Supported versions

TorrenClou is self-hosted and ships as a single image. Only the most recent
release is supported — if you are reporting a bug, please confirm it on the
current image first.

## What TorrenClou expects of you

The product is designed to run on a machine you control, reached over your own
network or behind your own reverse proxy.

- **Only port 47100 needs to be reachable** for normal use. The API on 47200,
  Grafana on 47500 and Prometheus on 47600 do not need to be exposed to the
  internet, and exposing them widens your attack surface for no benefit.
- **The admin account is the only account, and there is no password reset.**
  Losing it means losing access.
- **Generated secrets live on the `torrencloud-pgdata` volume.** Deleting that
  volume rotates the signing keys and logs everyone out. Back it up before an
  upgrade you are unsure about.
- **Your storage credentials are yours.** Google Drive and S3 are accessed with
  credentials you supply; nothing is proxied through a third party.
