# agents-anywhere-image-ci

Builds the upstream Agents Anywhere Server image (linux/amd64) on GitHub Actions
and pushes it to GHCR. Deployment stays manual: `./upgrade.sh <image>`.

- Scheduled daily at 03:00 Asia/Shanghai; also supports manual dispatch with a tag.
- Bark notification only when the release contains the deployed commit and its
  schema is not older (repo variables `DEPLOYED_COMMIT` / `DEPLOYED_SCHEMA`).

This repo is **public** because Actions on private repos is currently broken for
this account (all runs fail before a runner is assigned). The workflow contains no
secrets; `BARK_URL` is stored as an encrypted repository secret.
