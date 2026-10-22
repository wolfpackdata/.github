<!-- Wolfpack GitHub SOP — PR template. Squash-merges into `develop`. See docs/sop/02-commits-and-prs.md. -->

## Summary
<!-- What does this PR change, and why? One or two sentences. -->

## Related issues
<!-- Two kinds of line. NEVER closing keywords (Closes / Fixes / Resolves): the issue's
     Reporter closes it after verifying.
     Delivers: #N — this PR carries the fix. Every issue named here is labeled
       `fixed-on-develop` after the merge. Omit it (leave the line blank) when the branch is
       `prefix/N-slug` and the PR delivers exactly that issue: the branch number is the
       default. When any Delivers line names an issue, those issues are the whole set and the
       branch number is NOT added, so list every delivered issue, the branch's own included:
       `Delivers: #N, #M`. The keyword must start its line; prose that says "delivers #N"
       mid-sentence, and anything in a code fence or comment, does not count.
     Refs #N — a citation only (cites, defers to, or files an issue). It NEVER labels.
     See docs/sop/03-issues-and-labels.md → "What a merged PR delivers". -->
Delivers: #
Refs #

## Risk tier
<!-- risk-tiered = auth · data migration · security · release tooling · CI or rulesets · the SOP/skills other agents obey. Anything else is low. docs/sop/10-ai-review.md -->
low   <!-- or: risk-tiered → AI review required -->

## Acceptance criteria met
<!-- Copy the issue's criteria; tick each with the evidence, or write why not. -->
- [ ]

## Local verification results
<!-- CI runs where the repo has something to run; these local results complement it, they
     don't replace it. Paste the commands you actually ran and their results, credentials
     redacted (or "N/A — docs only"). -->

```
# e.g. npm test, npm run build, lint — with their output/summary
```

## Review handoff
<!-- Or the single line: not requested — low risk. See docs/sop/10-ai-review.md. -->
Run id:
Reviewed SHA:
Findings: P0 _ · P1 _ · P2 _ · P3 _
Dispositions:

## Checklist

- [ ] Conventional Commit title with an area scope (e.g. `feat(matrix): …`, `fix(compare): …`).
- [ ] Branch is `prefix/issue-number-kebab-slug`, cut from `develop`.
- [ ] No closing keywords. The fixed issue is the branch number or a `Delivers:` line; anything only cited is `Refs #N`.
- [ ] Risk tier stated; AI review done or `not requested — low risk`.
- [ ] Acceptance criteria copied from the issue and each one ticked with evidence.
- [ ] Full local suites run and results pasted above (or explicitly N/A).

<!-- `fixed-on-develop` is no longer a checklist item here. A checklist is read BEFORE the merge
     button, so a post-merge instruction on it could never fire — which is how the 2026-08-31
     misses happened. It is now applied by .github/workflows/fixed-on-develop.yml to the
     issues this PR delivers — the `Delivers:` lines above, else the issue number in the
     branch name; `Refs` lines are never labeled — and owned by the merging Maintainer where
     that workflow is not installed. See docs/sop/03-issues-and-labels.md. -->

