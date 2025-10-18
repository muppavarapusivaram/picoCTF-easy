# Challenge: Log Hunt

 1. List item

**Category:** 🧬 Forensics  
**Points:** 50  
**Date:** Oct 2025  

---

## 🧩 Description

**Author:** Yahaya Meddy  

Our server seems to be leaking pieces of a secret flag in its logs. The parts are scattered and sometimes repeated. Can you reconstruct the original flag? Download the logs and figure out the full flag from the fragments.

---

## 🕵️ Approach

### 1. Open the downloaded `server.log` file in a terminal

### 2. Use `grep` to extract only the lines containing the flag fragments:

```bash
cat server.log | grep FLAGPART
```

**Output (sample from the log):**

```
[1990-08-09 10:00:10] INFO FLAGPART: picoCTF{us3_
[1990-08-09 10:02:55] INFO FLAGPART: y0urlinux_
[1990-08-09 10:05:54] INFO FLAGPART: sk1lls_
[1990-08-09 10:05:55] INFO FLAGPART: sk1lls_
[1990-08-09 10:10:54] INFO FLAGPART: cedfa5fb}
[1990-08-09 10:10:58] INFO FLAGPART: cedfa5fb}
[1990-08-09 11:04:27] INFO FLAGPART: picoCTF{us3_
[1990-08-09 11:04:29] INFO FLAGPART: picoCTF{us3_
[1990-08-09 11:09:16] INFO FLAGPART: y0urlinux_
[1990-08-09 11:12:40] INFO FLAGPART: sk1lls_
[1990-08-09 11:16:58] INFO FLAGPART: cedfa5fb}
[1990-08-09 12:19:23] INFO FLAGPART: picoCTF{us3_
[1990-08-09 12:23:43] INFO FLAGPART: y0urlinux_
[1990-08-09 12:25:32] INFO FLAGPART: sk1lls_
[1990-08-09 12:28:45] INFO FLAGPART: cedfa5fb}
```

### 3. Remove duplicates and show only the unique fragments (one-liner command):

```bash
cat server.log | grep FLAGPART | sort | uniq
```

**Clean output:**

```
picoCTF{us3_
y0urlinux_
sk1lls_
cedfa5fb}
```

### 4. Reconstruct the full flag by joining the fragments in order:

```
picoCTF{us3_y0urlinux_sk1lls_cedfa5fb}
```

---

## ✅ Final Flag

```
picoCTF{us3_y0urlinux_sk1lls_cedfa5fb}
```

---

## 🔧 Commands used (copy-paste ready)

```bash
# show all FLAGPART lines
cat server.log | grep FLAGPART

# show unique fragments (sorted)
cat server.log | grep FLAGPART | sort | uniq
```

---

## 💡 Notes / Learning

- `grep` efficiently filters log files for relevant markers (here `FLAGPART`).
- `sort | uniq` is a quick way to remove repeated fragments and reveal distinct pieces.
- When fragments are scattered in logs, look for consistent markers (timestamps, tags like `FLAGPART`) to extract them.
- Manually or programmatically join fragments once order is known to reconstruct hidden strings/flags.

---

## ⚠️ Reminder

Use write-ups for learning only. Do not publish active CTF flags that would violate contest rules.
