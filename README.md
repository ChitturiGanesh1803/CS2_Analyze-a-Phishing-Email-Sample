# Phishing Email Analysis Report
# Use mxtoolbox 
## https://mxtoolbox.com/Public/Tools/EmailHeaders.aspx
## Sample Email
**From:** PayPal Security <security@paypal-verify.com>  
**Subject:** Urgent: Verify your account  
**Date:** Thu, 11 Dec 2025 18:59:00 +0000  

---

## 1. Suspicious Sender Address
- **Email:** `security@paypal-verify.com`  
- **Red Flags:**  
  - Domain `paypal-verify.com` is **not the official PayPal domain** (`paypal.com`).  
  - Slight domain variations are commonly used in phishing attacks.  

---

## 2. Email Header Analysis
- **Received:** Originating server `mail.example.com [192.0.2.1]` (not a PayPal server)  
- **SPF:** Fail (`domain of security@paypal-verify.com does not designate 192.0.2.1 as permitted sender`)  
- **DKIM:** Fail (`signature not verified`)  
- **DMARC:** Fail (`header.from=paypal-verify.com`)  

**Interpretation:** Email fails multiple authentication checks → likely spoofed.  

---

## 3. Suspicious Links
- **URL in email:** `https://example-phish.com/verify-paypal`  
- **Red Flags:**  
  - Domain does **not match official PayPal site**  
  - Hovering over the link would reveal the real, malicious URL  

---

## 4. Urgent or Threatening Language
- Phrases like:  
  - “Click the link below to verify within 24 hours”  
  - “or your account will be limited”  
- Creates a sense of urgency, pressuring the recipient to act quickly  

---

## 5. Spelling / Grammar Errors
- Email text is mostly correct, but professional emails rarely use such direct threatening language  

---

## 6. Other Phishing Traits
- Generic greeting: “Dear Valued Customer”  
- Requests action via link instead of official channels  
- Email sent from unrelated server (`mail.example.com`)  

---

## 7. Summary Table

| Indicator | Details |
|-----------|---------|
| Suspicious Sender | `security@paypal-verify.com` (fake domain) |
| Header Discrepancy | SPF/DKIM/DMARC fail; originating IP not PayPal |
| Malicious Link | `https://example-phish.com/verify-paypal` |
| Urgent Language | “Verify within 24 hours or your account will be limited” |
| Greeting | Generic (“Dear Valued Customer”) |
| Other Red Flags | Requests action via link, not official channels |

---

## Conclusion
This email is **a clear phishing attempt**.  
- The domain is fake, authentication checks fail, and the link is malicious.  
- Users should **not click the link or provide any personal information**.  
