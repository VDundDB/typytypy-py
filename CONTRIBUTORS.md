# Contributors

This document identifies contributors to **TypyTypy@[typytypy-py](https://github.com/VDundDB/typytypy-py)**, their KitschCode Identities (KI), and provides cryptographic verification information for releases.

---

## Table of Contents

- [About KitschCode Identities (KI)](#about-kitschcode-identities-ki)
- [Understanding Contributor Profiles](#understanding-contributor-profiles)
- [How to Verify Releases](#how-to-verify-releases)
- [Active Contributors](#active-contributors)
- [Retired Contributors](#retired-contributors)
- [About This Document](#about-this-document)

---

## About KitschCode Identities (KI)

Contributors to the [KitschCode](https://github.com/VDundDB/KitschCode) project are provided with *voluntary* **titled identities** (KitscherEins, KitscherZwei, etc.) to represent themselves. Knows as KitschCode Identities (KI), they serve as an artistic statement about authorship and craft, in line with the project's ethos. These titles may be retired, reassigned (exchanged), or expired over time and care must be taken to verify their validity.

### Key Principles

- **Project-Specific:** Each KitschCode project maintains its own CONTRIBUTORS.md
- **Voluntary Titles:** Contributors may adopt, exchange, or retire KI titles (community-decision) over time
- **Transparent Mapping:** This file maps KI to verified GitHub identities
- **Verifiable Provenance:** All releases are cryptographically signed

> [!NOTE]
> Not all KitschCode contributors work on all projects. *This file* documents *only* those who contribute to **TypyTypy@[typytypy-py](https://github.com/VDundDB/typytypy-py)**.

---

## Understanding Contributor Profiles

Each contributor profile includes:

| Field | Purpose |
|-------|---------|
| **KitschCode Identity (KI)** | *(e.g., KitscherEins)* |
| **GitHub Identity** | *Name associated with GitHub account* |
| **GitHub Handle** | *@username for commits and issues* |
| **Role** | *Contribution focus (Author, Maintainer, etc.)* |
| **Active Since** | *Month/year of first contribution* |
| **GPG Key ID** | *Short identifier for signing key* |
| **Full Fingerprint** | *Complete key fingerprint for verification* |
| **Key Type** | *Cryptographic algorithm (e.g., EdDSA)* |
| **Associated Email** | *Email tied to the key* |

---

## How to Verify Releases

### Quick Verification

To verify a release signature:

```bash
# 1. Import the contributor's public key (first time only)
gpg --keyserver keyserver.ubuntu.com --recv-keys <KEY_ID>

# 2. Verify the signature against the release file
gpg --verify <filename>.asc <filename>
```

Expected output:
`gpg: Good signature from "Name <email>"`

> [!IMPORTANT]
> Replace `<KEY_ID>` with the contributor's key ID from their profile below.

---

### Advanced Verification

#### Verify Key Fingerprint

To ensure you have the correct public key, verify the fingerprint matches:

```bash
# Display fingerprint of imported key
gpg --fingerprint <KEY_ID>
```

Compare output with the "Full Fingerprint" listed in the contributor profile.

> [!IMPORTANT]
> Match **all 40 hexadecimal characters** of the fingerprint.

#### Derive Fingerprint from Public Key (Manual Verification)

For maximum security, independently derive the fingerprint:

1. **Download the public key** from GitHub Gist or keyserver
2. **Import locally:**

```bash
gpg --import typytypy-signing-key.asc
```

3. **Extract fingerprint:**

```bash
gpg --fingerprint <KEY_ID>
```

4. **Cross-reference** with this document

**Tool Option:** Use [CyberChef](https://gchq.github.io/CyberChef/) to hash the public key:

- Recipe: `From Base64` → `SHA-1`
- Compare the SHA-1 hash with the last 40 characters of the fingerprint

---

### What to Verify

For each GitHub Release:

- ✅ `.whl` file signature: `typytypy-X.Y.Z-py3-none-any.whl.asc`
- ✅ `.tar.gz` file signature: `typytypy-X.Y.Z.tar.gz.asc`
- ✅ Signature matches a key listed in this document
- ✅ Fingerprint matches exactly

**Note:** [PyPI](https://pypi.org/project/typytypy) does not display or verify signatures, but all release files on GitHub include `.asc` signature files.

---

## Active Contributors

### KitscherEins

**GitHub Identity:** Vabian Doerner  
**GitHub:** [@VDundDB](https://github.com/VDundDB)  
**Role:** Primary Author & Maintainer  
**Active Since:** October 2025  

**GPG Key Verification:**

| Field | Value |
|-------|-------|
| **Key ID** | `8CF960B174A35AB6` |
| **Full Fingerprint** | `AC07 8A7A 6EB0 F010 3D5F  3A93 8CF9 60B1 74A3 5AB6` |
| **Key Type** | EdDSA (Curve 25519) |
| **Associated Email** | `224838908+VDundDB@users.noreply.github.com` |

**Public Key Locations:**

- **GitHub Gist:** [View Public Key](https://gist.github.com/VDundDB/c97572da6e7586510e70edf7e2770727)
- **Keyserver:** `keyserver.ubuntu.com`

---

## Retired Contributors

*(None yet — this section will document retired {out of respect} KI titles in future)*

---

## About This Document

### Purpose

This file is part of KitschCode's commitment to **transparent authorship** and **verifiable provenance**.

It provides:

- **Identity mapping** between KI and GitHub contributors
- **Cryptographic verification reference** for release signatures
- **Trust anchor** for users and package maintainers

### Scope

This document applies *only* to **TypyTypy@[typytypy-py](https://github.com/VDundDB/typytypy-py)**. Other KitschCode projects maintain their own CONTRIBUTORS.md files.

### Updates

It will be updated as:

- New contributors join (assigned KIs)
- Keys are rotated, revoked, or expired
- Contributors retire or change roles
- KIs are retired or reassigned

---

**Last Updated:** 2025-10-15  
**Document Version:** 1.0
