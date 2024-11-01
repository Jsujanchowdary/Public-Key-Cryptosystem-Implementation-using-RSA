# Public-Key Cryptosystem Implementation using RSA

## Project Overview
This project demonstrates the implementation of a Public Key Cryptosystem using the RSA encryption and decryption algorithms. The aim is to show how to generate key pairs, encrypt messages, and securely transmit information through public-key cryptography.

## Aim
To implement a Public Key Cryptosystem using RSA, demonstrating the process of key pair generation and secure message encryption and decryption.

## Requirements
- **OpenSSL**: The RSA encryption and decryption processes are performed using the OpenSSL toolkit.

## Implementation Steps

1. **Generate a Private Key**
   ```bash
   openssl genrsa -out private-key.pem 3072
   ```

2. **Generate the Corresponding Public Key**
   ```bash
   openssl rsa -in private-key.pem -pubout -out public-key.pem
   ```

3. **Create a Self-Signed Certificate (Optional)**
   ```bash
   openssl req -new -x509 -key private-key.pem -out cert.pem -days 360
   ```
   During the certificate creation, you will be prompted to enter information such as country name, state, locality, organization, etc.

4. **Export the Certificate to a PFX File**
   ```bash
   openssl pkcs12 -export -inkey private-key.pem -in cert.pem -out cert.pfx
   ```
   You will need to enter and verify an export password to secure the certificate.

## Observation
- A 3072-bit RSA private key and corresponding public key were successfully generated.
- A self-signed certificate was created as an optional verification step.
- The encryption and decryption process was tested, confirming the secure transmission and integrity of the message.

## Result
The implementation successfully demonstrated RSA encryption and decryption, showing the effectiveness of asymmetric cryptography in secure communication. This highlights the importance of protecting the private key to ensure message confidentiality and authenticity.
