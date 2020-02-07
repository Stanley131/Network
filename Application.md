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
  
### EMAIL 
  - Three major components: user agents, mail servers, and SMTP 
  - User agent: editing, reading, wrinting email, Iphone mail client, outgoing messages 
  - SMTP: between mail servers to send mail
  - default port: 25 
  - three phases of transfer: handshaking, transfer of messages, closure 
  - Command/Response interactrion like HTTP 
  - TCP between servers 
  - SSMP tool, telnet 
    - To： 
    - From: 
    - Subject: 
   - SMTP: MSG store in servers 
   - POP (RFC 1939): authorization, downalod
   - IMAP: Internet Mail Access Protocol [RFC 1730]: more features, including manipulation of stored masseges on server
   - HTTP: gmail, Hotmail
   - POP3: authorization phase and transiaction phase 
      - Deleted after download, 
### DNS 
  - Internet, hosts, routers 
  - Domain Name System: 
    - distributed database, implemented in hierarchy of many name servers 
    - application-layer protocol: hosts, name servers communicate to resolve names.
    - DNS Services: 
        - IP and hostname translation 
        - host aliasing 
        - mail server aliasing 
        - load distribution 
     - why not centralize DNS 
        - single point failure 
        -  traffic volume 
        - distant centralized database 
        - maintainance 
        - does't scale 
     - A distributed, hierachical database 
       - Root DNS Servers 
       - top-tier DNS servers 
       - 
   
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  

