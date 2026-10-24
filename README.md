# Agent Authorization Gate — Source-Linked Experiment

**Status: minimal executable prototype; not a secure authentication mechanism.**

## Research question
Can a deterministic gate deny action requests that lack trusted user approval? The [hypothesis](hypothesis.json) links a source signal but does not establish novelty or validate the security model.

## What actually runs
`evaluate(value)` accepts only dictionaries with `explicit_approval is True` and `trusted_origin == "user"`. Two unit tests cover one allowed and one untrusted-origin case.

**Security limitation:** the caller supplies both fields. No user identity or origin is verified, so an attacker can forge them. The prototype does not enforce real-world authorization.

## Run
```bash
python -m unittest discover -s . -p 'test_*.py' -v
```

## Contribution target
Add forged-origin and malformed-input tests, specify an adversary model, and propose a verifiable approval mechanism with regression tests. Keep the prototype independent from secrets and production accounts.

This is a [radar-generated experiment](https://github.com/AMMARICA1791/ai-research-agents), not a validated invention.
