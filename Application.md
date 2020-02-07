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
       - top-level DNS servers 
       - indivudal DNS servers 
       - 13 logical root servers worldwide (Each servers replicated manytimes)
          - DNS root: contracted by local name serber that cannot reslve name 
          - root name server: 
            - contacts authoritative name server if name mapping not known
            - gets mapping 
            - returns mapping to local name server 
          - top-level domain servers: 
            - responsible for com.,org, edu, aero, jobsm museums, and top-level 
              cuntry domains, such as uk, fr, ca,ip 
             - netweok solutions maintains servers for .com 
             - educations for .edu TLD 
          - authoritative DNS servers: 
             - organization's own DNS servers, providing authoriative hostname to IP mappings organiztion's named hosts 
             - can be maintained by organization or service provider
             
           - iterative query: client => local server => (root DNS server, TLD, authoritative DNS server)
           - recursive query: client <=> local <=> root <=> TLD <=> authoritatoive 
        - Once (any) name server learns mapping, it caches mapping 
        - cached entries may be out-of-date 
          - if name host changes IP address, may not be known internet-to-adress util all TTLs expire 
          - update/notify mechanisms proposed IRTF standard 
        - DNS record: distributed database storing resource records (RR)
          - (name, value, type, ttl)
          - type=A: name value
          - type=NS: name, value is hostname of authoritative name server for this domain 
          - type= CNAME: name is alias name for some "canonical" the real name 
            - www.ibm.com is really servereast.backup2.ibm.com
            - value is canonical name
          - type=MX: value is name of mailserver associated with name 
        - DNS protocol, messsage 
          - identidication: 16 bit for query, reply top query uses same # 
        - flags: 
          - query or reply 
          - recursion desired 
          - resursion avaiable 
          - replay is authoritative 
        - insert records into DNS: 
          - example: new startup "Newwork Utopia"
          - register name networkuptopia.com at DNS registrar 
            - provide names, IP addresses of authoritative name server (primary and secondary)
            - registrar inserts two RRs into .com TLD server:(networkutopia.com, dns1.networkutopia.com, NS) (dns1.networkutopia.com, 212.212.212.1, A)
            - create authoritative server type A record for www.networkuptopia.com; type MX record for networkutopia.com
        - Attack DNS: 
          - bombard root servers 
          - bombard TLD servers 
          - redirect servers
          - exploit DNS for DDos 
        




          
   
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  

