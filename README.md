# Building a Public Key Infrastructure (PKI) with Active Directory Certificate Services (AD CS)
![PKI / AD CS](https://i.imgur.com/Ne9tY6Y.png)

## Overview

This project walks through the setup and deployment of a Public Key Infrastructure (PKI) using Active Directory Certificate Services (AD CS) on Windows Server 2022.  The goal is to simulate real-world certificate issuance, secure a website via HTTPS, and demonstrate certificate request and binding workflows using a two-VM Windows environment.

This build highlights key tasks such as:  

- Set up a Certificate Authority (CA)
- Generate and process Certificate Signing Requests (CSRs)
- Issue and install digital certificates
- Secure web communications using HTTPS

## Installed Active Directory Certificate Services (AD CS) Role

Enabled the Windows Server to operate as a Certificate Authority (CA) – the foundational component of any PKI deployment.

Strategic Insight:  This establishes the root of trust for certificate issuance, a critical control point in enterprise security architecture.

![PKI2](https://imgur.com/TmCeyIu.png)

