# BrainAPI Privacy Policy

**Effective Date:** [DATE]
**Last Updated:** 2026-02-26

---

## 1. Introduction

BrainAPI ("we", "our", "us") operates the BrainAPI platform at brainapi.dev. This Privacy Policy explains how we collect, use, disclose, and protect your personal information.

---

## 2. Information We Collect

### 2.1 Account Information
- Name, email address, and password (hashed with bcrypt)
- Organization name and billing information
- OAuth tokens from connected integrations (encrypted AES-256-GCM at rest)

### 2.2 Usage Data
- Agent interaction logs (stored in `agent_traces`)
- Tool call telemetry (stored in `audit_logs`)
- Token consumption events (stored in `usage_events`)
- IP addresses, browser type, and device information

### 2.3 Content Data
- Prompts and responses sent through the AI chat interface
- Workflow definitions and automation configurations
- Knowledge base documents you upload
- Custom MCP server configurations

---

## 3. How We Use Your Information

| Purpose | Legal Basis |
|---------|-------------|
| Providing the service | Contract performance |
| Billing and invoicing | Contract performance |
| Security and fraud prevention | Legitimate interest |
| Product improvement | Legitimate interest |
| Marketing communications | Consent |
| Legal compliance | Legal obligation |

---

## 4. Data Retention

| Data Type | Retention Period |
|-----------|-----------------|
| Account data | Duration of account + 30 days post-deletion |
| Agent traces | 90 days (rolling) |
| Audit logs | 1 year |
| Usage events | 2 years |
| Backups | 30 days |

---

## 5. Data Sharing

We do **not** sell your personal data. We share data only with:

- **Supabase** (database hosting) — Data Processing Agreement in place
- **Anthropic / OpenAI / Google** (AI providers) — only the prompt content you send
- **Stripe** (payment processing) — billing data only
- **Vercel** (hosting) — infrastructure provider

---

## 6. Your Rights (GDPR)

If you are located in the European Economic Area, you have the right to:

- **Access**: Request a copy of your personal data
- **Rectification**: Correct inaccurate data
- **Erasure**: Request deletion of your data ("right to be forgotten")
- **Portability**: Receive your data in a machine-readable format
- **Objection**: Object to processing based on legitimate interest
- **Restriction**: Restrict processing in certain circumstances

To exercise these rights, email **privacy@brainapi.dev**.

---

## 7. Security

- All data transmitted over TLS 1.3
- Database encrypted at rest (AES-256)
- Integration tokens encrypted with AES-256-GCM + unique IV per token
- Zero-Trust DLP engine masks PII in AI prompts
- Access logs retained for audit purposes

---

## 8. Cookies

We use strictly necessary cookies for:
- Session authentication (NextAuth.js session cookie)
- CSRF protection

No third-party tracking cookies.

---

## 9. Contact

**Data Controller:** BrainAPI, Inc.
**Email:** privacy@brainapi.dev
**DPO:** dpo@brainapi.dev

---

## 10. Changes

We will notify users of material changes via email and in-app notification with 30 days notice.
