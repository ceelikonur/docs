# BrainAPI — SOC 2 Type I Internal Controls

**Prepared for:** SOC 2 Type I Audit
**Date:** 2026-02-26
**Scope:** BrainAPI SaaS Platform

---

## Trust Service Criteria Coverage

| Criteria | Status |
|----------|--------|
| CC1 — Control Environment | In Progress |
| CC2 — Communication & Information | In Progress |
| CC3 — Risk Assessment | In Progress |
| CC4 — Monitoring Activities | In Progress |
| CC5 — Control Activities | Implemented |
| CC6 — Logical & Physical Access | Implemented |
| CC7 — System Operations | Implemented |
| CC8 — Change Management | In Progress |
| CC9 — Risk Mitigation | In Progress |
| A1 — Availability | Implemented |

---

## CC5 — Control Activities

### CC5.1: COSO Principle 10 — Select and Develop Control Activities

| Control | Implementation |
|---------|---------------|
| Authentication | NextAuth.js with session tokens + SSO (Azure AD, Okta) |
| Authorization | RBAC: admin/editor/viewer roles via org_members table |
| API authentication | Bearer token (hashed SHA-256 in user_api_keys) |
| MFA | Delegated to SSO providers (Azure AD, Okta) |

### CC5.2: Technology Controls

| Control | Implementation |
|---------|---------------|
| Encryption in transit | TLS 1.3 enforced by Vercel |
| Encryption at rest | Supabase AES-256 + application-level AES-256-GCM |
| Key management | ENCRYPTION_MASTER_KEY in environment (rotated quarterly) |
| DLP | Zero-Trust PII masking engine (src/lib/security/dlp-engine.ts) |

---

## CC6 — Logical and Physical Access

| Control | Implementation |
|---------|---------------|
| Access provisioning | SCIM v2 auto-provisioning (/api/scim/v2/Users) |
| Access de-provisioning | SCIM PATCH deactivate + DELETE deprovision |
| Privileged access | withOrgAuth('admin') middleware wrapper |
| Audit trail | audit_logs table (user_id, tool_name, timestamp, request/response) |
| Session management | NextAuth.js JWT/session with configurable expiry |

---

## CC7 — System Operations

| Control | Implementation |
|---------|---------------|
| System monitoring | Agent traces + usage_events telemetry |
| Error tracking | Server-side error logging |
| Incident detection | Guardrails engine (jailbreak, DLP, topic restriction) |
| Backup | Supabase daily automated backups (Point-in-time recovery) |
| Availability | Vercel Edge Network + Supabase HA |

---

## CC8 — Change Management

| Control | Implementation |
|---------|---------------|
| Version control | Git (all changes via PR review) |
| Type safety | TypeScript strict mode (`npx tsc --noEmit`) |
| Deployment pipeline | Vercel CI/CD (Preview → Production promotion) |
| DB migrations | Supabase migrations tracked in /sql directory |

---

## Pending Controls (Audit Readiness Checklist)

- [ ] Formal Security Policy document
- [ ] Vendor risk assessment for sub-processors
- [ ] Employee security awareness training records
- [ ] Formal incident response playbook
- [ ] Penetration test report (schedule: Q2 2026)
- [ ] Business continuity plan
- [ ] SOC 2 auditor engagement (Target: Q3 2026)

---

## Data Classification

| Level | Examples | Handling |
|-------|----------|---------|
| Public | Marketing content, docs | No restrictions |
| Internal | Logs, metrics | Authenticated access only |
| Confidential | User data, API keys | Encrypted, access-controlled |
| Restricted | Private keys, master encryption key | Environment secrets, never logged |
