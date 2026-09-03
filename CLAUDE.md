# CLAUDE.md — .github

## Canonical repository
**`wolfpackdata/.github`** — always target this `owner/repo` for issues, PRs,
and labels. Resolve it from git (`gh repo view --json nameWithOwner`), never from the
selected subfolder name.

## GitHub workflow
This repo follows the Wolfpack GitHub SOP (the `github-gitflow` and `create-github-issue`
skills + the [`wolfpackdata/wp-github-sop`](https://github.com/wolfpackdata/wp-github-sop)
repo). Nothing here overrides it — see those for branching, commits, PRs, labels,
versioning, and releases. Risk-tiered changes — auth, data migration, security, release
tooling, CI/rulesets, or the SOP and skills other agents obey — and every release PR take
the **AI-review stage** (Codex as the AI Reviewer) before merge; see
`docs/sop/10-ai-review.md` in that repo. Under `-p review` Codex is the AI Reviewer
(`main-wolfpack`); in every other profile it acts under the human's identity as an AI
Implementer. Sessions that can't load the skills (e.g. the
mobile app) read the SOP from that repo's `docs/sop/`.

## Notion workspace
Work that touches the Notion team space follows the Wolfpack Notion SOP (the
`notion-create-project` / `-task` / `-product` / `-client` and `notion-link-task-github`
skills + the `wolfpackdata/wp-notion-team` repo's `docs/notion-sop/`). Nothing here
overrides it — the live Notion team space is authoritative for icons, templates, and schema.
Full SOP page (readable from any session, mobile included):
[Wolfpack Notion SOP](https://app.notion.com/p/39dc70e5c7b481078ab8e2f2de4603b8). If that
link doesn't resolve, warn the Requester it's dead, then search the Notion teamspace for
the *Wolfpack Notion SOP* page (Wolfpack Document Hub) to recover the current URL.

## What this repo is
GitHub's **org-level default community health repository** for `wolfpackdata`. The
`.github/ISSUE_TEMPLATE/` forms and `.github/PULL_REQUEST_TEMPLATE.md` here are served by
GitHub to **every repo in the org that does not carry its own copy**, so the SOP's issue and
PR templates reach a repo without any script installing them. It carries **templates only** —
never `CODEOWNERS` (not a community health file; it stays per-repo), never a secret.

**The template files are a byte-identical mirror of `wolfpackdata/wp-github-sop/.github/`**,
the canonical set. Change them there first; this repo receives them as a byte-identical
fan-out (`sop-fanout`), never as an independent edit.

**The default branch must stay `develop`.** GitHub reads the org defaults from this repo's
default branch, so flipping it would silently empty the org's inherited templates.

No build, no test suite, no runtime — a `.github` repo is content GitHub reads, not code that
runs.
