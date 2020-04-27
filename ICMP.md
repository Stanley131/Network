### 1. ICMP
- internet control message protocol
- used by hosts and routers to communication network-level information 
### ICMP Packet format 
- the ICMP is encapsualted in IP datagram. The packet consists of header and data sections 
- All ICMP packets have an 8-byte header and variable-sized data session. the first 4 bvytes 
of the header have fixed format, while the last 4 bytes depend on the type/code of the that ICMP packet. 
- After IP datagram: type, code, checksum, content 
- ICMP message: type, code, plus first 8 bytes of IP datagram causing error
### Traceroute adn ICMP 
- source sends series of ICMP packets to destination 
- TTL expired(port unreachable) or arrived 
