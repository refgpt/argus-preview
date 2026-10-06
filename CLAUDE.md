# CLAUDE.md — argus-preview

Repo guide for coding agents. The cross-repo guide is the workspace `~/git/refgpt/CLAUDE.md`.

<!-- english-code-rule:v1 — the same section in every refgpt repo; change it everywhere at once -->
## Code is English — the product is Dutch (MANDATORY)

Wim, 2026-10-06: *the whole codebase is English, mandatory.* This is the same rule as in
the workspace `CLAUDE.md` (`~/git/refgpt/CLAUDE.md`) and in the Deriq repos.

**Everything a developer reads is English:** identifiers (functions, classes, variables,
files, folders), comments, docstrings / XML docs, test names, internal log messages, error
codes, commit messages, PR texts and script output meant for developers. A mixed-language
codebase costs every reader a translation step on every symbol, and it makes grep useless:
you never know whether a concept is filed under `found` or `gevonden`.

**What stays Dutch is content** that an end user or operator reads: UI copy, user-facing
error messages, e-mail templates, chat/assistant system prompts and tool instructions (they
steer a Dutch-speaking model), help and content articles, and operator-facing status lines
on screen. The test: *would a developer joining the team need to read this to change the
code?* If yes, it is English. If it is a sentence an end user sees, it stays Dutch.

- **New Dutch in code is never accepted**: not in identifiers, comments, docstrings, test
  names, internal logs, commit messages or PR texts. Reviewers (the review loops too) mark
  it as `major`.
- **Translate what you touch.** A comment that *quotes* real Dutch content (a UI string, an
  e-mail heading, a CSV header the parser accepts) keeps the quote, because translating it
  would describe text that does not exist.
- **Never silently rename a public contract**: API routes and JSON field names, DB tables
  and columns, enum values stored in data, event names, env variables. Those migrate only as
  separate, decided migrations with backwards compatibility (alias, view, deprecation
  window), and Wim makes the choice.
- **Large rename PRs only in coordination with the english-codebase lead** (plan in
  `~/git/refgpt/plans/english-codebase.md`, entry in `~/git/refgpt/TASKS.md`), so they do
  not collide with other agents' open PRs. Translating comments, test names and log
  messages in small PRs is always fine.
<!-- /english-code-rule -->
