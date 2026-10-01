# GraphQL Unicode Encoder (WAF Bypass Tool)

This is a lightweight client-side utility designed for penetration testers and security researchers to evade Web Application Firewalls (WAF) blocking GraphQL traffic with **403 Forbidden** errors.

## How it works (WAF Evasion)
Many WAFs look for plain-text keywords, specific parameter structures, or blacklisted strings in the incoming JSON body. 

By converting the entire GraphQL query string into raw Unicode Escape Sequences (`\uXXXX`), the request becomes obfuscated to signature-based firewalls while remaining perfectly valid for backend JSON parsers (which decode the Unicode automatically before sending it to the GraphQL engine).

### Example
**Before (Blocked with 403 Forbidden):**
```json
{
  "query": "query { customer { orders(filter: { number: { eq: \"000000000\" } }) } }"
}
```

**After (Bypasses WAF successfully):**
```json
{
  "query": "\u0071\u0075\u0065\u0072\u0079\u0020\u007b\u0020\u0063\u0075\u0073\u0074\u006f\u006d\u0065\u0072..."
}
```

## Deployment
This application runs entirely in the user's browser (pure HTML/JS). No data is sent to external servers, making it completely secure for sensitive API testing.

---
Created by eparo
