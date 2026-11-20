# PDF Password Cracking — Dictionary Attack Lab

Week 3 project from my Cybersecurity & Ethical Hacking internship at **Networkwalks Academy**. This repo documents a hands-on exploration of password-protected PDF cracking using two different approaches: a classic offline tool (John the Ripper) and a browser-based dictionary attack tool.

## 📋 Overview

The goal was to understand how password hashes are extracted from encrypted files and how dictionary attacks recover the original password, comparing a professional security tool against a simplified educational tool that mimics the same logic.

## 🧩 Module 1: John the Ripper + Johnny (GUI)

- Extracted the password hash from an encrypted PDF (`$pdf$` format, pdf2john-compatible)
- Loaded the hash into **Johnny**, the GUI front-end for John the Ripper
- Ran a dictionary/wordlist attack against the hash
- Successfully recovered the password and unlocked the PDF

**Tools used:** John the Ripper (jumbo build), Johnny GUI

## 🧩 Module 2: Networkwalks Hash Calculator & Password Cracker

- Used the **Hash Calculator** tool to parse the PDF and extract a crackable `$pdf$` hash directly in-browser (no upload, parsed locally)
- Pasted the extracted hash into the **Password Cracker** tool
- Ran the built-in wordlist (100 passwords) against the hash
- Tool hashed each candidate password and compared it against the target hash until a match was found
- Password recovered: cracked successfully and used to unlock the PDF

**Tools used:** [networkwalks.com/hash-calculator](https://networkwalks.com/hash-calculator/), [networkwalks.com/password-cracker](https://networkwalks.com/password-cracker/)

## 🔑 Key Concepts

- How PDF encryption hashes are structured and extracted
- Dictionary attacks vs. brute-force attacks
- Why weak/common passwords (e.g., from top-100 password lists) are cracked almost instantly
- Comparing a production-grade tool (John the Ripper) with a lightweight educational equivalent

## 🎯 Outcome

Both methods successfully cracked the target PDF password, reinforcing the importance of strong, unique passphrases and proper password hygiene.

## 📸 Screenshots

**Johnny settings — pointing to the John the Ripper executable**
![Johnny settings](screenshots/01-johnny-settings.png)

**Johnny — hash cracked, 100% complete (1/1)**
![Johnny cracked](screenshots/02-johnny-cracked.png)

**Captured flag #1 — "My Locked PDF1.pdf" unlocked**
![Flag 1](screenshots/03-flag-pdf1.png)

**Captured flag #2 — "My Locked PDF3.pdf" unlocked**
![Flag 2](screenshots/04-flag-pdf3.png)

**Networkwalks Hash Calculator — crackable `$pdf$` hash extracted locally**
![Hash calculator](screenshots/05-hash-calculator.png)

**Networkwalks Password Cracker — hash loaded, ready to run**
![Password cracker ready](screenshots/06-password-cracker-ready.png)

**Networkwalks Password Cracker — password cracked successfully (`password1`)**
![Password cracker success](screenshots/07-password-cracker-success.png)

> Create a `screenshots/` folder in the repo root and upload the 7 PNGs with the exact filenames above so the images render correctly.

## 🙏 Acknowledgements

- **Instructor:** Karim Wakas, CCE — for guidance throughout the internship
- **Networkwalks Academy** — for sponsoring the internship and providing the lab tools

---

*Part of an ongoing Cybersecurity & Ethical Hacking internship series. More modules to follow.*
