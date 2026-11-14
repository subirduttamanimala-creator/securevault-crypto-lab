# SecureVault — Product Requirements Document

## Product vision
SecureVault is an educational, browser-only encrypted note vault that makes modern cryptographic concepts visible and understandable. It helps learners store a small private note locally while seeing the exact security model: PBKDF2 key derivation, AES-GCM authenticated encryption, a random salt, and a random IV.

## Problem
Security students often learn cryptography as equations or API calls without seeing how key derivation, encryption, integrity, storage, and recovery fit together. Many demo apps also overclaim security. SecureVault should be useful, polished, and explicit about its limits.

## Target users
- AI and cybersecurity students
- Developers learning the Web Crypto API
- Recruiters evaluating practical security thinking

## MVP requirements
1. Create or unlock a vault using a passphrase.
2. Derive an AES-256-GCM key with PBKDF2-SHA-256 and a random 16-byte salt.
3. Encrypt/decrypt a note with a random 12-byte IV.
4. Store only ciphertext, salt, IV, and version metadata in localStorage.
5. Auto-lock on refresh and provide a manual lock action.
6. Show a security inspector and threat-model guidance.
7. Export/import an encrypted JSON backup.
8. Never send note content or passphrases over the network.

## Non-goals
- Password-manager use
- Cloud sync, account recovery, or multi-device access
- Protection from malware, browser extensions, keyloggers, or a compromised device
- Formal cryptographic audit or compliance certification

## Success criteria
- A user can create, lock, unlock, edit, export, import, and reset a vault.
- Wrong passphrases fail closed without exposing plaintext.
- The interface remains usable on mobile and desktop.
- Documentation never describes the prototype as production-ready.

## Privacy and security
All cryptographic operations use the browser's Web Crypto API. Plaintext and passphrases remain in memory only while the vault is unlocked. localStorage contains encrypted data and public parameters only. The app uses 310,000 PBKDF2 iterations for the demo; production systems should use a reviewed architecture, platform-specific tuning, secure memory handling, and independent security assessment.

## Future work
- WebAuthn-backed key wrapping
- Encrypted multi-note collections
- Idle timeout and clipboard clearing
- Automated crypto-format test vectors
- Independent threat-model review

