# Content Intelligence Engine

A Python pipeline that turns source content and typed model answers into durable, evidence-linked assessments.

## Features

- Primary publications, replies and quotes retain separate attribution.
- Typed output and relevance policies validate decisions before reuse.
- Persistent records support recovery and reuse without repeated inference.

## Stack

Python · typed contracts · local inference adapter · SQLite · JSONL · unittest

SQLite decision ledgers persist assessment identity, policy, evidence and replay state. JSONL is used for batch input and output.

## Getting started

Python >=3.10. Install with `python -m pip install -e .`. Run python -m unittest discover -s tests -v. A local inference backend is optional and is not required by these offline tests.

## How it works

```text
Attributed publication → input/policy checks → typed backend answer → validated assessment → decision ledger and queries
```

## Current limitations

Offline tests use controlled backends; they do not benchmark model quality or verify a live checkpoint. Internal package names are retained for compatibility. Original Apache-2.0 notices and third-party attribution are preserved.

## Tests

```console
python -m unittest discover -s tests -v
```

All 96 tests passed on Python 3.13.16 using offline fixtures or controlled backends. A live inference checkpoint was not exercised.

## License

See [LICENSE](LICENSE), [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md).
