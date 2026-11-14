# SecureVault

SecureVault is an educational browser-only encrypted note vault built with the Web Crypto API. It demonstrates PBKDF2-SHA-256 key derivation and AES-256-GCM authenticated encryption without sending data to a server.

> This is a learning project, not a production password manager. Do not store recovery phrases, banking credentials, identity documents, or other critical secrets.

## Features
- Create, lock, and unlock an encrypted local vault
- Authenticated encryption with random salt and IV
- Encrypted JSON backup export/import
- Security inspector and explicit threat model
- Responsive, accessible interface

## Run locally
Open `dist/index.html` in a modern browser. No build step or dependency installation is required.

## Product documentation
See [PRD.md](PRD.md) for scope, requirements, limits, and future work.

## Author
Debraj Dutta — AI & Cybersecurity student.

