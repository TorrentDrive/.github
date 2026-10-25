# .github

Organization-level defaults for [TorrentDrive](https://github.com/TorrentDrive).

| Path | What it does |
|------|--------------|
| `profile/README.md` | The page shown at [github.com/TorrentDrive](https://github.com/TorrentDrive) |
| `CONTRIBUTING.md` | Default contributing guide for every repo without its own |
| `SECURITY.md` | How to report a vulnerability |
| `CODE_OF_CONDUCT.md` | Default code of conduct |
| `.github/ISSUE_TEMPLATE/` | Default issue forms |
| `.github/PULL_REQUEST_TEMPLATE.md` | Default pull request template |

**This file is not the org profile.** GitHub renders `profile/README.md` on the
organization page and this one only on this repository. They used to hold the
same content, copied from `deploy/README.md`, which meant the org page carried
relative links like `docs/USAGE.md` that resolved against this repo and 404'd.

Product documentation belongs at
[tc.gitnasr.com/docs](https://tc.gitnasr.com/docs), never here.
