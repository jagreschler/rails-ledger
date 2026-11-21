# AGENTS

## Project

Rails 8.1 personal finance ledger. Planned: Solid Queue, Solid Cache, Solid Cable, Hotwire/Turbo, the auth generator, and Kamal deploy. Plain conventional Rails; use stock generators.

## Git flow

[Gitflow workflow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow).

`main` only ever holds stable, tagged releases. Feature branches come off `develop` and merge back into it. A release branch is cut from `develop`, tested on staging, then merged into `main` and back into `develop`, and `main` is tagged with the version so any release can be deployed at any time. Hotfixes are the only branches cut from `main`, and they merge into both `main` and `develop`. Agents never push to `main` or `develop` directly and never merge; open work goes on a feature branch for Jason to review.

## Branch names

Name branches in JIRA style, with the project name or abbreviation first, as in `PROJ-NAME-TICKET-NUMBER-FEATURE-NAME`.

## Workflow

TDD: red, green, refactor. For a bug, write a failing test first. Small, scoped PRs, one piece each. Every PR adds an entry to `docs/decisions.md` and updates any affected note in `docs/features/`, and has a plain-English "What this does and why" section. Tests and lint must pass.

## Tests

Test behavior and rules a user would notice. Never hard-code stored data (exact lists, fixtures copied into asserts). A few short, clearly named tests.

## Ruby style

Never use `unless`, and never use `!x` negation. Write `if` with `.present?`, `.blank?`, `.nil?`, or `== false` instead (in Rails prefer `.present?`). Named intermediate variables over long chains. Noun class names. Event-driven design for side effects: a class publishes a past-tense event and handlers react; it does not run downstream effects itself.

## Wording

Say "user" or "end user", not "player".

## Secrets

Never commit secrets or keys. The repo is public.
