### traceroute 
  - a hop: a hop count is the total number of intermediate devices such as routers through which a 
    given piece of data must pass between the source and destination。 
  - ICMP (Internet Control Message Protocol)
  - Good Source: https://www.maxcdn.com/one/tutorial/how-to-read-a-traceroute/
  

### whois 
  - tell everything about an IP 

### telnet
  - telnet hostname
  - telnet ip-address port number
  - close 
  - ?
  - display argument 
  - environ argument 
  - logout 
  - mode type 
  - quit 
  
  - example sending email: 
    - telnet example.com 25 
    - helo example.com
    - mail from: username@example.com
    - rcpt to: friend@hotmail.com, friend@yahoo.com
    - data
    - Subject: My Telnet Test Email 
    - Hello, 
    - This is an email sent by suing telnet command 
    - Your friend, 
    - Me 
    - . 
    - quit 
   - example read email 
    - telnet example.com 110 
    - user username@example.com
    - pass yourpassword@example.com
    - list 
    - retr 2
    - dele 1
    - quit 
 


### ping 
  - ping ip
### FTP
  - ftp IP  (FTP is unencrypted, ssh is encrypted)
    - username 
    - password 
    
