# GraphQL Unicode Encoder 

A simple, lightweight web tool designed for security testing and bug bounty hunting. It converts GraphQL queries into a fully Unicode-escaped (`\uXXXX`) JSON format to help bypass strict Web Application Firewalls (WAFs) that block standard requests (such as 403 Forbidden on Introspection queries).

## Features
* **Full Unicode Escape**: Converts every character of the query into its hexadecimal Unicode escape sequence.
* **JSON Structure Preservation**: Outputs a clean, valid JSON object ready to be pasted directly into tools like **Caido** or **Burp Suite**.
* **Introspection Ready**: Includes a built-in placeholder example for full schema introspection testing.
* **One-Click Copy**: Easily copy the generated payload to your clipboard.

## Usage
1. Open `index.html` in any modern web browser.
2. Paste your GraphQL query into the input box (or use the default placeholder).
3. Click **Generate Unicode JSON**.
4. Copy the result and use it in your proxy/testing tool (Caido/Burp Suite).

## Author
* **eparo** (eparotest675@gmail.com)
