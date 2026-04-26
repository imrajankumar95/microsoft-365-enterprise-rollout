# E3 vs E5 — License Tradeoffs

## Why This Matters

Microsoft 365 has different license tiers. **E3** is the standard business plan. **E5** is the premium plan (more security, more cost). Picking the right one is an architecture decision — not a sales pitch.

This project used **E3** because it covers ~80% of secure collaboration needs. Here's what E3 gave us, and what we gave up.

---

## What E3 Includes (and worked great)

| Feature | What It Does |
|---------|--------------|
| **Office Apps** | Word, Excel, PowerPoint, Outlook, Teams |
| **Email** | Exchange Online with 100 GB mailbox |
| **File Storage** | OneDrive (1 TB per user) + SharePoint |
| **Identity** | Entra ID (login + access control) |
| **Defender for Office 365 (Plan 1)** | Anti-phishing, anti-malware, anti-spam |
| **Audit Logs** | Track user activity for compliance |
| **Message Encryption** | Auto-encrypt sensitive emails |
| **Microsoft Purview (basic)** | Data governance, retention, sensitivity labels |

✅ E3 handles the daily work for most companies.

---

## What E3 *Doesn't* Have (and we worked around)

| Feature | E5 Only | Workaround on E3 |
|---------|---------|------------------|
| **Safe Links** (URL scanning in real-time) | ✅ | User awareness training + Defender baseline |
| **Safe Attachments** (sandbox unknown files) | ✅ | Standard anti-malware scan |
| **Advanced Alert Policies** (smart, customizable alerts) | ✅ | One basic alert configured manually |
| **OneDrive: 1-yr recycle + 5-yr retain in one policy** | ✅ | Split into two separate policies |
| **eDiscovery Premium** (legal investigations) | ✅ | Standard eDiscovery sufficient for now |
| **Microsoft Defender for Endpoint** (device protection) | ✅ | Out of scope — handled by separate antivirus |
| **Insider Risk Management (advanced)** | ✅ | Basic DLP policies + manual reviews |

---

## Cost vs Value — Decision Logic

| Scenario | Pick |
|----------|------|
| Small/mid org, standard threats, budget-conscious | **E3** |
| Regulated industry (finance, healthcare, legal) | **E5** |
| Heavy remote work + BYOD + advanced threats | **E5** |
| Need automated incident response | **E5** |

**E3 ≈ $36/user/month**
**E5 ≈ $57/user/month**

For 300 users → **$75K/year extra** for E5.

---

## What I Learned

- License tier shapes what's *possible*, not just what's *available*
- Many "E5 features" can be partially replicated with E3 + smart configuration
- Document gaps clearly — auditors and security teams will ask
- E3 is the **right starting point**; upgrade to E5 when threat surface grows

---

## In One Sentence

E3 is enough to build a secure, compliant M365 environment for most mid-sized organizations — but you must know what you're trading away.
