# TorrenClou

**Self-hosted torrent-to-cloud.** Point it at a `.torrent`, pick the files you
want, and it downloads them on your server and uploads them straight to Google
Drive or any S3-compatible storage.

One container. No configuration files.

## Install

<!-- snippet:install-linux -->
```bash
curl -fsSL https://raw.githubusercontent.com/TorrenClou/deploy/main/install.sh | bash
```
<!-- /snippet -->

Windows (PowerShell):

<!-- snippet:install-windows -->
```powershell
irm https://raw.githubusercontent.com/TorrenClou/deploy/main/install.ps1 | iex
```
<!-- /snippet -->

Docker is the only requirement. There is no `.env` to fill in and no secrets to
generate — the container creates its own on first boot and keeps them on its
data volume. Open the URL it prints and create your account.

## What it does

- Add a torrent by file or magnet link, inspect its contents, and download only
  the files you actually want.
- Upload finished downloads to **Google Drive** or **S3** — AWS, Backblaze B2,
  Cloudflare R2, MinIO, or anything else that speaks the S3 API.
- Uses **your** storage credentials. Nothing is proxied through a third party.
- Watch transfers, retries and failures from the dashboard, with Grafana
  dashboards bundled in if you want them.

Everything else has a working default and is configurable in the app's Settings.

## Documentation

**[tc.gitnasr.com/docs](https://tc.gitnasr.com/docs)** — installation, first-run
setup, configuration, storage providers, monitoring and troubleshooting.

## Repositories

| Repository | Contents |
|------------|----------|
| [deploy](https://github.com/TorrenClou/deploy) | The all-in-one Docker image, the installer, and CI. Start here. |
| [backend](https://github.com/TorrenClou/backend) | .NET 9 API and the torrent, Google Drive and S3 workers |
| [frontend](https://github.com/TorrenClou/frontend) | Next.js web app |
| [website](https://github.com/TorrenClou/website) | Documentation site — the canonical docs live here |

## Contributing

Issues and pull requests are welcome on any repository. See
[CONTRIBUTING.md](https://github.com/TorrenClou/.github/blob/main/CONTRIBUTING.md)
for how the repos fit together, and
[SECURITY.md](https://github.com/TorrenClou/.github/blob/main/SECURITY.md)
to report a vulnerability privately.

## License

MIT.
