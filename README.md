# Enhanced Secure Encryptor v3.0 🔐

```
  ███████╗███╗   ██╗ ██████╗██████╗ ██╗   ██╗██████╗ ████████╗ ██████╗ ██████╗ 
  ██╔════╝████╗  ██║██╔════╝██╔══██╗╚██╗ ██╔╝██╔══██╗╚══██╔══╝██╔═══██╗██╔══██╗
  █████╗  ██╔██╗ ██║██║     ██████╔╝ ╚████╔╝ ██████╔╝   ██║   ██║   ██║██████╔╝
  ██╔══╝  ██║╚██╗██║██║     ██╔══██╗  ╚██╔╝  ██╔═══╝    ██║   ██║   ██║██╔══██╗
  ███████╗██║ ╚████║╚██████╗██║  ██║   ██║   ██║        ██║   ╚██████╔╝██║  ██║
  ╚══════╝╚═╝  ╚═══╝ ╚═════╝╚═╝  ╚═╝   ╚═╝   ╚═╝        ╚═╝    ╚═════╝ ╚═╝  ╚═╝
```

[![Java Version](https://img.shields.io/badge/Java-17%2B-orange)](https://www.oracle.com/java/)
[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Security](https://img.shields.io/badge/Security-AES--256--GCM-green)](https://en.wikipedia.org/wiki/Galois/Counter_Mode)
[![Status](https://img.shields.io/badge/Status-Active-success)](https://github.com/yourusername/enhanced-secure-encryptor)

A robust Java-based encryption utility that provides secure file and text encryption using AES-256-GCM with advanced features for data protection and security management.

> 🔐 **Quick Start**: Jump to [Installation](#installation) to get started in less than 2 minutes!

<details>
<summary>🎯 Why Choose Enhanced Secure Encryptor?</summary>

- Military-grade AES-256-GCM encryption
- User-friendly interface with emoji indicators
- Comprehensive security features
- Active development and support
- Regular security updates
</details>

## Features

### Core Encryption Features
- 🔒 AES-256-GCM encryption with PBKDF2 key derivation
- 📝 Text encryption and decryption
- 📁 File encryption with compression support
- 📦 Directory and batch encryption
- 🗄️ Encrypted archive creation and extraction

### Security Features

<details>
<summary><b>🛡️ Core Security Features</b></summary>

| Feature | Description | Security Level |
|---------|-------------|----------------|
| 🔑 Key Files | Two-factor encryption support | Very High |
| 🎲 Password Gen | Cryptographic random generation | High |
| 💪 Strength Check | Real-time password analysis | Medium |
| 🗑️ Secure Delete | DOD-compliant shredding | Very High |
| ✓ Integrity | SHA-256 verification | High |

```
Password Strength Indicators:
🔴 Weak   : < 8 chars
🟡 Medium : 8-11 chars + mixed
🟢 Strong : 12-15 chars + mixed + symbols
💚 V.Strong: 16+ chars + all types
```
</details>

### Advanced Features
- 📋 Clipboard encryption
- 📜 Audit logging
- 💾 Automated backup management
- 📊 File comparison tools
- 🎯 Configurable security profiles

## Requirements
- Java 17 or higher
- Terminal/Console with Unicode support

## Installation
1. Compile the Java source file:
```bash
javac EnhancedSecureEncryptor.java
```

2. Run the program:
```bash
java EnhancedSecureEncryptor
```

## Usage 🚀

<details open>
<summary><b>📖 Interactive Guide</b></summary>

### Quick Command Reference
```bash
# Start the encryptor
java EnhancedSecureEncryptor

# Compile with debug information
javac -g EnhancedSecureEncryptor.java

# Run with increased memory
java -Xmx2g EnhancedSecureEncryptor
```

### Basic Operations

<details>
<summary><b>1. 📝 Text Encryption</b></summary>

```
Main Menu > Option 1
╔════════════════════════════════╗
║ Enter text: Hello, World!      ║
║ Password: ***********          ║
╚════════════════════════════════╝
✓ Text encrypted successfully!
```

**Example Output:**
```
Encrypted: AES256[base64...]
Strength: 🟢 STRONG
Clipboard: Copied ✓
```
</details>

2. **File Encryption**
   - Select option 3 from the main menu
   - Specify input and output file paths
   - Choose whether to enable compression
   - Enter encryption password
   - Optionally save file metadata

### Advanced Features

1. **Key File Encryption**
   - Create a key file using option 9
   - Use option 10 to encrypt with both password and key file
   - Store the key file securely

2. **Batch Operations**
   - Use option 5 for encrypting multiple files
   - Use option 6 for encrypting entire directories
   - Create encrypted archives with option 16

3. **Security Profiles**
   - Access profiles via option 19
   - Choose between FAST, BALANCED, and PARANOID modes
   - Each profile offers different security/performance tradeoffs

## Security Considerations

- 🔐 Use strong passwords (16+ characters)
- 🔑 Keep key files separate from encrypted data
- 📦 Enable compression for sensitive data
- 💾 Regular backups are recommended
- 📝 Monitor audit logs for security

## Configuration ⚙️

<details>
<summary><b>Interactive Settings Guide</b></summary>

```
╔═══════════════════════════════════════╗
║           Settings Menu                ║
╠═══════════════════════════════════════╣
║ 1. 📁 Output Directory: /encrypted     ║
║ 2. 🗜️ Compression: ENABLED             ║
║ 3. 💾 Auto-Backup: ON                  ║
║ 4. 🛡️ Security Profile: BALANCED       ║
╚═══════════════════════════════════════╝
```

### Quick Settings Guide

| Setting | Command | Description |
|---------|---------|-------------|
| Output Dir | Option 14 > 1 | Set default save location |
| Compression | Option 14 > 2 | Toggle file compression |
| Auto-Backup | Option 14 > 3 | Enable automatic backups |
| Security | Option 14 > 4 | Adjust security levels |

</details>

## Backup Management

- Automatic backups before decryption (configurable)
- Manual backup creation
- Backup restoration
- Password attempt history

## File Integrity

- SHA-256 hash verification
- File comparison tools
- Metadata preservation
- Secure deletion with multiple passes

## Contributing

Feel free to submit issues and enhancement requests!

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Security Notice

⚠️ This encryption tool uses strong cryptographic methods, but security depends on:
- Password strength
- Secure key file storage
- Physical system security
- Proper operational security practices

## Support & Troubleshooting 🛟

<details>
<summary><b>Common Issues & Solutions</b></summary>

### 1. Encryption Fails
```
Error: Unable to encrypt file
┌─────────────────────────┐
│ ✓ Check file permissions│
│ ✓ Verify available space│
│ ✓ Check file not in use │
└─────────────────────────┘
```

### 2. Decryption Issues
```
Error: Invalid password
┌─────────────────────────┐
│ ✓ Verify password       │
│ ✓ Check key file path   │
│ ✓ Verify file integrity │
└─────────────────────────┘
```

### Quick Diagnostic Commands
```bash
# Check Java version
java -version

# Verify file permissions
dir EnhancedSecureEncryptor.java

# View last audit log
type crypto_audit.log
```

### Need More Help?
- 📝 Check audit logs: `Option 13`
- 🔍 Verify file integrity: `Option 15`
- 🔐 Review security settings: `Option 14`
- 💡 Generate debug info: `Option 14 > View current settings`

</details>
