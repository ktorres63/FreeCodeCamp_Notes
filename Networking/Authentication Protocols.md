Many different authentication are used in networking to verify the identity of devices and users. Those protocols are essential because they provide a secure and standardized way of verifying the identity of user, devices, and others entities in a network. Without authentication protocols, it would be difficult to securely and reliably identify entities in a network, making easy for attackers to gain  unauthorized access and potentially compromise the network
Authentication protocols also provide a means for securely exchanging information between entities in a network. Let us take a look at a few most commonly used authentication protocols:

|Protocol|Description|
|-|-|
|Kerberos|Key Distribution center (KDC) based authentication protocol that uses tickets in domain enviroments|
|SRP|This is a password-based authentication protocol that uses cryptography to protect against eavesdropping and man in the middle attacks|
|SSL|A cryptographic protocol used for secure communication over a computer network|
|TLS| TLS is a cryptographic protocol that provides communication security over the internet. It's the successor to SSL|
|OAuth|An open standard for authorization that allows users to grant third-party access to their web resources without sharing their passwords
|OpenID|OpenID is a decentralized authentication protocol that allows users to use a single identity to sign in to multiple websites|
|SAML|Security Assertion Markup language is an XML- based standard for securely exchanging authentication and authorization data between parties|
|2FA| An authentication method that used a combination of 2 different factors to verify a user's identity|
|FIDO|The fast IDentity online alliance is a consortium of companies working to develop open standards for strong authenticaion|
|PKI|PKI is a system for securely exchanging information based on the use of public and private keys for encryption and digital signatures|
|SSO|An authentication method that allows a user to use a single set of credentials to access multiple applications|
|MFA|MFA is an authentication method that uses multiple factors, such as something the user knows (a password), something the user has (a phone), or something the user is (biometric data), to verify their identity.|
|PAP|A simple authentication protocol that sends a user's password in clear text over the network|
|CHAP|An authentication protocol that uses a three-way handshake to verify a user's identity|
|EAP|A framework for supporting multiple athentication methods, allowing for the use of various technologies to verify a user's identity|
|SSH|This is a network protocol for secure communication between a client and a server. We can use it for remote command-linee access and remote command execution, as well as for secure file transfer. SSH uses encryption to protect against eavesdropping and other attacks and can also be used for authentication|
|HHTPS|This is a secure version of the HTTP protocol used for communication on the internet. HTTPS uses SSL/TLS to encrypt communication and provide authentication, ensuring that third parties cannot intercept and read the transmitted data. It is widely used for secure communication over the internet, particularly for web browsing.|
|LEAP| Is a wireless authentication protocool developed by Cisco. It uses EAP toprovide mutual authentication between a wireless client and a server and uses the RC4 encryption algorithm to encrypt communication between the two, LEAP is vulnerable to dictionary attacks and other security vulnerabilities and has been largely replaced by more secure protocols such as EAP-TLS and PEAP|
|PEAP| PEAP on the other hand is a secure tunneling protocol used for wireless and wired networks. It's based on EAP and uses TLS to encrypt communication between a client and a server. PEAP uses a server-side certificate to authenticate the server and can also be used to authenticate the client using various methods, such as passwords, certificates, or biometric data. PEAP is widely used in terprise networks for secure information|

For example, LEAP and PEAP may be used to authenticate wireless clients when they access the wireless network or to authenticate remote employees connecting to the network via a VPN. In these cases, using SSH or HTTPS would be challenging to implement, as they are designed for different purposes. In terms of security PEAP is generally more secure than LEAP beacuse it uses a server-side public key certificate to authenticate the server and encrypt MSCHAPv2 hash, whille LEAP relies on a shared secret that is negotiated between the client and the server and doesn't encrypt MSCHAPv2 hashes. PEAP also supports the use of stronger encryption algorithms, such as AES and 3DES, for encrypting the authentication information, whereas LEAP uses the weaker RC4 algorithm.

However, both protocols are vulnerable to specific attacks and have been largely replaced by more secure protocols such as EAP-TLS.