# Contract architecture

## Responsibility

A research tool for replaying historical Stellar payment routes against recorded market data to compare path choices, slippage, and settlement outcomes.

## Security boundary

Every state-changing operation must authenticate the actor that is allowed to cause
the change. Contract storage is intentionally smaller than the application database.

## Future specification

The generic development contract in this baseline must be replaced with the
project-specific state model before production deployment.
