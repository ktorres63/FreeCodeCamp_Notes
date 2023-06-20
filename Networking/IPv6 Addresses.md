
IPv6 is the successor of IPv4. In contrast to IPv4, the IPv6 address is 128 bit long. The prefix identifies the host and network parts. The Internet Assigned Numbers Authority (IANA) is responsible for assigning IPv4 and IPv6 addresses and their associated network portions. In the long term, IPv6 is expected to completely replace IPv4, which is still predominantly used on the Internet. In principle, however, IPv4 and IPv6 can be made available simultaneously (Dual Stack).

IPv6 consistently follows the end-to-end principle and provides publicly accessible IP addresses for any end devices without the need for NAT. Consequently, an interface can have multiple IPv6 addresses, and there are special IPv6 addresses to which multiple interfaces are assigned.
IPv6 is a protocol with many new features, which also has many other advantages over IPv4:

Larger address space
Address self-configuration (SLAAC)
Multiple IPv6 addresses per interface
Faster routing
End-to-end encryption (IPsec)
Data packages up to 4 GByte
![[ipv6.png]]

There are 4 different types of IPv6 addresses
![[ipv6_1.png]]

In total, the IPv6 address consists of 16 bytes. Because of its length, an IPv6 address is represented in a hexadecimal notation. Therefore the 128 buts are divided into 8 blocks multiplied by 16 bits (or 4 hex numbers). All 4 hex numbers are grouped and separated by a colon (:) instead of a simple dot (.) as in IPv4.
To simplify the notation we leave out leading at leas 4 in the blocks and we can replace them with 2 colons (::)
An IPv6 address can look like this:

+ Full IPv6: fe80:0000:0000:0000:dd80:b1a9:6687:2d3b/64
+ Short IPv6: fe80::dd80:b1a9:6687:2d3b/64

An IPv6 address consists of 2 parts
+ Network prefix (network part)
+ Interface Identifier also called suffix (host part)
The Network Prefix identifies the network, subnet, or address range. The Interface Identifier is formed from the 48-bit MAC address (which we will discuss later) of the interface and is converted to a 64-bit address in the process. The default prefix length is /64. However, other typical prefixes are /32, /48, and /56. If we want to use our networks, we get a shorter prefix (e.g. /56) than /64 from our provider.

In RFC 5952, the aforementioned IPv6 address notation was defined:

+ All alphabetical characters are always written in lower case.
+ All leading zeros of a block are always omitted.
+ One or more consecutive blocks of 4 zeros (hex) are shortened by two colons (::).
+ The shortening to two colons (::) may only be performed once starting from the left.