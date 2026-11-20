# 🔐 PDF Password Cracking — Dictionary Attack Lab

**Week 3 project — Cybersecurity & Ethical Hacking Internship @ Networkwalks Academy**

This repository walks through two different methods of recovering a password from an encrypted PDF file: a dedicated offline cracking tool (John the Ripper) and a lightweight browser-based tool that mirrors the same underlying logic. The objective was to understand how password hashes are extracted and cracked, and to compare a professional-grade tool against a simplified educational one.

---

## 🗂️ Project Structure

```
.
├── README.md
└── screenshots/
    ├── 01-johnny-settings.png
    ├── 02-johnny-cracked.png
    ├── 03-flag-pdf1.png
    ├── 04-flag-pdf3.png
    ├── 05-hash-calculator.png
    ├── 06-password-cracker-ready.png
    └── 07-password-cracker-success.png
```

---

## 🧩 Module 1 — John the Ripper & Johnny (GUI)

1. Extracted the password hash from an encrypted PDF into `pdf2john`/hashcat-compatible format (`$pdf$...`)
2. Pointed **Johnny** (the GUI front-end for John the Ripper) to the John executable
3. Loaded the hash and ran a dictionary/wordlist attack
4. Password recovered and the PDF successfully unlocked

**Tools:** John the Ripper (jumbo build), Johnny GUI

![Johnny settings](screenshots/01-johnny-settings.png)
*Johnny → Settings, pointing to `john.exe` (John the Ripper 1.9.0-jumbo-1 OMP detected).*

![Johnny cracked](screenshots/02-johnny-cracked.png)
*Johnny → Passwords: hash cracked, password recovered as `good-luck` — 100% (1/1 cracked, 0 left), format = PDF.*

![Flag 1](screenshots/03-flag-pdf1.png)
*"My Locked PDF1.pdf" opened — Flag 1: `nw{cybersecurity_flag_captured_2608}`.*

![Flag 2](screenshots/04-flag-pdf3.png)
*"My Locked PDF3.pdf" opened — Flag: `nw{networkwalks_flag_260821_1}`.*

---

## 🧩 Module 2 — Networkwalks Hash Calculator & Password Cracker

1. Uploaded the encrypted PDF to the **Hash Calculator** (parsed entirely client-side — nothing is uploaded to a server) to extract the crackable `$pdf$` hash
2. Pasted the hash into the **Password Cracker** tool
3. Ran the built-in 100-word list against it
4. Each candidate word was hashed and compared to the target hash until a match was found

**Tools:** [Hash Calculator](https://networkwalks.com/hash-calculator/) · [Password Cracker](https://networkwalks.com/password-cracker/)

![Hash calculator](screenshots/05-hash-calculator.png)
*Hash Calculator → PDF tab: "My Locked PDF1.pdf" (266.9 KB) parsed locally, `$pdf$` hash extracted.*

![Password cracker ready](screenshots/06-password-cracker-ready.png)
*Password Cracker: extracted hash pasted in, built-in list (100 passwords) active, ready to run.*

![Password cracker success](screenshots/07-password-cracker-success.png)
*Attack finished (91/100 tried, 91%) — match found: password recovered as `password1`.*

---

## 🔑 Key Takeaways

- How a PDF's encryption hash is structured and how it's extracted for cracking
- The difference between dictionary attacks and brute-force attacks
- How quickly weak/common passwords (e.g. top-100 lists) fall to a basic dictionary attack
- How a production tool like John the Ripper compares to a simplified educational equivalent built around the same principle

## 🎯 Outcome

Both approaches successfully recovered the target password, reinforcing why long, unique passphrases (not dictionary words or common patterns) are essential for protecting sensitive files.

## 🙏 Acknowledgements

- **Instructor:** Karim Wakas, CCE — for guidance throughout the internship
- **Networkwalks Academy** — for sponsoring the internship and providing the lab environment and tools

---

*Part of an ongoing Cybersecurity & Ethical Hacking internship series. More modules to follow.*
