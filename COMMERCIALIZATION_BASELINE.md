# QR-V™ Billing — Commercialization Baseline

Billing exists to convert a paid plan or approved pilot into a controlled issuer entitlement. It must not become the canonical source for verification records.

## 30-day priorities

- map customer/payment state to issuer entitlement;
- expose safe server-side billing status to the private Admin Dashboard;
- track implementation revenue separately from recurring subscription revenue;
- support founding-issuer pilot onboarding;
- prevent unpaid, suspended, refunded, or unauthorized accounts from obtaining uncontrolled issuance privileges.

## Admin metrics

Expose or derive:

- implementation revenue;
- contracted MRR;
- paying issuers;
- active pilots;
- past-due accounts;
- suspended entitlements;
- plan/package;
- onboarding/provisioning state.

## Provisioning contract

```text
payment or approved pilot
→ entitlement event
→ issuer account provisioned
→ issuer authorization activated
→ issuance limits/policy attached
→ admin audit event
```

Billing data may control commercial entitlement, but QR-V record validity remains registry-controlled.

## Security

Payment-provider secrets and webhook signing secrets must remain server-side. Browser dashboards receive only the minimum account/billing metadata needed for authorized operators.
