🔐 Enhanced Secure Encryptor v3.0
A professional-grade command-line encryption tool built with Java, featuring AES-256-GCM encryption, military-grade file shredding, encrypted archives, and comprehensive security utilities.

📋 Table of Contents
Features
Security Specifications
Installation
Quick Start
Detailed Usage Guide
Security Profiles
Configuration
Best Practices
Troubleshooting
License
✨ Features
Core Encryption
Text Encryption/Decryption - Secure message encryption with Base64 output
File Encryption - Encrypt files with optional GZIP compression
Batch Processing - Encrypt multiple files simultaneously
Directory Encryption - Recursively encrypt entire folder structures
Progress Indicators - Visual progress bars for long operations
Advanced Security
🔐 Key File Authentication - Two-factor security with password + key file
🗑️ Secure File Deletion - DoD-standard file shredding (1-7 passes)
🎯 Encryption Profiles - Three security levels (Fast, Balanced, Paranoid)
📝 Metadata Preservation - Maintain original file attributes
💾 Auto-Backup - Automatic backup before decryption operations
Archive Management
📦 Encrypted Archives - Create password-protected archive files (.enca)
📂 Archive Extraction - Decrypt and extract archived files
💾 Backup System - Comprehensive backup/restore functionality
Utilities
🔍 File Comparison - SHA-256 hash-based file comparison
✓ Integrity Verification - Generate and verify file checksums
📋 Clipboard Integration - Encrypt/decrypt directly from clipboard
📜 Audit Logging - Complete operation history with timestamps
⚙️ Configuration Manager - Persistent settings storage
Password Tools
🎲 Password Generator - Cryptographically secure random passwords
🔑 Strength Checker - Four-level password strength analysis
📊 Password History - Track password attempt history
🔒 Security Specifications
Encryption Algorithm
Algorithm: AES-256-GCM (Galois/Counter Mode)
Key Size: 256-bit
Authentication: Built-in authentication tag (128-bit)
IV Size: 12 bytes (96-bit) - randomly generated per operation
Salt Size: 16 bytes (128-bit) - randomly generated per operation
Key Derivation
Algorithm: PBKDF2 with HMAC-SHA256
Iterations: 65,536 (configurable via profiles)
Salt: Unique per encryption operation
Output: 256-bit key
Security Features
Memory Safety: Passwords cleared from memory after use
Secure Random: Uses SecureRandom for all random data generation
No Hardcoded Keys: All keys derived from user passwords
Authentication: GCM mode provides both encryption and authentication
📥 Installation
Prerequisites
Java Development Kit (JDK) 14 or higher
Operating System: Windows, macOS, or Linux
Installation Steps
Download the source code
bash
   # Save EnhancedSecureEncryptor.java to your desired directory
Compile the program
bash
   javac EnhancedSecureEncryptor.java
Run the application
bash
   java EnhancedSecureEncryptor
Optional: Create an Executable Script
Linux/macOS:

bash
#!/bin/bash
java EnhancedSecureEncryptor "$@"
Save as encryptor.sh, then: chmod +x encryptor.sh

Windows:

batch
@echo off
java EnhancedSecureEncryptor %*
Save as encryptor.bat

🚀 Quick Start
Encrypting Your First File
Launch the application:
bash
   java EnhancedSecureEncryptor
Select option 3 (Encrypt File)
Enter the file path you want to encrypt:
   Enter input file path: /path/to/secret.txt
Accept the auto-generated output path or specify your own:
   Enter output file path (or press Enter for auto):
Enable compression (recommended for text files):
   Enable compression? (y/n): y
Enter and confirm your password:
   Enter password: ********
   Confirm password: ********
Your file is now encrypted! The output will be saved as secret.txt.enc
Decrypting a File
Select option 4 (Decrypt File)
Enter the encrypted file path: secret.txt.enc
Accept auto-generated output or specify path
Indicate if compression was used: y
Enter your password
File decrypted successfully!
📖 Detailed Usage Guide
1. Text Encryption (Option 1)
Encrypt short messages or sensitive text.

Example:

Enter message to encrypt: This is a secret message
Enter password: MyStrongPassword123!
Confirm password: MyStrongPassword123!
Output:

✅ Encrypted Message:
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
WE5qYXhGcjNkSG...base64_encoded_data...
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Copy to clipboard? (y/n): y
2. Batch File Encryption (Option 5)
Encrypt multiple files in one operation.

Usage:

Enter file paths (comma-separated): 
  file1.txt, file2.pdf, file3.docx
Enter output directory: /encrypted_files/
All files will be encrypted and saved to the specified directory.

3. Directory Encryption (Option 6)
Recursively encrypt all files in a directory.

Usage:

Enter input directory: /my_documents/
Enter output directory: /encrypted_documents/
Preserves folder structure in encrypted output.

4. Key File Creation (Option 9)
Create a cryptographic key file for enhanced security.

Steps:

Select option 9
Specify key file path: my_keyfile.key
Choose key size (32-256 bytes): 64
IMPORTANT: Store this file securely!
5. Encrypt with Key File (Option 10)
Use password + key file for two-factor security.

Usage:

Enter file to encrypt: sensitive_data.xlsx
Enter password: MyPassword123
Enter key file path: my_keyfile.key
Decryption requires BOTH password AND key file!

6. Secure File Deletion (Option 11)
Permanently destroy files with military-grade overwriting.

Warning: This operation is irreversible!

Usage:

Enter file path to securely delete: old_file.txt
Number of overwrite passes (1-7): 3
This will permanently destroy the file. Continue? yes
Shred Passes Explained:

1 pass: Basic security (fast)
3 passes: Standard security (recommended)
7 passes: Maximum security (DoD 5220.22-M standard)
7. Encrypted Archives (Option 16)
Create password-protected archive files.

Usage:

Enter file paths (comma-separated): 
  report.pdf, data.xlsx, notes.txt
Enter output archive name: project_files
Enter password: ArchivePassword123!
Creates project_files.enca - a single encrypted file containing all your files.

8. File Comparison (Option 18)
Compare two files to verify integrity.

Usage:

Enter first file path: original.txt
Enter second file path: backup.txt

📊 File Comparison Results:
════════════════════════════════════════
File 1: original.txt
Size: 1024 bytes

File 2: backup.txt
Size: 1024 bytes

Result: ✅ IDENTICAL
9. Clipboard Encryption (Option 12)
Encrypt/decrypt text directly from clipboard.

Workflow:

Copy sensitive text to clipboard
Select option 12
Choose mode (1 = Encrypt, 2 = Decrypt)
Enter password
Encrypted/decrypted text copied back to clipboard
Perfect for:

Quick message encryption
Encrypting passwords before storing
Secure note taking
🎯 Security Profiles
Choose the right balance between speed and security:

⚡ FAST Profile
Best for: Non-sensitive data, testing, temporary files

Iterations: 10,000
Compression: OFF
Shred Passes: 1
Speed: Very Fast
Security: Basic
⚖️ BALANCED Profile (Recommended)
Best for: General use, personal documents, everyday encryption

Iterations: 65,536
Compression: ON
Shred Passes: 3
Speed: Moderate
Security: Strong
🔒 PARANOID Profile
Best for: Highly sensitive data, legal documents, financial records

Iterations: 200,000
Compression: ON
Shred Passes: 7
Speed: Slower
Security: Maximum
To set a profile:

Select option 19 (Encryption Profile)
Choose your desired profile
All future operations use this profile
⚙️ Configuration
Configuration File
Settings are stored in encryptor.config

Available Settings
Setting	Options	Description
default_output_dir	Path	Default directory for encrypted files
default_compression	true/false	Enable compression by default
auto_backup	true/false	Create backup before decryption
encryption_profile	FAST/BALANCED/PARANOID	Default security profile
Managing Settings
Use option 14 (Settings) to configure:

⚙️  Settings & Configuration
════════════════════════════════════════
1. Set default output directory
2. Set default compression (on/off)
3. Set auto-backup before decrypt (on/off)
4. View current settings
5. Reset to defaults
💡 Best Practices
Password Security
✅ DO:

Use passwords with 16+ characters
Mix uppercase, lowercase, numbers, and symbols
Use unique passwords for different files
Store passwords in a password manager
Use the password generator (option 7)
❌ DON'T:

Reuse passwords across files
Use dictionary words or common patterns
Share passwords via unencrypted channels
Write passwords down insecurely
File Management
✅ DO:

Keep encrypted files separate from originals
Use secure deletion for original sensitive files
Save metadata files (.meta) with encrypted files
Regularly test your backups
Store key files separately from encrypted data
❌ DON'T:

Delete encrypted files before verifying decryption
Store key files with encrypted data
Forget which files used compression
Ignore backup recommendations
Key File Usage
✅ DO:

Store key files on external media (USB drive)
Keep multiple copies in secure locations
Use key files for highly sensitive data
Document which files use which key files
❌ DON'T:

Store key files on the same device as encrypted files
Email or cloud-sync key files
Forget which key file was used for encryption
Audit & Monitoring
✅ DO:

Regularly review audit logs (option 13)
Monitor password history for failed attempts
Keep backups of important encrypted files
Test decryption periodically
🔍 Troubleshooting
"Decryption failed - check password and data"
Causes:

Incorrect password
File corrupted
Wrong key file used
File not properly encrypted
Solutions:

Verify password (check for typos, caps lock)
Try password from password history
Ensure correct key file if used
Check file integrity (option 15)
Restore from backup if available
"File too large (max 100MB)"
Solution:

Use directory encryption for large datasets
Create an encrypted archive for multiple files
Split large files before encryption
"Could not read from clipboard"
Causes:

No GUI environment (SSH session)
Clipboard access denied
Solution:

Use file-based encryption instead
Run in graphical environment
Check system permissions
"Password too weak"
Solution:

Use the password generator (option 7)
Add more characters (aim for 16+)
Include uppercase, numbers, and symbols
Avoid common words and patterns
Encrypted file won't decrypt
Recovery steps:

Check if compression was enabled during encryption
Verify you're using the correct password
If key file was used, ensure you have the exact same file
Check audit log for encryption details
Try restoring from backup (option 20)
📂 File Structure
project/
├── EnhancedSecureEncryptor.java    # Main program
├── encryptor.config                 # Configuration file (auto-generated)
├── crypto_audit.log                 # Audit log (auto-generated)
├── .password_history                # Password attempts (auto-generated)
└── .encryptor_backups/             # Backup directory (auto-generated)
    └── [backup files]
🔐 Security Considerations
What This Tool Protects Against
✅ Unauthorized file access
✅ Data theft from stolen devices
✅ Cloud storage snooping
✅ Data breaches
✅ Forensic recovery of deleted files

What This Tool Does NOT Protect Against
❌ Keyloggers capturing your password
❌ Malware on your system
❌ Rubber-hose cryptanalysis (physical coercion)
❌ Quantum computer attacks (use post-quantum cryptography if needed)
❌ Side-channel attacks on the encryption process

Recommendations for Maximum Security
Use on trusted systems only - Avoid public computers
Keep system updated - Patch OS and Java regularly
Use antivirus/antimalware - Protect against keyloggers
Enable full disk encryption - Protect the encryption tool itself
Use key files - Add second factor for critical data
Regular backups - Store in multiple secure locations
Test recovery - Ensure you can decrypt before deleting originals
📊 Performance Benchmarks
Approximate performance (will vary by system):

Operation	File Size	Time (Balanced)	Time (Paranoid)
Encrypt	1 MB	0.5s	1.2s
Encrypt	10 MB	3.5s	8.0s
Encrypt	50 MB	15s	35s
Decrypt	1 MB	0.4s	1.0s
Shred (3 passes)	100 MB	8s	-
Archive (5 files)	20 MB	5s	12s
Benchmarks on: Intel i5 @ 3.0GHz, 8GB RAM, SSD

🆘 Support & Resources
Common Questions
Q: Can I encrypt the same file twice?
A: Yes, but it's unnecessary. AES-256-GCM is already military-grade.

Q: What happens if I lose my password?
A: Data is permanently unrecoverable. There is no backdoor or password reset.

Q: Can I use this for commercial purposes?
A: Yes, but review your jurisdiction's encryption laws.

Q: Is this safe for cloud storage?
A: Yes! Encrypted files are safe to upload to cloud services.

Q: How do I securely share encrypted files?
A: Share encrypted file via one channel, password via another (e.g., encrypted email).

🔄 Version History
v3.0 (Current)
Added encrypted archive support
Implemented backup manager
Added security profiles
Clipboard integration
File comparison tool
Password history tracking
Configuration management
Comprehensive audit logging
v2.0
Added key file authentication
Secure file deletion
Metadata preservation
Directory encryption
Batch processing
Progress indicators
v1.0
Basic file/text encryption
Password strength checker
Password generator
📝 License
This software is provided "as is" without warranty of any kind. Use at your own risk.

Important: Check your local laws regarding encryption software. Some jurisdictions restrict or regulate the use of strong encryption.

🤝 Contributing
Contributions are welcome! Areas for improvement:

GUI interface
Post-quantum cryptography support
Hardware security module integration
Multi-threading for large files
Additional compression algorithms
Cross-platform testing
⚠️ Disclaimer
This tool is for legitimate security purposes only. Users are responsible for:

Complying with local encryption laws
Securing their passwords and key files
Testing backup/recovery procedures
Not using for illegal activities
The developers assume no liability for data loss, legal issues, or misuse.

🎓 Educational Resources
Learn More About Cryptography
NIST Cryptographic Standards
AES Specification (FIPS 197)
OWASP Cryptographic Storage Cheat Sheet
Password Security
EFF's Guide to Creating Strong Passwords
NIST Password Guidelines
Made with 🔐 for secure computing

Last Updated: 2025
