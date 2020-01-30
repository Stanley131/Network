### principles of network applications
  - same hosts: inter-process communication 
  - different hosts: messages 
  - clients, servers, client process 
  - sockets 
### Adress Processes 
  - IP(Internet Protocol): 32 Bits 0.0.0.0
  - identifier: IP + Port 
    - HTTP: 80 
    - Mail Server: 25 
  - types o messages exchanged: request, reponse  
  - message syntax 
  - message semantics  
  - proprietary protocols: protocol owned by a single entity 
  - **open protocol: defined in RFC, allowed for interoperability** 
    - HTTP, SMTP

### What transport service does an app need?
  - data integrity: 100% file 
  - timing: some apps (e.g., Internet telephony, interactive games) require low delay  
      to be “effective”
  - Throughput is a measure of how many units of information a system can process in a   
      given amount of time.
  - TCP: 
      - reliable transport 
      - flow control: senders won't overwhelm receiver 
      - congestion control: throttle sender when network overloaded
      - connection-oriented: setup required between client and server processess
      - **does not provide: timing, minimum throughput**
      - TCP: SMTP, Telnet(remote terminal access), Web, file Transfer, 
      - TCP or UDP: streaming multimeadia: HTTP Youtube, SIP RTP, Skype 
 
### Securing TCP 
  - SSL (: Secure Sockets Layer): provided TCP connection, data intergraty, end-point authentication 
  - TCP & UDP: no encryption,clear text,no secure 

### Web and HTTP
  - web page consists of objects
  - HTTP: hypertext transfer protocol 
  - HTTP is "stateless": server maintains no information about past client requests
### HTTP Connections  
  - non-persistent HTTP: 
    - At most one obejct sent over TCP connection, then closed 
    - downloading multiple objects required multiple connections
  - persistent HTTP: multiple objects can be sent over single TCP connection between client, server

