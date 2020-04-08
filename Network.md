# Network Layer
1. Goal
  - understand principles behind network layer services, foucusing on
    data plane: 
      - netwrok layers service models 
      - forwarding verus models 
      - how a router works 
      - generalized forwarding
  - instatiation, implementation in the internet 
2. Network layer 
  - transport segment from sending to receiving host
  - on sending side encapsulates segments into datagrams 
  - on receiving side, delivers segments to transport layer 
  - network layer protocols in every host , router 
  - router examines header fields in all IP diagrams passing though it

3. Two key network-layer functions 
  - network-layer functions:
    - forwarding: move packets from routers' input to appropriate router output 
    - routing: determine route taken by packtes from source to destination 
4. Network layer: data plane, control plane 
  - data plane: 
    - local, per-router funcntion
    - determines how datagram arriving on router input port is forwarded to router 
      output port.
    - forwarding function 
  - control plane 
    - network-wide logic 
    - determines how datagram is routed among routers along end-end path from source 
      host to destination host to detination host 
    - two control-plne approached: 
      - traditional routing algorithms 
      - software-defined networking 
      - (SDN): implemented in remotes servers
     - Per-router control plane 
        - individual routing algorithm components in each and every router inteact in
           the control plane 
     - A distinct (typically remote) controller interacts with local control agents
        (CAs)
     - Network Service model: 
        - example services for individual datagrams: 
            - guaranteed delivery 
            - guaranteed delivery with less than 40 mesc delay 
         - example services for a flow of datagrams: 
            - in-order datagram deivery 
            - guarenteed minimum bandwidth to flow 
            - restrictions on changes in inter-packets spacing. 
            
### 2. The Data Plane
1. DHCP: Dynamic Host Configuration Protocol 
  - Dynamically obtain its IP address from network 
  - Can renew its lease on address in use 
  - allows reuse of addresses 
  - suppoet for mobil users who want to join network
2. DHCP client-server scenario 
  - new arriving client broadcasts a msg
  - example: 0.0.0.0, 68, dest: 255.255.255.67 yiaddr: 0.0.0.0  transactionID:654
  - DHCP server reply msg: DHCP offer: src:233.1.2.5.yiaadrr: 233.1.2.4 lifetime:3600 secs
  - DHCP request: src: 0.0.0.0, 68, dest: 255.255.255.255, 67, yiaddrr: 233.1.2.4 
  - DHCP ACK: src: 233.1.2.5, 67 dest: 255.255......
  - 2RRT, timeout in an hour and reusability 
3. DHCP: more than IP addresses： 
  - DHCP：can retuen more than just allocated IP address on subnet 
  - address of first-hop router of client 
  - name and ip address of DNS server 
  - network mask 
4. DHCP: example 
  - Router with DHCP server built into router 
5. DHCP: Wireshark output (home LAN)
  - can look at DHCP output 
6. Hierachical Addressing: route aggregation
  - 200.23.16.0/20
  - 200.23.18.0/23
  - different ISPs
  - How ISP get block of addresses?
  - ICANN: internet Corporation Asssignrf Nanees and Numbers:
7. NAT: network address translation
  - One router, one IP, then why many devices?
  - Port Number
  - NAT Translation Table: LAN side addr <--> WAN side addr
  - 10.0.0.1, 3345  <--> 138.76.29.7, 5001
  - Firewall is different from NAT
  - port number 16-bit 
8. IPv6: motivation
  - priority: identify priority among datagrams in flow
  - flow Label: identify datagrams in samme "flow."
  - next header: identify upper layer protocol for data. 
9. other changes from IPv4
  - Checksum: removed entirely to reduce processing time at 
    each hop 
  - options: allowed, but outside of header, indicated by "Next
    Header" field
  - ICMPv6: new version of ICMP

10. Translation from IPv4 to IPv6 
  - tunneling: IPV6 datagram carried as payload in Ipv4 datagram
    among Ipv4 routers 
  - example: UPv4 tunnel connectiong Ipv6 routers 

11. IPv6: adoption
  - 8% of clients access servers vua Ipv6 
  - still having maximun data fragment 
  - it has a larger header 
  
  
  
  
  
  
  
  
  
  
  
            
            
            
            
            
            
            
            
            
            
            
            
            
            
            
            
            
            
            
            
            
            
            
            
            
            
            
            
            
            
        
