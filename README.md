# 🧩 picoCTF Easy Challenges Write-ups

This repository contains my personal write-ups for **Easy-level picoCTF challenges**.  
Each write-up includes the problem description, approach, and key learning points — focusing on understanding *how* and *why* each challenge works.

> ⚠️ All content is for **educational and ethical learning** only.  
> Active challenge flags are **not shared** to respect competition integrity.

---

## 📂 Categories
| Category | Description |
|-----------|--------------|
| 🕸️ Web Exploitation | Exploring websites, hidden data, and scripts |
| 🔐 Cryptography | Basic ciphers, encoding, and encryption techniques |
| 🧬 Forensics | File analysis, metadata, and data recovery |
| 🧠 Reverse Engineering | Understanding simple binaries and logic |
| ⚙️ General Skills | Basic Linux, scripting, and problem-solving |

---

## 🧠 Example Write-up Format
Each challenge is documented in a Markdown file like this:

```markdown
# Challenge: Insp3ct0r
**Category:** Web Exploitation  
**Points:** 50  
**Date:** Oct 2025  

## 🧩 Description
Inspect the web code and find the hidden hints.

## 🕵️ Approach
1. Open DevTools → View Source.
2. Found hidden data in `robots.txt`, `style.css`, and `myjs.js`.
3. Combine hints → Decode → Get flag.

## 💡 Learning
- Using browser developer tools effectively  
- Recognizing hidden data in client-side files
