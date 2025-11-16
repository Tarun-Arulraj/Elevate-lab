# Header Analysis — Flipkart Phishing Sample

This document analyzes technical email headers for authenticity.

---

## 1. Authentication Results Summary
- **SPF:** softfail  
  The server 185.203.112.14 is NOT authorized to send emails for flipkarrt-secure.com.
- **DKIM:** none  
  Legitimate companies like Flipkart always sign outgoing emails.
- **DMARC:** fail  
  Domain policy is REJECT, yet this email was delivered → strong spoofing indicator.

---

## 2. Detailed Observations

### A. Return-Path vs From
- Return-Path: `order-update@flipkarrt-secure.com`
- From: `"Flipkart Support" <order-update@flipkarrt-secure.com>`

Both match, but the domain itself is fake.

### B. Received Header Chain
Received: from mail.flipkarrt-secure.com (unknown [185.203.112.14])
by smtp.gmail.com ...

- Reverse DNS mismatch (IP → no valid hostname)
- IP belongs to non-corporate VPS hosting

### C. Authentication-Results
- `spf=softfail`
- `dkim=none`
- `dmarc=fail`

This trifecta is extremely typical in phishing campaigns.

---

## 3. Message-ID Analysis
Message-ID: 20251115091204.XYZ987QWE@mail.flipkarrt-secure.com

- Generated format is generic
- Not using corporate Flipkart message-ID patterns

---

## Final Conclusion
This header is **not from Flipkart**.  
All trust mechanisms (SPF, DKIM, DMARC, RDNS) fail → email is definitively phishing.
