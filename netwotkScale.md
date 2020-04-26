1. Idealized so far 
  - all routers are identical 
  - network flat 

2. scale 
  - cannot store all destinations in routing tables 
  - routing tables exchange would swamp links 
3. Scale Appraoch 
  - Aggregate routers into regions known as "autonomous system"(AS, aka, domains)
  - Intra-AS routing 
     - routing among hosts, routers, in same AS ("network")
     - all routers in AS must run same intra-domain protocol 
     - routers in different AS can run different intra-domain routing protocol 
     - gateway router: at "edge" of its own AS, has links(s) to routers in other AS'es 
  - Inter-AS 
    - routing among AS'es 
    - gateways perform intern-domain routing (as well as intra-domain routing)
  - Interconnected ASes 
4. Inter-AS tasks 
  - how to determine which AS to forward?
    - job of inter-AS routing 
5. Intra-AS routing 
  - alse known as interior gateway protocols (IGP)
  - most common intra-AS routing protocols 
    - RIP: routing Information protocol
    - OSPF: open shortest path first(IS-IS protocol essentially same as OSPF)
    - IGRP: Interior Gateway Routing Protocol 
6. OSPF 
  - "open": publicly avaliable 
  - uses link-state algorithm 
    - topology map at each node 
    - route computation using Dijkstra's algorithm 
    - routers flood OSPF link-state advertisements to all other 
  - advanced features 
    - security: all OSPF msgs authenticated to prvent malicious intrsions 
    - multiple same-cost paths allowed (only one path in RIP 
    - for each link, multuple cost metrics for different TOS(tyep of services)
  - intergrated uni- and multi-cast support 
  - hierarchical OSPF in large domains 
  - Hierachical OSPF: boundary router -> backbone router 
6. Routong among the ISPs: BGP 
  - Internet inter-AS routing: BGP
  - BGP: border gateway protocol: glue that holds the internet together 
  - BGP provides each AS a means to: 
    - eBGP: obtain subnet reachability information to all AS-internal routers 
    - iBGP: propagate reachability iformation to all AS-internal routers 
    - determine "good"(not least cost) routers to other networks based on reachability information and policy 
    - allow subnet to advertise its existence to rest of internet: "I am here."
  - eBGP between ASs, iBGP: inner ASs
7.BGP basics
  - BGP Sessions: two BGP routers ("peers") exchange BGP messages over semi-permanent TCP connection: 
    - advertising paths to different destination network prefixes
    - AS will promise other ASes to forward to its inner routers 
    - gateway router may learn about multitple paths to destination:  choose least number of ASes' path 
8. BGP megs 
  - BGP megs exhcnaged betweren peers over TCP connection 
  - BGP: Open, update, keepalive, notification
  - BGP, OSPF, forwarding table entries 
  - BGP route selection 
    - router may learn about more than one route to destination AS, selects route based on: 
    - local prefrence value attribute: policy decision, shortest AS-PATH, closest NEXT-HOP router: hot potato routing, additional criteria
  - Hot Potato Routing: choose local gateway that hs least intra-domain cost. 
  - BGP: achieving policy via advertisements: choose not to advertise, dual-homed
9. Why different Intra-, Inter-AS routing?
  - policy: 
    - inter-AS: admin wants control over how is traffic routed, who routes through its net 
    - intra-AS: single admin, so no policy decisions needed 
  - Scale: 
    - hierachial routing saves table size, reduced update traffic 
  - Performance:  
    - Intra-AS: can foucs on performance 
    - Inter-AS: policy may dominate over performance 
    
    
  
  
  
  
    
  







