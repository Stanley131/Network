### 1. Link Layer and LAN
- terminology: 
    - nodes: hosts and routers 
    - links: communication channels that connect adjacent nodes along communication paths
        - wired links 
        - wireless links 
        - LANs 
    - Layer-2 packet: frame, encapsulate datagram 

### 2. Recap: encapsulation 
- Data (application layer) -> header+data(Transport Layer) ->  IP Header+ header+ data(Network layer) -> frame header + x + frame footer (link layer)
- reverse: decapsulation 

### 3. LInk layer services
- frame, link access: 
   - encapsulate datagram into frame, adding header, trailer 
   - channel access if shared medidum 
   - "MAC" addresses used in fram headers to identify source, destinations (media access control address)
- reliable delivery between adjacent nodes 
  - we learned how to do this already in transport layer 
  - why again： 1. middle point check to improve efficiency. 2. more error check 
  - seldom used on low bit-error link(fiber, some twisted pair)
  - wireless links: high error rates
### 4. Where is the link layer implemented?
- In each and every host, link layer implemented in "adaptor" aka network interface card NIC or on a chip 
- attaches into host's system buses 
- combinnation of hardware, software, fireware

### 5. Adaptors commnicating
- Sending side: encapsualting datagram in frame
- Adds error checking bits, rdt, flags, etc 
- receive side: looks for errors, rdt, flags, 

### 6. Error detection 
- error detection not 100% reliable 
- Single bit parity 
- two-dimensional bit parity: 4 bit error, might not 

### Internet Checksum
- goal: detect "errors" in transmitted packet (Note: used at transport layer only)
- sender: 
- reveiver: 




