# 🔐 APK Secret Scanner

A Python-based utility to detect hardcoded secrets, tokens, and sensitive data inside Android APKs or extracted directories. It performs deep scanning on both text and binary files and generates a categorized, styled HTML report.

---

## 🚀 Features

- 📦 Scan both APK files and extracted directories
- 🔍 Detects:
  - Google/Firebase API keys
  - AWS keys and secrets
  - JWTs, Stripe keys, Slack tokens
  - Usernames, passwords, generic API keys
- 🧠 Base64 string decoding with UI false positive filtering
- ⚠️ Sensitive file extension detection (`.pem`, `.key`, `.crt`, etc.)
- 🛡️ Obfuscation hints detection (Proguard, R8, etc.)
- 📁 Skips known non-sensitive files like images, fonts, stylesheets
- 🧾 Extracts printable strings from binary files
- 📊 Generates a fully categorized, dark-themed, mobile-friendly HTML report:
  - Secret matches (grouped)
  - Base64 values with decoded preview
  - Binary findings
  - Obfuscation status
  - Sensitive files list

---

## 🖥️ Usage

### 🔸 Scan a direct APK file

```bash
python apk_secret_scanner.py --apk path/to/app.apk
````

### 🔸 Scan an already extracted APK directory

```bash
python apk_secret_scanner.py --dir path/to/folder
```

### 🔸 Customize output report filename

```bash
python apk_secret_scanner.py --apk app.apk --output my_scan_report.html
```

---

## 🧾 Output

* Default output: `apk_scan_report.html`
* HTML report includes:

  * Secret data grouped by category
  * Base64 decoded values table
  * Separate binary data section
  * Obfuscation flag
  * List of sensitive file types found

---

## 📦 Requirements

* Python 3.6+
* tqdm (for progress bars)

Install via pip:

```bash
pip install tqdm
```

---

## ⚠️ Limitations

* No recursive Base64 decoding (single pass only)
* Simple keyword filtering for false positives
* Slower scan on large APKs (no multi-threading yet)
* Only HTML reports (no CSV/PDF/JSON)
* No CI/CD integration by default (scriptable)

---

## 📜 License

This project is licensed under the **GNU General Public License v3.0 (GPL-3.0)**.

---

**Author**: Shyam Chauhan
**Disclaimer**: For educational and authorized security testing purposes only.
