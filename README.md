# Content Intelligence Engine

A Python pipeline that turns source content and typed model answers into durable, evidence-linked assessments.

![review](https://img.shields.io/badge/review-private-374151) ![primary](https://img.shields.io/badge/primary-Python-2563EB) [![LinkedIn](https://img.shields.io/badge/LinkedIn-Douglas%20Silva-0A66C2?logo=linkedin&logoColor=white)](https://www.linkedin.com/in/douglas-silva-data-analyst/)

[Overview](#overview) · [Architecture](#architecture) · [Setup](#setup) · [Validation](#validation) · [Roadmap](#roadmap) · [Review notes](docs/REVIEW.md)

## Overview

- Primary publications, replies and quotes retain separate attribution.
- Typed output and relevance policies validate decisions before reuse.
- Persistent records support recovery and reuse without repeated inference.

**Technology:** Python · typed contracts · local inference adapter · SQLite · JSONL · unittest

**Persistence and data:** SQLite decision ledgers persist assessment identity, policy, evidence and replay state. JSONL is used for batch input and output.

## Architecture

```text
Attributed publication → input/policy checks → typed backend answer → validated assessment → decision ledger and queries
```

| Location | Review focus |
| --- | --- |
| [`src/omnia_news/pipeline.py`](src/omnia_news/pipeline.py) | Source/configuration inspected for scope and structure |
| [`src/omnia_news/intelligence.py`](src/omnia_news/intelligence.py) | Source/configuration inspected for scope and structure |
| [`src/omnia_news/_engine/ledger.py`](src/omnia_news/_engine/ledger.py) | Source/configuration inspected for scope and structure |
| [`tests/helpers.py`](tests/helpers.py) | Source/configuration inspected for scope and structure |
| [`pyproject.toml`](pyproject.toml) | Source/configuration inspected for scope and structure |

Internal package and module names are retained where changing them would affect imports or compatibility. This descriptive repository name does not imply a completed package/API migration.

## Setup

Python >=3.10. Install with pip install -e .. Run python -m unittest discover -s tests -v. A local inference backend is optional and is not required by these offline tests.

Start from an isolated environment. Use `.env.example` when present and inspect the configuration loader: an example file is not necessarily loaded automatically. Runtime databases, real account sessions and private credentials are not bundled. Live integration prerequisites are separate from local tests.

## Validation

Static parsing checked 40 Python files and 5 strict JSON files. Python syntax errors: 0; JSON errors: 0. The selected offline suite passed.

```console
python -m unittest discover -s tests -v
```

These results apply to the selected checks on the preparation copy. They do not establish deployment readiness, full coverage, live provider availability or measured performance. CI definitions, when present under `docs/ci-templates/`, are inactive review templates; no remote CI badge is claimed.

## Limits and current status

Offline tests use controlled backends; they do not benchmark model quality or verify a live checkpoint. Internal package names are retained for compatibility. Original Apache-2.0 notices and third-party attribution are preserved.

This private snapshot is for code and portfolio review. Generated runtime material and unreviewed binary assets may be excluded. [Review notes](docs/REVIEW.md) record preparation scope, findings and outstanding validation.

## Roadmap

- [ ] Validate a pinned local inference checkpoint separately from contract tests.
- [ ] Add a small synthetic end-to-end walkthrough.
- [ ] Review package naming and compatibility before any package distribution rename.

## History and attribution

25 existing commits were retained after path/content filtering. Original authors and author/committer dates were retained; commit hashes may change. Upstream commits are not presented as new work by the maintainer.

Existing license and attribution files are retained: [LICENSE](LICENSE). Review their scope and third-party notices before redistribution.

## Maintainer and feedback

Douglas de Oliveira Silva · [GitHub](https://github.com/qquante) · [LinkedIn](https://www.linkedin.com/in/douglas-silva-data-analyst/)

For this private review, report reproducible issues with a minimal fixture and the exact check output. Keep account data, credentials and generated sensitive reports out of issues and commits. Existing contribution guidelines apply where present.

**Topics:** `python`, `applied-ai`, `nlp`, `sqlite`, `data-pipeline`, `structured-output`, `event-processing`
