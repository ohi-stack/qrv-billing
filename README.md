# QR-V™ Billing — Consolidated Module Source

Billing is now a module of the primary QR-V platform rather than a separate public node.

## Canonical routes

```text
https://qrv.network/pricing
https://qrv.network/store
https://qrv.network/billing
https://qrv.network/issuer/billing
```

## Runtime architecture

```text
qrv.network billing UI
  ↓ server-to-server
api.qrv.network billing/account endpoints
  ↓
payment provider + PostgreSQL billing metadata
```

Payment-provider secrets, webhook secrets, and account-management credentials must remain server-side. Public browser code must never contain privileged billing keys.

## Scope

- issuer plans;
- subscriptions;
- implementation packages;
- invoices;
- usage metering;
- payment-provider integration;
- account status;
- entitlement checks;
- revenue operations.

## Commercial launch rule

QR-V can collect early implementation revenue through the consolidated `/store` and `/pricing` flows before a full self-service subscription engine is complete. The billing module should not create another public hostname.

## Repository status

Retain this repository as the billing source module and integration workspace. Production UI should be mounted under `qrv.network`, and machine-facing billing operations should be exposed through `api.qrv.network` only when implemented and secured.
