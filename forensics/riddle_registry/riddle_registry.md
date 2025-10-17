# Challenge: Riddle Registry
**Category:** Forensics  
**Points:** 50  
**Date:** Oct 2025  

## 🧩 Description
Downloaded a PDF file from picoCTF: `Hidden Confidential Document.pdf`.  
The challenge description hinted that the flag is hidden somewhere inside the PDF metadata.

---

## 🕵️ Step-by-Step Approach

### Step 1: Inspect PDF metadata
For PDF forensic challenges, metadata often contains hidden flags. Normally, you would check metadata using:

```bash
pdfinfo "Hidden Confidential Document.pdf"
exiftool "Hidden Confidential Document.pdf"



These commands show information such as Author, Creator, Producer, and custom metadata fields where flags are often hidden.

Step 2: Identify the suspicious string
In this challenge, the description itself hinted at a string in the metadata:

cGljb0NURntwdXp6bDNkX20zdGFkYXRhX2YwdW5kIV9jYTc2YmJiMn0=

At first glance, it looks like random letters and numbers, but it is Base64 encoded.

Why Base64?
Base64 is commonly used in CTFs to hide text or binary data in a readable format. Here, the flag was hidden inside the PDF’s metadata using Base64 encoding.


Step 3: Decode the Base64 string
To extract the flag, decode the string using:

echo "cGljb0NURntwdXp6bDNkX20zdGFkYXRhX2YwdW5kIV9jYTc2YmJiMn0=" | base64 -d


Output:

picoCTF{puzzl3d_m3tadata_f0und!_ca76bbb2}

Flag found:

picoCTF{puzzl3d_m3tadata_f0und!_ca76bbb2}

