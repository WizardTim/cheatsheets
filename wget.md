[Back to Cheatsheets Index](README.md)
# wget Cheatsheet

---

#### Retrieve content from URL and save locally to ISO 8601 UTC timestamped filename

`wget -O './'$(date --utc +%Y%m%dT%H%M%SZ).html https://example.com`

---
