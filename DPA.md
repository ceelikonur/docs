# Data Processing Agreement (DPA)

**Between:** BrainAPI, Inc. ("Processor")
**And:** Customer ("Controller")
**Date:** [DATE]

---

## 1. Definitions

- **Personal Data**: Any information relating to an identified or identifiable natural person.
- **Processing**: Any operation performed on Personal Data (collection, storage, use, transmission, deletion).
- **Data Subject**: The individual whose Personal Data is being processed.
- **GDPR**: EU General Data Protection Regulation (2016/679).

---

## 2. Subject Matter and Duration

BrainAPI processes Personal Data on behalf of the Customer solely to provide the BrainAPI AI agent platform services described in the Terms of Service. Processing continues for the duration of the service agreement.

---

## 3. Nature and Purpose of Processing

| Category | Purpose |
|----------|---------|
| Account data | Authentication and user management |
| Agent conversation data | Providing AI agent functionality |
| Integration tokens | Executing authorized automations |
| Usage telemetry | Billing, usage enforcement, analytics |
| Uploaded documents | Knowledge base and RAG functionality |

---

## 4. Types of Personal Data

- Name, email address
- Professional information (organization, role)
- Content of AI agent interactions (may contain PII)
- Technical identifiers (IP address, user agent)

---

## 5. Obligations of the Processor (BrainAPI)

BrainAPI shall:

1. Process Personal Data only on documented instructions from the Customer
2. Ensure confidentiality obligations for all authorized personnel
3. Implement technical and organizational security measures (Article 32 GDPR)
4. Not engage sub-processors without Customer's prior written consent
5. Assist Customer in responding to Data Subject rights requests
6. Delete or return all Personal Data upon termination of the service
7. Provide all information necessary to demonstrate compliance

---

## 6. Sub-Processors

Current sub-processors:

| Sub-Processor | Purpose | Location | DPA Link |
|--------------|---------|----------|----------|
| Supabase, Inc. | Database hosting | US/EU | supabase.com/dpa |
| Vercel, Inc. | Application hosting | US/EU | vercel.com/dpa |
| Stripe, Inc. | Payment processing | US | stripe.com/dpa |
| Anthropic, PBC | AI model inference | US | anthropic.com/privacy |
| OpenAI, LLC | AI model inference | US | openai.com/policies |

---

## 7. Security Measures (Article 32 GDPR)

Technical measures:
- Encryption in transit: TLS 1.3
- Encryption at rest: AES-256-GCM
- Token encryption: AES-256-GCM with unique IV per credential
- Zero-Trust DLP: PII masking before AI model transmission
- Access control: Role-based (admin/editor/viewer)
- Audit logging: All tool calls logged with timestamps

Organizational measures:
- Security awareness training for all staff
- Incident response policy (72h breach notification to supervisory authority)
- Annual penetration testing
- Least-privilege access principle

---

## 8. Data Subject Rights

Upon Customer request, BrainAPI will assist in:
- Responding to access requests within 30 days
- Correcting inaccurate data within 72 hours
- Deleting Personal Data within 30 days of termination
- Providing data exports in JSON format

---

## 9. International Transfers

For EU customers using the EU (Frankfurt) region, all data remains within the EEA. For US region customers, Standard Contractual Clauses (SCCs — Commission Decision 2021/914) are incorporated by reference.

---

## 10. Term and Termination

This DPA remains in effect as long as BrainAPI processes Personal Data on behalf of the Customer. Upon termination, BrainAPI will delete all Customer Personal Data within 30 days unless legally required to retain it.

---

## 11. Governing Law

This DPA is governed by the laws of the jurisdiction specified in the main Terms of Service agreement.

---

_Executed by the parties as of the date first written above._
