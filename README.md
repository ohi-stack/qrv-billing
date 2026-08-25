# QR-V™ Billing — Consolidated Module Source

Billing is a module of the primary QR-V platform rather than a separate public node.

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

## 30-day commercial priority

The flagship revenue offer is the **QR-V™ Verified Certificate Pilot**. Billing work must prioritize the shortest path from qualified issuer to paid and entitled issuer.

Commercial scoreboard:

- implementation revenue collected / booked;
- contracted MRR;
- paying issuers;
- active pilots;
- unpaid / failed payments;
- plan distribution;
- average revenue per issuer;
- implementation status linked to billing status.

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

QR-V can collect early implementation revenue through the consolidated `/store` and `/pricing` flows before a full self-service subscription engine is complete.

The commercial sequence should be:

```text
qualified issuer
→ pilot / implementation offer
→ payment or approved invoice
→ entitlement created
→ issuer onboarding unlocked
→ production issuance
→ recurring subscription state tracked
```

The Admin Dashboard at `qrv.network/admin` should receive server-side billing summaries for implementation revenue, MRR, account state, and payment exceptions. Do not expose provider secrets or raw privileged billing credentials to the browser.

## Pricing governance

Historical QR-V documents contain multiple pricing generations. Production pricing displayed to customers must come from one canonical billing configuration rather than duplicated hard-coded values across repositories.

## Repository status

Retain this repository as the billing source module and integration workspace. Production UI should be mounted under `qrv.network`, and machine-facing billing operations should be exposed through `api.qrv.network` only when implemented and secured.

Do not create another public billing hostname for the 30-day commercial sprint.
