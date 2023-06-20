Transmission Control Protocol (TCP) and User Datagram Protocol (UDP) are both protocols used in information and data transmission on the internet. Typically, TCP connections transmit important data, such as web pages and emails. In contrast UDP connections transmit real-time data cusch as streaming video or online gaming

TCP is a connection oriented protocol that ensures that all  data sent from one computer to another is received. It's like a telephone converssation where both parties remain connected until the calls is terminated. If an error occurs while sending data, the receiver sends a message back so the sender can resenf the missing data. This makes TCP reliable and slower than UDP because more time is required for transmission and error recovery.

UDP on the other hand is a connectionless protocol. It's used whrn speed is more important than reliability, such as for video streaming or online gaming. With UDP, there is no verification that the received data is complete and error-free. If an error occurs while sending data, the receiver will not receive this missing data, and no message will be sent back to resend it. Some data may be lost with UDP, but the overall transmission is faster 

## IP Packet

An internet protocol (IP) packet is the data are used by the network layer of the Open Systems Interconnection(OSI) model to transmit data from one computer to another. It consists of a header and the payload, the actual payload data.

We can also think of the IP packet as a letter sent in an envelope. The envelope contains the header, which includes information on the sender and the recipient, as well as instructions for routing the letter, ie via which post offices the letter should be sent. The letter itself is the payload , the actual payload data.

#### IP header
The header of an IP packet contains several fields that have important information.
|Field|Description|
|-|-|
|Version|ndicates which version of the IP protocol is being used|
|Internet Header Length| Indicates the size of the header in 32-bit words|
|Class of service|Means how important the transmission of the data is|
|Total length|Specifies the total length of the packet in bytes|
|Identification (ID)| Is used to identify fragments of the packet in bytes|
|Flags|Used to indicate fragmentation|
|Fragment Offset|Indicate where the current fragment is placed in the packet|
|Time to live| Specifies how long the packet may remain on the network |
|Protocol| Specifies which protocol is used to transmit the data such as TCP or UDP|
|Checksum|Is used to detect errors in the header|
|Source/Destination| Indicate where the packet was sent from and where it's being sent to|
|options|Contains optional information for routing|
|Padding|Pads the packet to a full word length|

We may see a computer with multiple IP addresses in different networks. Here we should pay attention to the IP ID field. It is used to identify fragments of an IP packet when fragmented into smaller parts. It is a 16-bit field with a unique number ranging from 0-65535.

#### Network Sniffing
![[netSniff.png]]
We can see from the output that two different IP addressesare sending packets to IP address 10.129.1.1. However from the IP ID, we can see that the packets are continuous. This is strongly indiciates that the 2 IP addresses belong to the same host in the network

#### IP Record-route Field

The record-route field in the IP header also records the route to a destination device. When the destination device sends back the ICMP Echo Reply packet, the IP addresses of all devices that pass through the packet are listed in the record-route field of the IP header. This happens when we use the following command: 

![[ipRecordroute.png]]

The output indicates that a ping request was sent and a response was recived from the destination evice and also shows the record-route field in the IP header of the ICMP echo rquest packet. The record route field contains the IP addresses of all devices that passed through the ICMP Echo request pacet on the way to the destination device. In this case, the Record route field contains the IP addresses:
![[ips.png]]

The traceroute tool can also be used to trace the route to a destination more accurately, which uses the TCP timeout method to determine when the route has been fully traced.
1. We send a TCP SYN packet to the destination device with a high initial TTL in the IP header.  When the TCP SYN packet reaches a router whose TTL is greater than 1, the value of the TTL is decreased by 1, and the packet is forwarded to the next device. If the TCP SYN packet reaches a router whose TTL is 1, the packet is dropped, and the router sends an ICMP Time-Exceeded packet back to us.

2. We receive the ICMP Time-Exceeded packet and note the IP address of the router that sent the packet.

3. After that, we send another TCP SYN packet to the destination device with a lower TTL.

The process repeats until the TCP SYN packet reaches the destination host and receives a TCP SYN/ACK or a TCP RST response from the target. Once we receive a response from the destination device, we know that we have traced the route to the destination and ended the traceroute process.
IP Payload
The payload (also referred to as IP Data) is the actual payload of the packet. It contains the data from various protocols, such as TCP or UDP, that are being transmitted, just like the contents of the letter in the envelope.

## TCP
TCP packets,also known as segments, are divided into several sections called headers and paloads. The TCP segments are warpped in the sent IP packet
The header contains several fields that contain important information. The source port indicates the computer from which the packet wwas sent. The destination port indicates the order in wich the data was sent.he control flags indicate whether the packet marks the end of a message, whether it is an acknowledgment that data has been received, or whether it contains a request to repeat data. The window size indicates how much data the receiver can receive. The checksum is used to detect errors in the header and payload. The Urgent Pointer alerts the receiver that important data is in the payload.

The payload is the actual payload of the packet and contains the data that is being transmitted, just like the content of a conversation between two people.

## UDP
UDP trasnfers datagrams (small data packets) between two hosts. It's a connectionless protocol, meaning it doesn't need to establish a connection between the sender and the reciever before sending data. Instead the data is sent directly to the target host without any prior connection
When traceroute is used with UDP, we will receive a destination unreachable and port unreachable message when the UDP datagram packet reaches the target device. Generally UDP packets are sent using traceroute on unix hosts
## Blind Spoofing
Blind spoofing is a method of data manipulation attack in which an attacker sends false information on a network without seeing the actual responses sent back by target devices. It involves manipulating the IP header field to indicate false source and destination port numbers and a false initial sequence number (ISN).The ISN is a field in TCP header that is used to specify the sequence number of the first TCP packet in a connection. The ISN is set by sender of a TCP packet and sent to the receiver in the TCP header of the first packet. This is can cause the target host to establish a connection with us without receiveing the connection
This attack is commonly used to disrupt the integrity of network connections or to break connections between network devices. It can also be used to monitor network traffic or to intercept information sent by network devices.




