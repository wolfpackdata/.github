# AGENTS.md — .github

Codex reads this file automatically at the repo root. It is the **repo-level** contract. The
**global** contract — the one that binds Codex in *every* Wolfpack repo — lives at
`~/.codex/AGENTS.md` and is maintained in
[`wolfpackdata/wp-codex-sop`](https://github.com/wolfpackdata/wp-codex-sop). Where the two
disagree, **this file wins** (it is nearer the work).

Keep this file thin. It carries **pointers, not copies**: Codex truncates instruction files
past `project_doc_max_bytes` with no warning, and a stale copy of an SOP silently overrides
the good one.

## Canonical repository
**`wolfpackdata/.github`** — always target this `owner/repo` for issues, PRs, and labels.
Resolve it from git (`gh repo view --json nameWithOwner`), never from the selected subfolder
name.

## GitHub workflow
This repo follows the Wolfpack GitHub SOP —
[`wolfpackdata/wp-github-sop`](https://github.com/wolfpackdata/wp-github-sop), authoritative
text in that repo's `docs/sop/`. **Read it before the first git or GitHub action of a
session**; nothing here overrides it. Risk-tiered changes — auth, data migration, security,
release tooling, CI/rulesets, or the SOP and skills other agents obey — and **every** release
PR take the **AI-review stage** before merge, with Codex as the AI Reviewer: see
`docs/sop/10-ai-review.md` and `docs/sop/runbooks/ai-review.md` in that repo, and
`docs/sop/09-roles-and-permissions.md` for what the AI Reviewer may and may not do (it
reviews; its approval never satisfies the `main` gate). Under `-p review` Codex is the AI
Reviewer (`main-wolfpack`); in every other profile it acts under the human's identity as an
AI Implementer.

## Notion workspace
Work that touches the Notion team space follows the Wolfpack Notion SOP —
[Wolfpack Notion SOP](https://app.notion.com/p/39dc70e5c7b481078ab8e2f2de4603b8) (mirror:
`wolfpackdata/wp-notion-team` → `docs/notion-sop/`). **Read it before the first Notion write
of a session**, and before that write confirm via `self` that the identity is **Main**
(`main@wolfstrategyllc.com`, `39cd872b-594c-817a-8412-00023f0d7dc8`) — any other identity is
a hard stop. Codex and Claude both act as Main, so **Codex suffixes every Notion comment it
writes with ` [codex]`**; Claude's are unmarked. If the SOP link doesn't resolve, warn the
Requester it's dead, then search the Notion teamspace for the *Wolfpack Notion SOP* page
(Wolfpack Document Hub) to recover the current URL.

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
