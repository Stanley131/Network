### Delay
  - processing + queue + transmission + propagation 
  - traceroute: 
  - packet loss: packet arriving to full queue dropped
  - throughput 
  
 ### Layer: 
  - application: FCP SMTP, HTTP 
  - transport: TCP UDP 
  - Network: routing of datagrams from source to destinations 
  - link: data transfer between neigboring network elments 
  - physical: bits on the wire 
   
  ISO  
  - application => presnetation => session => ...  
  - presentation: allow applications to interpret meaning of data, e.g.,   
      encryption, compression, machine-specific conventions
  - session: synchronization, checkpointing, recovery of data exchange  
  
### network Security 
  - DoS: denial of Service 
  - packet “sniffing” 
  - IP spoofing: send packet with false source address
  -  DSLAM (Digital Subscriber Line Access Multiplexer)
### ISP 
  - end systems <=> ISP <=> IXP <=> ISP <=> end systems 
  - Content provider network (Google ...)
  - Tier 1 ISP + Google ISP 
    - IXP Reginal ISP 
    - 

### Delay 
  - dnodal = dproc + dqueue + dtrans +  dprop
  - Transmission delay is how long it takes to get all the bits into the wire in the first   
    place (it's packet_length/data_rate)  
  - The propagation delay, is the time it takes a bit to propagate from one router to the next  
  

