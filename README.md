# GraphQL Unicode Encoder (WAF Bypass Tool) 🚀

This is a lightweight client-side utility designed for penetration testers and security researchers to evade Web Application Firewalls (WAF) blocking GraphQL traffic with **403 Forbidden** errors.

## 🛡️ How it Works (WAF Evasion)
Many modern WAFs look for plain-text keywords, specific database structures, or blacklisted strings in the incoming JSON body. If they spot suspicious patterns, they instantly drop the request and return a `403 Forbidden` status.

By converting the entire GraphQL query string into raw Unicode Escape Sequences (`\uXXXX`), the request becomes completely obfuscated to signature-based firewalls. However, backend JSON parsers will automatically decode the Unicode sequences back into text before passing the query to the GraphQL engine, successfully bypassing the restriction.

### ⚠️ Real WAF/403 Trigger Example
The built-in example demonstrates a real, standard GraphQL Introspection query. Production environments almost always block this query with a `403 Forbidden` to prevent mapping out the API infrastructure.

**Before (Blocked instantly with 403 Forbidden):**
```json
{
  "query": "query IntrospectionQuery { __schema { queryType { name } types { name } } }"
}
```

**After (Successfully Obfuscated - Bypasses WAF):**
```json
{
  "query": "\u0071\u0075\u0065\u0072\u0079\u0020\u0049\u006e\u0074\u0072\u006f\u0073..."
}
```

## ⚙️ Deployment & Security
This application runs entirely in the user's browser (pure HTML/JavaScript). 
* **Zero Dependencies:** No heavy libraries required.
* **100% Private:** No data is ever sent to external servers or API logging endpoints. It is completely safe to use for sensitive infrastructure testing.

---
**Made by eparo** 🚀
* Email: eparotest675@gmail.com
* HackerOne: [hackerone.com/eparo](https://hackerone.com)
