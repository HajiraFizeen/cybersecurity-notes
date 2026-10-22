# Cryptography Basics

## 1. What is cryptography?
Cryptography uses mathematical techniques to protect information, verify integrity, and support authentication.

Its major goals include:
- Confidentiality: keeping information private.
- Integrity: detecting unauthorized changes.
- Authentication: verifying identities or message origins.
- Non-repudiation: supporting evidence that an action or signature is associated with a signing identity.

## 2. Encryption

**Meaning:** Encryption transforms readable data (plaintext) into unreadable ciphertext using an algorithm and key.

**Purpose:** Protect confidentiality.

**Types:**
- Symmetric encryption: the same secret key encrypts and decrypts data.
- Asymmetric encryption: uses a public/private key pair for operations such as encryption and digital signatures.

**Examples:** AES is a symmetric encryption algorithm. RSA is a public-key cryptographic algorithm.

## 3. Hashing

**Meaning:** A hash function maps input data to a fixed-length digest.

**Purpose:** Support integrity checking and other security operations.

**Examples:** SHA-256 and SHA-3.

Important:
- Hashing is not encryption.
- A cryptographic hash is designed to be difficult to reverse.
- A hash alone does not prove who created a file.
- Passwords should be stored using dedicated password-hashing algorithms such as Argon2id, scrypt, or appropriately configured bcrypt—not plain fast SHA-256 hashes.

## 4. Encoding

**Meaning:** Encoding changes data into a representation suitable for storage or transmission.

**Examples:** Base64 and URL encoding.

Encoding is not a security mechanism. Encoded information can usually be decoded without a secret key.

## 5. Digital Signatures

Digital signatures use asymmetric cryptography to help verify the integrity and origin of a signed message.

A verifier checks the signature using the relevant public key and a suitable verification algorithm.

Trust in the identity associated with a public key depends on how that key is established and managed.

## 6. TLS and HTTPS

TLS protects data exchanged between communicating systems.

HTTPS uses HTTP over TLS to provide transport confidentiality and integrity, along with server authentication through certificate validation.

**Security practices:**
- Use modern TLS configurations.
- Validate certificates.
- Keep cryptographic libraries updated.
- Protect private keys.
- Avoid obsolete protocols and algorithms.

## 7. Password Security

Good practices:
- Store passwords using a dedicated password-hashing function.
- Use unique passwords for different accounts.
- Use a password manager.
- Enable multi-factor authentication.
- Rate-limit authentication attempts.
- Protect password-reset processes.

## 8. Common Mistakes

| Mistake | Correct understanding |
|---|---|
| Base64 is encryption | Base64 is encoding |
| Hashing is encryption | Hashing and encryption serve different purposes |
| Every hash is secure for passwords | Fast general-purpose hashes are unsuitable for direct password storage |
| HTTPS makes a website completely safe | HTTPS protects the connection, not every part of the application |
| A digital signature encrypts the whole message | Signatures primarily support integrity and authenticity verification |

## 9. Practice Ideas

- Calculate a SHA-256 digest for a sample file.
- Compare a file's hash before and after modifying it.
- Encode and decode a harmless Base64 string.
- Inspect a website's TLS certificate using a browser.
- Explain why a password hash should not be stored as plaintext.

## Learning Resources
- NIST Computer Security Resource Center: https://csrc.nist.gov/
- OWASP Password Storage Cheat Sheet: https://cheatsheetseries.owasp.org/cheatsheets/Password_Storage_Cheat_Sheet.html
- OpenSSL documentation: https://docs.openssl.org/

## Key Takeaway
Encryption protects confidentiality, hashing supports integrity-related operations, encoding changes representation, and digital signatures help verify integrity and authenticity.
