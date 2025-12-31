# My Custom Nuclei Templates

A collection of custom, enhanced, and heavy fuzzing templates for Nuclei.

## Templates

### 1. Blind XSS Enhanced Pro (`blind-xss-ajvadn.yaml`)
A comprehensive Blind XSS template that targets both **Query Parameters** and **HTTP Headers** (User-Agent, Referer, X-Forwarded-For).
- **Features:**
  - Uses `xss.report` and `interactsh` for OOB detection.
  - Includes polyglots and context breakers.
  - Fuzzes headers to catch blind XSS in logging systems and admin panels.

### 2. Heavy Fuzzing Suite (`fuzzing-templates/`)
A set of aggressive fuzzing templates designed for deep testing.
- `heavy-sqli.yaml`: Massive SQL Injection payload list.
- `heavy-xss.yaml`: Comprehensive XSS payloads.
- `heavy-ssti.yaml`: Server-Side Template Injection.
- `heavy-lfi.yaml`: Local File Inclusion.
- `heavy-403-url.yaml`: 403 Bypass techniques.
- And more (Springboot, API Discovery, etc.)

## Usage

### Prerequisites
- [Nuclei](https://github.com/projectdiscovery/nuclei) installed.

### Running Blind XSS
```bash
nuclei -u "http://target.com" -t blind-xss-ajvadn.yaml
```

### Running Heavy Fuzzing Templates
> [!IMPORTANT]
> **To run the fuzzing templates, you MUST run them from within the `fuzzing-templates` directory.**
> These templates use large external payload files located in the `payloads/` directory. Running them from the root may cause payload resolution errors.

**Correct Usage:**
```bash
cd fuzzing-templates
nuclei -u "http://target.com" -t heavy-sqli.yaml
```

**Alternative (Absolute Path):**
You can also update the templates to use absolute paths if you prefer running from root.

---
*Happy Hacking!*
