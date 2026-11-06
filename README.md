<div align="center">

# 🔒 Password Security Toolkit

**A password strength analyzer and weak-password wordlist generator, built for cybersecurity education.**
Pure Python, no third-party libraries required.

![Python](https://img.shields.io/badge/Python-3.9%2B-3776AB?logo=python&logoColor=white)
![License](https://img.shields.io/badge/purpose-educational-yellow)

</div>

---

## ⚠️ Ethical use disclaimer

This project is for **learning about password security and authorized security testing only**.

- Do **not** use the wordlist generator to target a real person's accounts, including your own friends, family, or coworkers, without their explicit, informed consent.
- Unauthorized access to any system or account is illegal in most countries, even when the password is guessed rather than stolen.
- The included `sample_wordlist.txt` is generated from a **placeholder identity** (`user`, `2000`, `demo`) purely to demonstrate the kind of weak, predictable passwords people create from personal details. It contains no real person's information.

## ✨ Features

### Password Strength Analyzer
- Scores a password out of 6 based on length, character variety, common-password matches, predictable patterns (sequential letters/numbers, repeated characters) and dictionary-word detection
- Gives a WEAK / MEDIUM / STRONG verdict with human-readable feedback
- Suggests concrete improvements for weak or medium passwords

### Wordlist Generator
- Builds a list of likely weak passwords from a name, birth year and custom keywords — the same logic attackers use for dictionary/credential-stuffing attacks, so you can see how guessable name+birthdate passwords really are
- Adds common suffixes/prefixes (`123`, `!`, `@`, year), capitalisation variants and leet-speak substitutions (`a`→`4`, `e`→`3`, etc.)
- Lets you save the generated list to a text file

### Security Tips
- Built-in menu option with practical guidance: length, complexity, common mistakes, passphrases, 2FA, password managers

## 🚀 Run it

```bash
git clone https://github.com/divv29/Password_Security_Toolkit.git
cd Password_Security_Toolkit
python3 password_analyzer.py
```

No dependencies to install — it only uses Python's standard library.

### Menu options

```
1. Analyze Password Strength     — type any password, get a full breakdown
2. Generate Custom Wordlist      — demo with a placeholder name/year, not a real identity
3. Security Tips                 — read best practices
4. Exit
```

## 🗂 Project structure

```
Password_Security_Toolkit/
├── password_analyzer.py    # analyzer + generator + CLI menu
├── sample_wordlist.txt     # example output, built from a placeholder identity only
├── .gitignore
└── README.md
```

## 🧮 How scoring works

| Factor | Points |
|---|---|
| Length ≥ 12 | +3 |
| Length 8–11 | +2 |
| Length 6–7 | +1 |
| Length < 6 | +0 |
| 4 character types (upper/lower/digit/symbol) | +3 |
| 3 character types | +2 |
| 2 character types | +1 |
| 1 character type | +0 |
| Matches a common password | −2 |
| Contains a predictable pattern (e.g. `123`, `abc`, repeated chars) | −1 |
| Looks like a plain dictionary word | −1 |

**Strength:** `≤1` → WEAK, `2–3` → MEDIUM, `4+` → STRONG.

## 🎓 Why this project exists

Most real-world weak passwords aren't random — they're built from a name, a birth year, and a predictable suffix like `123!`. This toolkit demonstrates exactly how guessable that pattern is, so the takeaway is: **never use personal details as the base of your password**, and prefer a long, random passphrase or a password manager instead.

## 📄 License

No license file is included; all rights are reserved by the author. Ask before reusing this code.

---

<div align="center">
Made by <a href="https://github.com/divv29">@divv29</a> for educational purposes · Stay secure 🔐
</div>
