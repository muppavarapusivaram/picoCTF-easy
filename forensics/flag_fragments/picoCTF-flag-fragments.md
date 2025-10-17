# Challenge: Server Log — Flag Fragments

**Category:** Forensics
**Points:** 20
**Date:** October 17, 2025

## 🧩 Description

Server logs contain repeated, partial pieces of a secret flag. The pieces are scattered across many log entries and sometimes repeated. Reconstruct the original flag by extracting and combining the fragments.

## 📁 Folder

Place this file under: `forensics/flag_fragments/`

## 🕵️ Approach

1. Search the log for lines that include the keyword `FLAGPART`.

```bash
cat server.log | grep FLAGPART
```

2. To remove duplicates and make fragments easier to read, sort and uniq the results:

```bash
cat server.log | grep FLAGPART | sort | uniq
```

3. Inspect the unique fragments. In this case, the unique fragments were:

```
picoCTF{us3_
y0urlinux_
sk1lls_
cedfa5fb}
```

4. Reconstruct the flag by concatenating the fragments in logical order (start-to-end):

```
picoCTF{us3_y0urlinux_sk1lls_cedfa5fb}
```

## ✅ Final Flag

```
picoCTF{us3_y0urlinux_sk1lls_cedfa5fb}
```

## 💡 Notes / Tips

* When flags are broken into repeated fragments, `grep`, `sort`, and `uniq` are quick tools to collect and deduplicate fragments.
* If fragments are out of order, use timestamps (the left-most column) to sort by time and reassemble.
* Watch out for overlapping fragments; the longest or most complete piece is often the full flag.

## 🧠 Learning

* Practical log forensics: filtering logs, deduplication, and reconstructing artifacts.
* Using basic shell tools (`grep`, `sort`, `uniq`) to solve forensic puzzles quickly.

---

*Prepared for inclusion in the repository under `forensics/flag_fragments/`. Add any additional context or screenshots as needed.*
