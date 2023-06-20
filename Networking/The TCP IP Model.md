The TCP/IP model is also a layered reference model, often referred to as the Internet Protocol Suite. The term TCP/IP stands for the two protocols Transmission Control Protocol (TCP) and Internet Protocol (IP). IP is located within the network layer (Layer 3) and TCP is located within the transport layer (Layer 4) of the OSI layer model.
|Layer|Function|
|---|---|
|4. Application|The application Layer allows applications to acces the other layer's services and defines the protocols applications use to exchange data|
|3. Transport|The transport layer is the responsible for providing(TCP) session and (UDP) datagram services for the application layer|
|2. Internet |The internet Layer is resposible for host addressiong, packaging and routing functions|
|1. Link|The link layer is responsible for placing the TCP/IP packets on the network medium and receiving corresponding packets from the network medium TCP/IP is designed to work independently of the network access method, frame format and medium|

With TCP/IP every application can transfer and exchange data over any network, and it doesn't matter where the receiver is located. IP ensures that the data packet reaches its destination, and TCP controls the data transfer and ensures the connection between daa stream and application. The main difference between TCP/IP and OSI is the number of layers, some of which have been combined
![[tcpIPvsOSI.png]]

The most important tasks of TCP/IP are
|Task|Protocol|Description|
|---|---|---|
|Logical Addressing|IP|Due to many hosts in different networks, there is a need to structure the network topology and logical addressing. Within TCP/IP takes over the logical addressing of networks and nodes. Data packets only reach the network where they are supposed to be. The methods to do so are network classes, subnetting and CIDR|
|Routing|IP|For each data packet, the next node is determined in each node on the way from the sender to the receiver. This way, a data packet is routed to its receiver, even if its location is unknown to the sender|
|Error & Control Flow|TCP|The sender and receiver are frequently in touch with other via virtual connection. Therefore control messages are sent continuosly to check if the connection is still established|
|Application Support|TCP|TCP and UDP ports form a software abstraction to distinguish sepecific applications and their communication links|
|Name Resolution|DNS|DNS provides name resolution through Fully Qualified Domain Names (FQDN) in IP addresses, enabling us too reach the desired host with the specific name on the internet|
