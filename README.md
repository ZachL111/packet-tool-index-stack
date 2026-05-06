# packet-tool-index-stack

`packet-tool-index-stack` explores cli tools with a small Python codebase and local fixtures. The technical goal is to package a Python local lab for index analysis with append-only fixtures, checkpoint recovery checks, and documented operating limits.

## Purpose

The project exists to keep a narrow engineering decision visible and testable. For this repo, that decision is how file span and argument risk should influence a review result.

## Packet Tool Index Stack Review Notes

For a quick review, compare `report density` with `file span` before reading the middle cases.

## What Is Covered

- `fixtures/domain_review.csv` adds cases for file span and terminal width.
- `metadata/domain-review.json` records the same cases in structured form.
- `config/review-profile.json` captures the read order and the two review questions.
- `examples/packet-tool-index-walkthrough.md` walks through the case spread.
- The Python code includes a review path for `report density` and `file span`.
- `docs/field-notes.md` explains the strongest and weakest cases.

## Implementation Notes

The core code exposes a scoring path and the added review layer uses `signal`, `slack`, `drag`, and `confidence`. The domain terms are `file span`, `terminal width`, `argument risk`, and `report density`.

The Python implementation avoids hidden state so fixture changes are easy to reason about.

## Command

```powershell
powershell -NoProfile -ExecutionPolicy Bypass -File scripts/verify.ps1
```

## Audit Path

The same command runs the local verification path. The highest-scoring domain case is `recovery` at 218, which lands in `ship`. The most cautious case is `baseline` at 124, which lands in `watch`.

## Limits

The repository is intentionally scoped to local checks. I would expand it by adding adversarial fixtures before adding features.
