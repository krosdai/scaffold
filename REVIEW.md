# Code Review Policy

Repository-specific rules for automated code review. They extend the default
policy from `krosdai/.github` and take precedence where the two conflict.

## Pinning upstream actions and reusable workflows

A GitHub Actions `uses:` reference (an action or a reusable workflow) may point
at a tag such as `@v2` instead of a full commit SHA when the upstream owner is
one of these trusted organizations:

- `github`
- `anthropics`
- `krosdai`

Match the owner exactly: the segment before the first `/` in `uses:`. For these
owners, do not report a tag reference as unpinned or as a supply-chain risk,
and do not ask to replace it with a SHA. Tracking the tag is intentional, so
upstream fixes roll out without per-repository bump PRs.

Every other owner still requires a full 40-character commit SHA, preferably
with a trailing `# vX.Y.Z` comment. Branch references such as `@main` remain
reportable for every owner, including the trusted ones.
