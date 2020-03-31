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
5. What is inside a router?
   -  
            
            
        
