### 1. SDN
- tranditional network layer implemented via distribution, per-router apparoah 
- renewed interest in rethinking network control plane 
- Recall: per-router control plane, individual routing algorithm components in each and every router innteract with each other in control plane to compute forward tables
- SDN compute tables and send to routers 
### 2. why centralized control plane?
- easier network management: avoid router, misconfigurations, greater flexibility of traffic flows
- table-based forwarding: centeralized idea is easier for compuations, distributing program is hard
- Open(non-proprietary) implementation of control plane 
- buy SDN switch and just program it instead of changing the whole hardwares. 
### 3. Difficulties in traditonal routing
- cannot distiguish between paths 
- loading balance, flooding one path 
### 3. SDN 
- 1. generalized flow-based forwarding 
- 2. control data plane separation 
- 3. control plane functions external to data-plane switches 
- 4. programmable control applications 
### 4. SDN: data plane switches 
- fast, simple, commodity switches implementing generalized data-plane forwarding in hardware 
- switch flow table computed installed by controller 
- API for table-based switch control 
- protocol for communicating with controlle
### 5. SDN persepctive: SDN controller (netowrk OS)
- 
