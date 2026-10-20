# Security audit — 2026-10

Account audited: `HeziLiu` (4 repositories found under the account, including 2 forks).
Audit date: 2026-10. Every check result below is reported exactly as it came back from the API, including errors.

| Repository | Type | Default branch | Language |
|---|---|---|---|
| HeziLiu/Little-rookie | source (non-fork) | master | Java |
| HeziLiu/Big-Buzzard | source (non-fork) | master | — |
| HeziLiu/CodingInterviewChinese2 | fork | master | C++ |
| HeziLiu/awesome-chatgpt-prompts-zh | fork | main | — |

## Dependabot alerts

The open-Dependabot-alert check could not be completed for any repository. Each call returned an API error, not an alert list:

- `HeziLiu/Little-rookie` — API error: `403 Resource not accessible by personal access token`
- `HeziLiu/Big-Buzzard` — API error: `403 Resource not accessible by personal access token`
- `HeziLiu/CodingInterviewChinese2` — API error: `403 Dependabot alerts are disabled for this repository`
- `HeziLiu/awesome-chatgpt-prompts-zh` — API error: `403 Dependabot alerts are disabled for this repository`

Result: 0 alerts could be enumerated. Two repos explicitly report Dependabot alerts as disabled at repository level; for the other two the token lacks permission to read the Dependabot alerts API. No open Dependabot alert data is quotable until this is re-run with an appropriately scoped token.

## Code scanning alerts

The open-code-scanning-alert check also failed for every repository, each returning the same permission error:

- `HeziLiu/Little-rookie` — API error: `403 Resource not accessible by personal access token`
- `HeziLiu/Big-Buzzard` — API error: `403 Resource not accessible by personal access token`
- `HeziLiu/CodingInterviewChinese2` — API error: `403 Resource not accessible by personal access token`
- `HeziLiu/awesome-chatgpt-prompts-zh` — API error: `403 Resource not accessible by personal access token`

Result: 0 code scanning alerts returned, therefore no alert-level detail lookup was possible (there were no alert numbers to pull full details for). This is a tooling/token permission gap, not evidence that the repositories are clean.

## Workflows

The GitHub Actions workflow listing succeeded for all four repositories and each came back empty:

- `HeziLiu/Little-rookie` — no workflows found (total_count: 0)
- `HeziLiu/Big-Buzzard` — no workflows found (total_count: 0)
- `HeziLiu/CodingInterviewChinese2` — no workflows found (total_count: 0)
- `HeziLiu/awesome-chatgpt-prompts-zh` — no workflows found (total_count: 0)

Result: the account runs no GitHub Actions workflows at all, so there is no Actions supply-chain surface (no third-party actions, no workflow permissions) to review this quarter.

## Open pull requests

A search for open PRs authored by the account returned 408 open pull requests in total (spanning repositories beyond the four owned repos, mostly in the `mcpmark-eval-liuhezi` organization). Examples of what is still outstanding:

- `mcpmark-eval-liuhezi/checklist-smoke-test#1` — "Add release checklist to README" (intentionally left unmerged as a dry run)
- `mcpmark-eval-liuhezi/org-research-hub#1` — "Add org research digest" (shortlist still needs re-verification)
- `mcpmark-eval-liuhezi/q3-release-metrics#1` — "Add Q3 QA summary report"

## Next steps

1. Re-run the Dependabot and code scanning checks with a token that has the security-events / vulnerability alerts read scope — the current token's 403s mean the two most important sections of this audit are unverified.
2. Enable Dependabot alerts on `CodingInterviewChinese2` and `awesome-chatgpt-prompts-zh` (both report alerts disabled at the repository level).
3. Confirm the intended state of the two forks; if they are no longer needed, delete them to shrink the account's attack surface.
4. Once permissions are fixed, pull full details for any code scanning alerts that surface and quote them here.
5. Triage the open PRs listed above — in particular close out or merge the dry-run PRs so they don't linger through the next review cycle.
6. Consider enabling secret scanning / push protection on the two source repositories, which have no automated scanning coverage today.
