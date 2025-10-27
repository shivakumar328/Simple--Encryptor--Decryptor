# 🔐 Enhanced Secure Encryptor v3.0

[](https://www.java.com)
[](https://en.wikipedia.org/wiki/Galois/Counter_Mode)
[](https://opensource.org/licenses/MIT)

Ever wanted a single, powerful tool to lock down your files, text, and even your clipboard? Meet the **Enhanced Secure Encryptor**—a command-line Swiss Army knife for your personal security.

This isn't just a simple encryptor. It's a full-featured security suite built in Java, using modern, authenticated **AES-256-GCM** encryption. It’s designed to be robust, user-friendly, and packed with utilities to cover all your encryption needs.

-----

## 🚀 Your Security Dashboard

When you run the application, you're greeted with a comprehensive menu. This is your central hub for every security operation.

```text
🔐 Enhanced Secure Encryptor v3.0
═══════════════════════════════════════════

╔════════════════════════════════════════════╗
║     Secure Encryptor (AES-256-GCM)       ║
╚════════════════════════════════════════════╝

ENCRYPTION/DECRYPTION:
1.  📝 Encrypt Text           2.  🔓 Decrypt Text
3.  📁 Encrypt File           4.  📂 Decrypt File
5.  📦 Batch Encrypt          6.  📚 Encrypt Directory

ADVANCED FEATURES:
7.  🎲 Generate Password      8.  📊 Check Strength
9.  🔐 Create Key File        10. 🗝️  Encrypt w/ Key File
11. 🗑️  Secure Delete (Shred)  12. 📋 Clipboard Encrypt/Decrypt
13. 🤐 Create Encrypted Archive 14. 📖 Extract Encrypted Archive

UTILITIES & AUDIT:
15. 🔐 Set Security Profile    16. 📦 Backup Manager
17. 🔎 Compare Files (Hash)    18. ✓ File Integrity Check
19. 📜 View Audit Log         20. ⚙️  Settings
21. 🚪 Exit

➤ Enter your choice:
```

-----

## ✨ Features at a Glance

This tool is more than just one thing. It's a...

| Feature | Description |
| :--- | :--- |
| 📝 **Text Encryptor** | Quickly encrypt and decrypt snippets of text or messages. |
| 📁 **File/Directory Encryptor** | Encrypt single files, batch-process multiple files, or encrypt entire directories recursively. |
| 🤐 **Encrypted Archives** | Bundle multiple files into a single, encrypted `.enca` archive. |
| 🔑 **Two-Factor Encryption** | Go beyond passwords. Generate a **Key File** to use alongside your password for two-factor protection. |
| 🗑️ **Secure Shredder** | Securely delete original files by overwriting them with random data multiple times before deletion. |
| 🎯 **Security Profiles** | Choose your security level: **Fast** (quick), **Balanced** (default), or **Paranoid** (max iterations). |
| 🎲 **Password Toolkit** | Generate cryptographically secure passwords and check the strength of existing ones. |
| 📋 **Clipboard Manager** | Encrypt text *from* your clipboard and copy the result back. Decrypt clipboard content just as easily. |
| 🔎 **Integrity Checker** | Verify file integrity by generating and comparing **SHA-256** hashes. |
| 📦 **Backup System** | Automatically or manually create backups of your encrypted files before performing operations. |
| 📜 **Audit Logger** | Keeps a `crypto_audit.log` of all successful operations and errors for your review. |
| ⚙️ **Config Manager** | Remembers your settings, like default compression or auto-backup preferences. |

-----

## ⚙️ Under the Hood: The Core Tech

We don't roll our own crypto. This tool is built on trusted, industry-standard Java Cryptography:

  * **Encryption Algorithm:** **AES/GCM/NoPadding** (AES-256). GCM provides authenticated encryption (AEAD), which means it encrypts your data and simultaneously verifies its integrity. This protects against tampering.
  * **Key Derivation:** **PBKDF2WithHmacSHA256**. Your password isn't used directly as the key. It's "stretched" using 65,536 iterations (or more\!) to make it resistant to brute-force attacks.
  * **Secure Randomness:** `SecureRandom` is used to generate a unique cryptographic **salt** and **IV** (Initialization Vector) for *every single encryption*. This ensures that encrypting the same file twice with the same password produces two completely different outputs.
  * **Compression:** Uses **GZIP** to compress files before encryption, saving space (especially on text-based files).

-----

## 📖 How to Use

### 1\. How to Compile & Run

You'll need the Java JDK (version 17+ recommended) installed.

```bash
# 1. Compile all the .java files
javac *.java

# 2. Run the main application
java EnhancedSecureEncryptor
```

### 2\. Your First 60 Seconds: Encrypting a File 🚀

Let's do a quick-start guide.

1.  Run `java EnhancedSecureEncryptor`.
2.  Select `3` (Encrypt File).
3.  **Enter input file path:** `my_secrets.txt`
4.  **Enter output file path:** (Press Enter to use the default: `my_secrets.txt.enc`)
5.  **Enable compression? (y/n):** `y`
6.  **Enter password:** `[your_super_strong_password]`
7.  **Confirm password:** `[your_super_strong_password]`
8.  The app will show you the strength (e.g., `💚 Password Strength: VERY_STRONG`) and then encrypt the file.
9.  **Securely delete original? (y/n):** `y`

**Done\!** Your original file is now securely shredded, and `my_secrets.txt.enc` is all that remains.

To get it back, just choose option `4` (Decrypt File) and use the same password.

-----

## 🔒 A Deep Dive: Must-Know Features

### The "Paranoid" Profile (Option 15)

By default, the app is in **Balanced** mode. But if you're protecting critical data, you can enable a profile:

  * **Fast:** Lower iterations, no compression. Quick for large files.
  * **Balanced:** (Default) 65,536 iterations, compression on. Great for most uses.
  * **Paranoid:** 200,000+ iterations, compression on, and defaults shredding to 7 passes. This will be slower, but it's *significantly* more resistant to offline brute-force attacks.

### Two-Factor Security: Key Files (Option 9 & 10)

This is one of the most powerful features. A password can be guessed. A password *and* a file you hold is much, much harder to break.

**How it works:**

1.  **First, create a key file:** Choose option `9`. It will generate a file (e.g., `my.key`) filled with secure random data. **Guard this file like a password\!**
2.  **Then, encrypt:** Choose option `10`. The app will ask for your **password** *and* the **path to your key file**.
3.  It combines your password and the key file's data to create the *real* encryption key.
4.  To decrypt, you **must** provide the *same password* AND the *same key file*.

> ⚠️ **A CRITICAL WARNING**
>
> This tool is secure. That means it's also unforgiving.
>
> **IF YOU FORGET YOUR PASSWORD, YOUR DATA IS GONE FOREVER.**
> **IF YOU USE A KEY FILE AND YOU LOSE IT, YOUR DATA IS GONE FOREVER.**
>
> There is no "forgot password" link. There is no backdoor. The encryption is absolute. Please, back up your passwords and key files in a secure location (like a password manager).
