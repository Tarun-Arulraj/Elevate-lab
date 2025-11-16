# Sender Analysis — Flipkart Phishing Sample

### Sender Fields Observed
- **From:** "Flipkart Support" <order-update@flipkarrt-secure.com>
- **Return-Path:** <order-update@flipkarrt-secure.com>
- **Reply-To:** support@flipkart.com
- **To:** tarunarulraj23@gmail.com

### 1. Domain Mismatch & Spoofing Indicators
- The visible sender domain **flipkarrt-secure.com** is NOT an official Flipkart domain.
- It uses a **typo-squatted** variant: *flipkarrt* (double "r"), a common phishing trick.
- The `Reply-To` address points to **support@flipkart.com**, which is legitimate, but attackers often use this technique to appear trustworthy.

### 2. Authentication Failures
- SPF: **softfail** — the sending server (185.203.112.14) is not authorized by this domain.
- DKIM: **none** — no signature at all.
- DMARC: **fail** — policy set to REJECT, but the message bypassed authentication.

These failures strongly suggest the sender **is not legitimate**.

### 3. Infrastructure Red Flags
- IP 185.203.112.14 is a VPS-hosting IP (commonly used in scams).
- Domain `flipkarrt-secure.com` is not a known Flipkart property.

### Final Verdict
**Sender is spoofed.** The domain is impersonating Flipkart, and authentication breakdown further confirms phishing.
