# PathReplay Contracts

> Historical payment-path simulator — Soroban contract layer.

![Logo](assets/logo.svg)

## Why this repository exists

A research tool for replaying historical Stellar payment routes against recorded market data to compare path choices, slippage, and settlement outcomes.

The contract repository owns only the state transitions that benefit from Stellar's
verifiability. It does not attempt to become the application's database. The intended
boundary is deliberate: contract state proves the important protocol event, while
off-chain services handle indexing, search, presentation, and operational workflows.

## Core responsibilities

- Define the minimal on-chain state model.
- Enforce authorization at the contract boundary.
- Emit useful events for indexers and audit tooling.
- Keep sensitive or bulky information off-chain.
- Provide deterministic unit tests for protocol behavior.

## Development model

The initial implementation is Testnet-oriented. Production deployment is a separate
engineering step that requires network configuration, contract review, migration
planning, monitoring, and security review.

## Repository layout

```text
src/           Contract implementation
tests/         Contract-level tests
docs/          Architecture and protocol notes
Makefile       Local build/test commands
```

## Testing philosophy

Tests should cover happy paths, invalid inputs, unauthorized callers, repeated calls,
boundary values, and state transitions. A green test suite is not an audit.

## Integration

The app and backend repositories consume this layer through generated bindings or
Stellar SDK calls. Contract identifiers are environment-specific and are intentionally
not hard-coded into this repository.

## Roadmap

- [ ] Complete protocol-specific storage model
- [ ] Add authorization edge-case tests
- [ ] Add event/indexing fixtures
- [ ] Test against Stellar Testnet
- [ ] Document deployment and upgrade procedure
- [ ] Perform independent security review before production

## Maintainer

Maintainer: 

