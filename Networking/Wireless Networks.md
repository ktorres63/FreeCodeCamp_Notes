Wireless networks are computer networks that use wireless data connections between network nodes. Thesse networks allow devices such as laptops, smartphones, and tablets to communicate with each other and the internet without needing physical connections such as cables
Wireless networks use radio frequency (RF) technology to transmit data between devices. Each device on a wireless network has a wireless adapter that converts data into RF signals and sends them over the air. Other devices on the network receive these signals with their own wireless adapters, and the data is then converted back into a usable form. Those can operate over various ranges, depending on the technology used. For example a local area network (LAN) that covers a small area, such as a home or small office,might use a wireless technology called WI-Fi, which has a range of a few hundred feet. On the other hand, a wireless wide area network(WWAN) might use mobile telecommunication technology such as cellular data (3G,4G,LTE,5G), which can cover a much larger area
Therefore, to connect to a wireless network, a device must be within range of the network and configured with the correct network settings, such as the network name and password. Once connected, devices can communicate with each other and the Internet, allowing users to access online resources and exchange data.
Communication between devices occurs over RF in the 2.4 GHz or 5 GHz bands in a wi-fi network. When a device, like a laptop wants to send data over the network, it first communicate with the ireless access point (WAP) to request permission to transmit. The WAP is a central device, like a router, that connects the wireless network to a wired network and controls access to the network. Once the WAP grants permission, the transmitting device sends the data as RF signals, which are received by the wireless adapters of other devices on the network. The data is then converted back into a usable form and passed on to the appropriate application or system.
The strength of the RF signal and the distance it can travel are influenced by factors such as the transmitter's power, the presence of obstacles, and the density of RF noise in the environment. So, to ensure reliable communication, WiFi networks use techniques such as spread spectrum transmission and error correction to overcome these challenges.

## Wifi Connection
The device must also be configured with the correct network settings, such as the network name /service set identifier (SSID) and password. So to connect to the router, the laptop uses a wireless networking protocol called IEE 802.11. This protocol defines the technical details of how wireless devices communicate with each other and with WAPs. When a device wants to join a WiFi network, it sends a request to the WAP to initiate the connection process. This request is known as a connection request frame or association request and is sent using the IEEE 802.11 wireless networking protocol. The connection request frame contains various fields o information, including the following but not limited to:

![[wifi.png]]
The device then uses this information to configure its wireless adapter and connect to the WAP. Once the connection is established, the device can communicate with the WAP and other network devices. It can also access the Internet and other online resources through the WAP, which acts as a gateway to the wired network. However, the SSID can be hidden by disabling broadcasting. That means that devices that search for that specific WAP will not be able to identify its SSID. Nevertheless, the SSID can still be found in the authentication packet.

In addition to the IEEE 802.11 protocol, other networking protocols and technologies may also be used, like TCP/IP, DHCP, and WPA2, in a WiFi network to perform tasks such as assigning IP addresses to devices, routing traffic between devices, and providing security.

### WEP challenge-response handshake

The challenge-response handshake is a process to establish a secure conection between a WAP and client device in a wireless network that uses the WEP security protocol. This involves exchanging packets between the WAP and the client device to authenticate the device and establish a secure connection
|Step|Who|Description|
|-|-|-|
|1|Client|Sends an association request packet to the WAP, requesting access|
|2|WAP| Responds with an association response packet to the client, which includes a challenge string|
|3|Client| Calculates a response to the challenge string and a shared secret key and sends it back to the WAP| 
|4|WAP|Calculated the expected response to the challenge with the same shared secret key and sends an authentication respose packet to the client |

Nevertheless, some packets can get lost, so the so-called CRC checksum has benn integrated. Cyclic Redundancy Check (CRC) is an error-detection mechanism used in the WEB protocol to protect against data corruption in wireless communications. A CRC value is calculated for each packet transmimtted over the wireless network based on the packet's data.the CRC value is recalculated and compared to the original value. If the values match, the data has been transmitted successfully without any errors. However, if the values do not match, the data has been corrupted and needs to be retransmitted.
## Security Features
Wi-fi networks have several security features to protect against unauthorized access and ensure the privacy and integrity of data transmitted over the network. Some of the leading security features include but are not limited to:
+ Encryption
+ Access Control
+ Firewall
### Encryption
We can use various encryption algorithms to protect the confidentiality of data transmitted over wireless networks. The most common encryption algorithms in Wi-fi networks are Wired Equivalent Privacy(WEP), Wifi Protected Access 2(WPA2) and Wi-fi Protected Access 3 (WPA3)
### Access Control
WiFi networks are configured by default to allow authorized devices to join the network using specific authentication methods, however, these methods can be changed by requiring a password or a unique identifier (such as a MAC address) to identify authorized devices
### Firewall
A firewall is a security system that controls incoming and outgoing network traffic based on predetermined security rules. For example, WiFi routers often have built-in firewalls that can block incoming traffic from the Internet and protect against various types of cyber threats.

## Encryption Protocols
Wired Equivalent Privacy(WEB) and Wi-fi protected Acces (WPA) are encryption protocols that secure data transmitted over a wifi network. WPA can use different encryption algorithms, including Advanced Encryption Standard (AES)

### WEP
WEP uses a 40-bit or 104-bit key to encrypt data, while WPA using AES uses a 128-bit key. Longer key provide more robust encryption an are more resistant to attacks. However, it is vulnerable to various attacks that can allow an attacker to decrypt data transmitted over the network. In addition, WEP is not compatible with newer devices and operating systems and is generally no longer considered secure. Finally, WEP uses the RC4 cipher encryption algorithm, which makes it vulnerable to attacks.
However, WEP uses a shared key for authentication, which means the same key is used for encryption and authentication. There are two versions of the WEP protocol:

+ WEP-40/WEP-64
+ WEP-104

However,since the IV in WEP is relatively small, we can brute force it, try every possible combination of characters for it, and determine the correct value. Afterward we can use it to decrypt the data in the packet. This allows us to access the data transmitted over the wireless network and potentialyy compromise the network's security.

### WPA

WPA provides the highest level fof security and isn't suceptible to the same types of attacks as WEP. In addition, WPA uses more secure authentication methods, such as a Pre-Shared Key (PSK) or an 802..1X authentication sever, which provide stronger protection against unauthorized access. Although older devices may not support WPA is compatible with most devices and operating systems. All wireless networks, especially in critical infrastructure like offices, should generally implement at least WPA2 or even WPA3 encryption.

## Authentication Protocols
Lightweight Extensible Authentication Protocol(LEAP) and protected Extensible AUthentication Protocol(PEAP) are authentication protocols used to secure wireless networks to provide a secure method for authenticating devices on a wireless network and are often used in conjunction with WEP or WPA to provide additional layer of security 

LEAP and PEAP are both based on the Extensible Authentication Protocol (EAP), a framework for authentication used in various networking contexts. However, one key difference between LEAP and PEAP is how they secure the authentication process

+ LEAP uses a shared key for authentication, which means that the same key is used for encryption and authentication

This can make it relatively easy for us to gain access to the network if the key is compromised

However, PEAP uses a more secure authentication method called tunneled  Transport Layer Security (TLS). This method establishes a secure connection between the device and the WAP using a sigital certificate and an encrypted tunnel protects the authentication process. This provides more robust protection against unauthorized access and is more resistant to attacks

## TACACS+
In a wireless network, when a wireless access point (WAP) sends an authentication request to a terminal controller access-control system plus (TACACS+) server, it's likely that the entire request packet will be encrypted to protect the confidentiality and integrity of the request

TACACS+ is a protocol used to authenticate and authorize users accessing network devices, such as routers and switches. When a WAP sends an authentication request to a TACACS+ server, the request typically includes the user's credentials and other information about the session.
Encrypting the authentication request helps to ensure that this sensitive information is not visible to unauthorized parties who may be able to intercept the request.  At the same time, it is being transmitted over the network. It also helps prevent tampering with the request or replacing it with a malicious request of their own
Several encryption methods may be used to encrypt the authentication request, such as SSL/TLS or IPSec. The specific encryption method used may depend on the configuration of the TACACS+ server and the capabilities of the WAP.

## Disassociation Attack

A disassociation Attack is a type of all wireless network attack that aims to disrup the communication between a WAP and its clients by sending disassociation frames to one or more clients
The WAP uses disassociation frames to disconnect a client from the network. When a WAP sends a disassociation frame to a client, the client will disconnect from the network and have to reconnect to continue using the network
We can launch the attack from within or outside the network depending on our location and network security measures. The purpose of this attack is to disrupt the communication between the WAP and its clients, causing the clients to disconnect and possibly causing inconvenience or disruption to the users. We can also use it as a precursor to other attack, such as MITM attack, by forcing the clients to reconnect to the network and potentially exposing them to further attacks

## Wireless Hardening
There are many differnt ways to protect wireless networks. However some  examples should be considered to increase wireless network's security dramatically. These are the following, but not limited to:
+ Disabling broadcasting
+ Wi-fi Protected access
+ MAC filtering
+ Deploy EAP-TLS

### Disabling Broadcasting
Disabling the broadcasting of the SSID is a security measure that can help harden a WAP by making it more difficult to discover and connect to the network. When the SSID is broadcasted, it's included in beacon frames regularly transmitted by the WAP to advertise the availability of the network. By disabling the broadcasting of the SSID, the WAP will not transmit beacon frames, and the network will not be visible to devices that aren't already connect to the network
### WPA 
Again, WPA provides strong encryption and authentication for wireless communications, helping protect against unauthorized network access and sensitive data interception. WPA includes two main versions:

+ WPA-Personal
+ WPA-Enterprise

WPA-Personal designed for home and small business networks, and WPA-Enterprise designed for larger organization and uses a centralized authentication server(e.g RADIUS or TACACS+ ) to verify the identify of clients
### MAC filtering
MAC filtering is a security measure that allows a WAP to accept or reject connections from specific devices based on their MAC addresses. By configuring the WAP to accept connections only from devices with approved MAC addresses, it is possible to prevent unauthorized devices from connecting to the network.

### Deploy EAP-TLS
EAP-TLS is a security protocol used to authenticate and encrypt wireless communications. It uses digital certificates and PKI to verify the identify of clients and stablish secure connections. Deploying EAP-TLS can help to harden a WAP by providing strong authentication and encryption for wireless communications, which can protect against unauthorized access to the network and the interception of sensitive data.




























