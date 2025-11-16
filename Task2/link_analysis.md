# Link Analysis — Flipkart Phishing Sample

## Embedded Link Found
Visible text:  
**"View Order & Verify Payment"**

### href (actual destination):
http://flipkart-secure-checkout.in/login?uid=8934217


### Visible vs Actual Comparison
| Displayed Text                     | Actual Href                                           | Match? |
|-----------------------------------|--------------------------------------------------------|--------|
| View Order & Verify Payment       | http://flipkart-secure-checkout.in/login?uid=8934217  | ❌ No  |

---

## Red Flags in the URL
1. **Domain mismatch:**  
   “flipkart-secure-checkout.in” is not Flipkart’s real domain.

2. **HTTP instead of HTTPS:**  
   Sensitive login page delivered insecurely → major phishing indicator.

3. **IP-redirect pattern likely:**  
   Such domains often redirect users to IP-based credential harvesting pages.

4. **Query parameter:**  
   `uid=8934217` gives illusion of personalization.

---

## Risk Assessment
- **Risk level:** HIGH  
- This URL is designed to steal login/billing credentials under the guise of “order verification.”
