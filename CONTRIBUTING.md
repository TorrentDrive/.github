# Contributing to TorrenClou

Thanks for helping out. This applies to every repository in the organization
unless that repository has its own `CONTRIBUTING.md`.

## How the repositories fit together

| Repository | Contents |
|------------|----------|
| [backend](https://github.com/TorrenClou/backend) | .NET 9 API and the torrent, Google Drive and S3 workers |
| [frontend](https://github.com/TorrenClou/frontend) | Next.js web app |
| [deploy](https://github.com/TorrenClou/deploy) | The Dockerfile that bundles all of the above into one image, plus the installer and CI |
| [website](https://github.com/TorrenClou/website) | Documentation site, and the canonical docs |

Merging to `main` in `backend` or `frontend` rebuilds the combined image in
`deploy`. Nothing needs to be released by hand.

## Documentation goes in one place

**`website/content/docs` is the single source of truth.** Everything about
installing, configuring or operating TorrenClou lives there and is published at
[tc.gitnasr.com/docs](https://tc.gitnasr.com/docs).

READMEs link to it. They do not restate it. If your change adds a setting, a
port, or a step, document it in `website` — not in a README, and not in a
second README as well.

This is not a style preference. Before this rule, the same environment variable
table existed in five files and no two agreed; the org profile documented ports
that had been changed a year earlier.

**Use absolute links in Markdown.** A relative link works on the file you are
editing and breaks everywhere the file gets rendered — the org profile page,
the container registry description, and every site that scrapes a raw README.

## Pull requests

- Branch from `main`: `feat/…`, `fix/…`, `docs/…`, `chore/…`.
- **Write the PR title as a conventional commit** — `feat(storage): …`,
  `fix(worker): …`, `docs: …`. Pull requests are squash-merged, so the title
  becomes the commit message and drives changelog generation. A `!` after the
  scope, or a `BREAKING CHANGE:` footer, marks a breaking change.
- Explain *why* in the description. The diff already shows what.
- Keep unrelated changes out. A rename touching every file is impossible to
  review alongside a behaviour change.

## Database migrations must roll forward

Users are told they can roll back to a previous version. That is only true if
an older build can run against a newer schema, so:

- **Additive changes only.** Add columns and tables; do not rename or drop them
  in the same release that stops using them.
- A column that release *N* stops writing may only be dropped in *N+2*.
- Never edit a migration that has shipped. Add another one.

## Code style

Match the file you are editing. The .NET projects use nullable reference types
and implicit usings; the TypeScript is strict-mode with no implicit `any`.
There is no separate style guide to memorize.

## Security

Do not open a public issue for a vulnerability. See
[SECURITY.md](https://github.com/TorrenClou/.github/blob/main/SECURITY.md).
