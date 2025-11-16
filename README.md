# Bruteforce Database - Wordlists for Ethical Security Testing

[![CI](https://github.com/duyet/bruteforce-database/actions/workflows/validate.yml/badge.svg)](https://github.com/duyet/bruteforce-database/actions/workflows/validate.yml)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](./LICENSE)

A curated, community-maintained collection of wordlists for **authorized security testing**, penetration testing, and password analysis.

> **⚠️ Ethical Use Only:** These wordlists are for testing systems you own or have explicit authorization to test. See our [Code of Conduct](#ethics--responsible-use).

---

## Quick Start

```bash
# Clone the repository
git clone https://github.com/duyet/bruteforce-database.git
cd bruteforce-database

# Example: Test SSH login (authorized testing only!)
hydra -L usernames.txt -P 1000000-password-seclists.txt ssh://target.example.com

# Example: Web directory brute-forcing
gobuster dir -u https://example.com -w forced-browsing/all.txt

# Example: Subdomain enumeration
ffuf -u https://FUZZ.example.com -w subdomains-10000.txt
```

---

## What's Inside?

### 📊 Quick Stats
- **11+ million** total entries across all wordlists
- **135+ MB** of curated data
- **4 main categories**: Passwords, Usernames, Infrastructure, Identities
- **Validated & Tested** with automated CI/CD

### 🎯 Use Cases

| I need to... | Use this wordlist | Why? |
|-------------|------------------|------|
| Test common passwords | `1000000-password-seclists.txt` | Most common passwords from breach data |
| Test password policy | `8-more-passwords.txt` | Filtered for length, complexity requirements |
| Enumerate user accounts | `usernames.txt` | 400K+ common US usernames |
| Find hidden directories | `forced-browsing/all.txt` | Comprehensive web path discovery |
| Discover subdomains | `subdomains-10000.txt` | 10K most common subdomain names |
| Test against massive dataset | `2151220-passwords.txt` | 2.1M password compilation |
| Generate wordlist for JtR | `uniqpass_v16_password.txt` | Optimized for John the Ripper |
| Test keyboard patterns | `cain.txt` | Includes common patterns from Cain & Abel |

---

## Available Wordlists

### 🔑 Password Dictionaries

#### General Purpose
- **`1000000-password-seclists.txt`** (1M entries, 8.5 MB)
  - Source: [SecLists](https://github.com/danielmiessler/SecLists) project
  - Best for: Initial password testing, most common passwords
  - Quality: ⭐⭐⭐⭐⭐ Industry standard

- **`2151220-passwords.txt`** (2.1M entries, 20 MB)
  - Source: Dazzlepod.com compilation
  - Best for: Comprehensive password testing
  - Quality: ⭐⭐⭐⭐ Large, diverse dataset

#### Filtered Sets
- **`8-more-passwords.txt`** (62K entries, 629 KB)
  - Filters: 8+ chars, requires caps + numbers, no consecutive chars
  - Best for: Testing password policies with complexity requirements
  - Quality: ⭐⭐⭐⭐ Targeted for modern policies

- **`7-more-passwords.txt`** (528K entries, 5 MB)
  - Filters: 7+ chars, numeric-only removed
  - Best for: Medium-complexity password policies
  - Quality: ⭐⭐⭐ Good middle ground

#### Specialized
- **`cain.txt`** (307K entries, 2.5 MB)
  - Source: Cain & Abel password cracker
  - Best for: Classic patterns, keyboard walks, common substitutions
  - Quality: ⭐⭐⭐⭐ Time-tested patterns

- **`bitcoin-brainwallet.lst`** (395K entries, 3.4 MB)
  - Source: Dictionary words used for Bitcoin brainwallets
  - Best for: Passphrase testing, dictionary attack foundations
  - Quality: ⭐⭐⭐ Unique use case

- **`38650-password-sktorrent.txt`** (39K entries, 309 KB)
  - Source: SKTorrent.eu leaked database
  - Best for: Real-world password patterns
  - Quality: ⭐⭐⭐ Historical reference

#### Tool-Specific
- **`uniqpass_v16_password.txt`** (2.1M entries, 20 MB)
  - Optimized for: [John the Ripper](https://www.openwall.com/john/) wordlist mode
  - Best for: Hash cracking with JtR
  - Quality: ⭐⭐⭐⭐ JtR optimized

### 👤 Usernames & Identities

- **`usernames.txt`** (403K entries, 3.3 MB)
  - Source: US username compilation
  - Best for: Account enumeration, user testing
  - Quality: ⭐⭐⭐⭐ Comprehensive US usernames

- **`38650-username-sktorrent.txt`** (39K entries, 258 KB)
  - Source: SKTorrent.eu leaked database
  - Best for: Real-world username patterns
  - Quality: ⭐⭐⭐ Historical reference

- **`facebook-firstnames.txt`** (4.3M entries, 37 MB)
  - Source: Facebook public first names
  - Best for: Name-based password testing, identity research
  - Quality: ⭐⭐⭐⭐⭐ Massive, real-world dataset

### 🌍 Geographic Data

- **`us-cities.txt`** (21K entries, 199 KB)
  - All US cities
  - Best for: Location-based password testing
  - Quality: ⭐⭐⭐⭐ Complete US coverage

- **`indo-cities.txt`** (102 entries, 1.2 KB)
  - Indonesian cities
  - Best for: Regional password testing
  - Quality: ⭐⭐⭐ Regional coverage

### 🌐 Infrastructure Testing

- **`subdomains-10000.txt`** (10K entries, 97 KB)
  - Most common subdomain names
  - Best for: Subdomain enumeration, DNS reconnaissance
  - Quality: ⭐⭐⭐⭐ Essential for recon
  - Tools: [Sublist3r](https://github.com/aboul3la/Sublist3r), [ffuf](https://github.com/ffuf/ffuf), [gobuster](https://github.com/OJ/gobuster)

### 📁 Forced Browsing / Directory Discovery

**`forced-browsing/`** directory contains specialized wordlists for web application testing:

- **`all.txt`** (43K entries) - Comprehensive file/directory list
- **`all-extensionless.txt`** (25K entries) - Paths without file extensions
- **`all-dirs.txt`** - Directory names only

#### Categorized by File Type

**`forced-browsing/cat/`** - Organized by file category:
- `Conf/` - Configuration files (`.conf`, `.config`, `.htaccess`, `.properties`)
- `Database/` - Database files (`.sql`, `.mdb`, `.xml`, `.ini`)
- `Language/` - Source code files (`.php`, `.asp`, `.jsp`, `.java`)
- `Project/` - Project files (`.csproj`, `.pdb`, `.sln`)

#### Context-Based Paths

**`forced-browsing/context/`** - Organized by context:
- `admin.txt` - Admin panels and interfaces
- `test.txt` - Test environments and files
- `debug.txt` - Debug endpoints
- `error.txt` - Error pages and handlers
- `help.txt` - Help and documentation paths
- Plus many more specialized contexts

**Usage Example:**
```bash
# Scan for admin panels
gobuster dir -u https://target.com -w forced-browsing/context/admin.txt

# Look for config files
ffuf -u https://target.com/FUZZ -w forced-browsing/cat/Conf/conf.txt

# Comprehensive directory scan
dirsearch -u https://target.com -w forced-browsing/all.txt
```

---

## Usage Examples

### Password Cracking

```bash
# John the Ripper
john --wordlist=2151220-passwords.txt hashes.txt

# Hashcat (MD5)
hashcat -m 0 -a 0 hashes.txt 1000000-password-seclists.txt

# Hydra (SSH brute force)
hydra -l admin -P 8-more-passwords.txt ssh://192.168.1.100
```

### Web Application Testing

```bash
# Directory discovery with gobuster
gobuster dir -u https://example.com -w forced-browsing/all.txt -t 50

# File discovery with specific extensions
gobuster dir -u https://example.com -w forced-browsing/all-extensionless.txt -x php,html,txt

# Fast fuzzing with ffuf
ffuf -u https://example.com/FUZZ -w forced-browsing/context/admin.txt -mc 200,301,302
```

### Subdomain Enumeration

```bash
# Sublist3r
sublist3r -d example.com -w subdomains-10000.txt

# ffuf for subdomain fuzzing
ffuf -u https://FUZZ.example.com -w subdomains-10000.txt -mc 200

# gobuster DNS mode
gobuster dns -d example.com -w subdomains-10000.txt
```

### Account Enumeration

```bash
# Test for valid usernames (authorized only!)
./enum4linux -U target.com -w usernames.txt

# Check username availability
curl https://api.example.com/check-username -d "username=FUZZ" -w usernames.txt
```

---

## Decision Guide: Which Wordlist?

### For Password Testing

**Quick test (< 1 minute):**
- Use `8-more-passwords.txt` (62K entries)
- Fast, focuses on complex passwords

**Standard test (5-10 minutes):**
- Use `1000000-password-seclists.txt` (1M entries)
- Industry standard, best coverage-to-time ratio

**Comprehensive test (30+ minutes):**
- Use `2151220-passwords.txt` (2.1M entries)
- Maximum coverage

**Policy-specific testing:**
- Strong policy (8+ chars, complexity): `8-more-passwords.txt`
- Medium policy (7+ chars): `7-more-passwords.txt`
- Weak/no policy: `1000000-password-seclists.txt`

### For Web Testing

**Quick scan:**
- `forced-browsing/context/<specific>.txt` (targeted)

**Standard scan:**
- `forced-browsing/all-dirs.txt` (directories only)

**Comprehensive scan:**
- `forced-browsing/all.txt` (everything)

**File-specific:**
- `forced-browsing/cat/<type>/` (by file extension)

---

## Tools That Work With These Wordlists

### Password Cracking
- [John the Ripper](https://www.openwall.com/john/) - Password cracking
- [Hashcat](https://hashcat.net/hashcat/) - Advanced password recovery
- [Hydra](https://github.com/vanhauser-thc/thc-hydra) - Network login cracker

### Web Testing
- [Gobuster](https://github.com/OJ/gobuster) - Directory/file & DNS busting
- [ffuf](https://github.com/ffuf/ffuf) - Fast web fuzzer
- [Dirsearch](https://github.com/maurosoria/dirsearch) - Web path scanner
- [Burp Suite](https://portswigger.net/burp) - Web application testing

### Subdomain Discovery
- [Sublist3r](https://github.com/aboul3la/Sublist3r) - Subdomain enumeration
- [Amass](https://github.com/OWASP/Amass) - Network mapping

---

## Automation & Quality

This repository includes intelligent automation:

### Validation Tools

```bash
# Validate all wordlists
python3 scripts/validate.py

# Validate specific file
python3 scripts/validate.py --file passwords.txt

# Deduplicate wordlists
python3 scripts/deduplicate.py passwords.txt

# Deduplicate all
python3 scripts/deduplicate.py --all
```

### CI/CD Pipeline

Every commit and pull request is automatically:
- ✅ Validated for encoding and format
- ✅ Checked for file corruption
- ✅ Scanned for sensitive data
- ✅ Analyzed for statistics
- ✅ Verified for integrity

See [`.github/workflows/validate.yml`](.github/workflows/validate.yml)

### Manifest

The `manifest.json` file contains metadata for every wordlist:
- Entry counts and unique entries
- File sizes and checksums
- Encoding information
- Validation status

Generated automatically on every commit.

---

## Contributing

We welcome contributions! See [CONTRIBUTING.md](./CONTRIBUTING.md) for detailed guidelines.

### Quick Contribution Checklist

- [ ] Wordlist is unique (not a duplicate)
- [ ] Source is documented
- [ ] File is UTF-8 encoded
- [ ] Deduplicated and validated
- [ ] README updated with entry
- [ ] Commit message is descriptive

### Running Validation Locally

```bash
# Before submitting PR
python3 scripts/validate.py
python3 scripts/deduplicate.py --all
```

---

## Ethics & Responsible Use

⚠️ **IMPORTANT:** These wordlists are for **authorized security testing only**.

### ✅ Acceptable Use
- Penetration testing with written authorization
- Security research on your own systems
- Educational purposes in controlled environments
- Password policy analysis and improvement
- Academic research with ethical approval

### ❌ Unacceptable Use
- Unauthorized access to any system
- Testing systems without explicit permission
- Malicious hacking or cybercrime
- Harassment or targeting individuals
- Any illegal activity under applicable laws

**By using these wordlists, you agree to use them responsibly and legally.**

See [CLAUDE.md](./CLAUDE.md) for our full philosophy on ethical use.

---

## Project Philosophy

This isn't just a collection of text files—it's a **living archive** maintained by the security community.

Read [CLAUDE.md](./CLAUDE.md) to understand our principles:
- Quality over quantity
- Ethical use only
- Full transparency
- Community first
- Evolution, not stagnation

---

## Contributors

Thank you to everyone who has contributed to this project:

- Van-Duyet Le - [**@duyet**](https://github.com/duyet) - Creator & Maintainer
- Taufiq Sumadi - [**@taufiqsumadi**](https://github.com/taufiqsumadi)
- San Sayidul Akdam Augusta - [**@sanAkdam**](https://github.com/sanAkdam)
- Dani Vijay - [**@danivijay**](https://github.com/danivijay) - Forced-browsing wordlists

Want to contribute? See [CONTRIBUTING.md](./CONTRIBUTING.md)!

---

## License

This project is licensed under the [MIT License](./LICENSE).

You are free to:
- ✅ Use for any purpose (commercial or non-commercial)
- ✅ Modify and create derivatives
- ✅ Distribute and share

Requirements:
- Include the license and copyright notice
- Use responsibly and legally

---

## Support This Project

If you find this project useful:

⭐ **Star this repository** on GitHub
🐛 **Report issues** to help us improve
💡 **Contribute** new wordlists or improvements
📢 **Share** with the security community
☕ **Sponsor** via [GitHub Sponsors](https://github.com/sponsors/duyet)

---

## Related Resources

- [SecLists](https://github.com/danielmiessler/SecLists) - Collection of security lists
- [PayloadsAllTheThings](https://github.com/swisskyrepo/PayloadsAllTheThings) - Penetration testing payloads
- [FuzzDB](https://github.com/fuzzdb-project/fuzzdb) - Attack patterns database
- [OWASP Testing Guide](https://owasp.org/www-project-web-security-testing-guide/) - Web security testing methodology

---

## Changelog

See [CHANGELOG.md](./CHANGELOG.md) for version history and updates.

---

**"Quality is not an act, it's a habit." - Aristotle**

Made with ❤️ by the security community, for the security community.
