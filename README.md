# Building a Public Key Infrastructure (PKI) with Active Directory Certificate Services (AD CS)

<img align="left" alt="PKI / AD CS" width="400px" src="https://i.imgur.com/Ne9tY6Y.png" />

### Overview

This project walks through the setup and deployment of a Public Key Infrastructure (PKI) using Active Directory Certificate Services (AD CS) on Windows Server 2022.  The goal is to simulate real-world certificate issuance, secure a website via HTTPS, and demonstrate certificate request and binding workflows using a two-VM Windows environment.

#### This build highlights key tasks such as:  

    - Set up a Certificate Authority (CA)
    - Generate and process Certificate Signing Requests (CSRs)
    - Issue and install digital certificates
    - Secure web communications using HTTPS

</br>
</br>
</br>

## Installed Active Directory Certificate Services (AD CS) Role

Enabled the Windows Server to operate as a Certificate Authority (CA) – the foundational component of any PKI deployment.

Strategic Insight:  This establishes the root of trust for certificate issuance, a critical control point in enterprise security architecture.

</br>

<div align="center">
  <img alt="PKI2" width="600px" src="https://imgur.com/bX8cuFs.jpeg" />
</div>

</br>

## Configured the Certificate Authority

Key actions
- Generated a new private key
- Selected the SHA-512 hashing algorithm for enhanced cryptographic integrity
- Assigned a CA name and configured a self-signed certificate with a 5-year lifespan

Mirrors enterprise-grade CA configuration with secure defaults to ensure long-term trust and minimal reissuance overhead.

</br>

<div align="center">
  <img alt="PKI3" width="600px" src="https://imgur.com/3nspuJg.jpeg" />
</div>

</br>

## Deployed IIS Website for HTTPS Binding

Provisioned a live website using Internet Information Services (IIS) to serve as the endpoint for HTTPS encryption validation.

Reflects a typical internal web application setup where secure transport protocols are mandated.

</br>

<div align="center">
  <img alt="PKI4" width="600px" src="https://imgur.com/J0O9mUB.jpeg" />
</div>

</br>


## Created and Transferred a Certificate Signing Request (CSR)

Generated the CSR and transferred it securely to the CA server via scp.  A CSR is normally sent to a CA by email.  

Rationale:  Simulates a secure, CLI-based enterprise certificate request workflow without reliance on GUIS-common in headless or scripted deployments.

</br>

<div align="center">
  <img alt="PKI5" width="600px" src="https://imgur.com/IkWHlYp.jpeg" />
</div>

</br>

</br>

<div align="center">
  <img alt="PKI6" width="600px" src="https://imgur.com/r9RebS8.jpeg" />
</div>

</br>

**PowerShell Command** 

scp 'c:\Users\Administrator\Desktop\certificate request.txt' administrator@ZYWIN01:C:\Users\Administrator\Documents

</br>

<div align="center">
  <img alt="PKI7" width="600px" src="https://imgur.com/pMMJbS1.jpeg" />
</div>

</br>

- Text file successfully copied over with SCP

</br>

<div align="center">
  <img alt="PKI7" width="600px" src="https://imgur.com/zXyy0vN.jpeg" />
</div>

</br>

## Issued and Delivered Digital Certificate

Processed the CSR and issued a certificate from the CA.

Emulates the internal CA workflow for managing certificates for endpoints, web servers, and VPN appliances.

</br>

<div align="center">
  <img alt="PKI7" width="600px" src="https://imgur.com/pNdy8HO.jpeg" />
</div>

</br>

## Bound Certificate to HTTPS (TCP 443)

Applied the issued certificate to the IIS website to enable encrypted traffic via HTTPS

Demonstrates the implementation of SSL/TLS encryption required by regulatory frameworks (e.g., HIPAA, PCI-DSS).

</br>

<div align="center">
  <img alt="PKI7" width="600px" src="https://imgur.com/5Tfe0j5.jpeg" />
</div>

</br>

## Enterprise Alignment & Use Case Relevance
This lab replicates an enterprise-grade Public Key Infrastructure (PKI) deployment using native Microsoft technologies.  It closely aligns with real-world IT and security practices across sectors:

-	Certificate Authority Operations: Mirrors internal certificate issuance workflows for web, user, and device authentication.
-	Lifecycle Management: Reflects full lifecycle handling—from CSR generation to certificate deployment and HTTPS binding.
-	Secure Communications: Demonstrates how encrypted web services are provisioned internally to support secure access and data protection.
-	Regulatory Compliance: Supports industry mandates for secure transport and trust-based access controls (Zero Trust Architecture, TLS 1.2+).
-	System Hardening: Offers a blueprint for building secure-by-default environments.

## Key Business Benefits:
-	Cost Avoidance: Reduces reliance on third-party certificate vendors.
-	Operational Agility: Equips teams with practical expertise for rapid deployment and maintenance of internal PKI.
-	Scalability & Control: Enables centralized certificate management and policy enforcement through AD integration.

## Conclusion
This project demonstrates hands-on implementation of a fully functioning PKI environment using Active Directory Certificate Services (AD CS) in Windows Server. It showcases the end-to-end process—from CA deployment to HTTPS enforcement—highlighting critical skills in enterprise security, certificate lifecycle management, and infrastructure hardening.

This implementation serves as a reliable foundation for more advanced enterprise integrations, including smart card authentication, VPN cert enforcement, and automated certificate provisioning at scale.




















