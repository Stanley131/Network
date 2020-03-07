### Transport-layer Services
  - provide logical communication between app processes running on different hosts 
  - transport protocols run in end systems 
  - more than one transport protocols avaliable to apps 
  - transport vs network layer 
      - network: logical communication between hosts 
      - transport:  logical communication between processes 
  - mutiplexing at senders, demultiplexing at receivers
      - hosts use IP && Port Numbers to direct segmebt to appropriate socket 
      
 ### reliable transfer over a reliable channel
  - underlying channel perfectly reliable
      - no bit errors
      - no loss of packets
      - checksum to detect errors 
  - rdt2.0 
      - ACKs: pkt OK
      - NAK: pkt errors
      - rdt1.0 + feedback 
      - fatal flaw: if ACK/NAK corrupted 
  - rdt3.0 
      - new assumption: lose packets 
      - approach: sender waits  "reasonable" amount of time 
      - retransmits if no ACK received in this time
      - if pkt (or ACK) just delayed (not lost):
          - retransmission will be  duplicate, but seq. # already handles this
          - receiver must specify seq # of pkt being ACKed
      - requires countdown timer
      - rdt3.0 is correct, but performance stinks

### Pipelined Protocols: increaed utiliztion
      - sender allows multiple, “in-flight”, yet-to-be-acknowledged pkts
      - range of sequence numbers must be increased
      - buffering at sender and/or receiver
      - go-Back-N and selective repeat 
   - Go-back-N
      - sender can have up to N unacked packets in pipeline
      - receiver only sends cumulative ack doesn’t ack packet if there’s a gap
      - sender has timer for oldest unacked packet when timer expires, retransmit all unacked packets
    - Selective Repeat
      - sender can have up to N unack’ed packets in pipeline
      - rcvr sends individual ack for each packet
      - sender maintains timer for each unacked packet
      - when timer expires, retransmit only that unacked packet
    - Go-Back-N: sender
      - k-bit seq # in pkt header
      - “window” of up to N, consecutive unack’ed pkts allowed
      - ACK(n): ACKs all pkts up to, including seq # n - “cumulative ACK”
      - timer for oldest in-flight pkt
      - timeout(n): retransmit packet n and all higher seq # pkts in window
    - GBN: receiver 
      - ACK-only: always send ACK for correctly-received pkt with highest in-order seq #
      - may generate duplicate ACKs
      - may generate duplicate ACKs
      - out-of-order pkt: 
    - Selective Repeat 
      - receiver individually acknowledges all correctly received pkts
      - buffers pkts, as needed, for eventual in-order delivery to upper layer
      - sender only resends pkts for which ACK not received
      - sender timer for each unACKed pkt
      - sender window, N consecutive seq #’s, limits seq #s of sent, unACKed pkts
      - what relationship between seq # size and window size to avoid problem in (b)?


### TCP 
  - point-to-point
  - reliable, in-order byte stream
  - pipelined 
  - full duplex data, maximum segment size (MSS)
  - connection-oriented: handshaking (exchange of control msgs) inits 
    sender, receiver state before data exchange
  - flow controlled: sender will not overwhelm receiver

### TCP segment structure 
  - URG: urgent data (generally not used
  - ACK: ACK # valid
  - sequence numbers: byte stream “number” of first byte in segment’s data
  - seq # of next byte expected from other side
  - cumulative ACK

### How to set timeout time?
  - longer than RTT but RTT varies
  - too short: premature timeout, unnecessary retransmissions
  - too long: slow reaction to segment loss
  - SampleRTT: measured time from segment transmission until ACK receipt
  - SampleRTT will vary, want estimated RTT “smoother” average several 
     recent measurements, not just current SampleRTT
  - EstimatedRTT = (1- alpha)*EstimatedRTT + *SampleRTT
  - timeout: timeout interval: EstimatedRTT plus “safety margin”
        - large variation in EstimatedRTT -> larger safety margin
        - estimate SampleRTT deviation from EstimatedRTT: 
        - TimeoutInterval = EstimatedRTT + 4*DevRTT
### TCP reliable data transfer
  - TCP creates rdt service on top of IP’s unreliable service
      - pipelined segments
      - cumulative acks
      - single retransmission timer
  - retransmissions triggered by:
      - timeout events
      - duplicate acks   
  - TCP sender: 
      - create segment with seq #
      - seq # is byte-stream number of first data byte in  segment
      - start timer if not already running 
      - think of timer as for oldest unacked segment
      - timeout: retransmit segment that caused timeout. restart timer
      - premature timeout: timeout earily 
   - TCP fast retransmit 
      - if sender receives 3 ACKs for some data, 
      - likely, that unacked segment lost, so don't wait for timeout 
      - receiver “advertises” free buffer space by including rwnd value
          in TCP header of receiver-to-sender 
      - segments: RcvBuffer size set via socket options (typical default is 
         4096 bytes) many operating systems autoadjust RcvBuffer
   - sender limits amount of unacked (“in-flight”) data to receiver’s rwnd value.
   - guarantees receive buffer will not overflow. 

### Connection Magagement
  - before exchanging data, sender/receiver “handshake”:
     - agree to establish connection (each knowing the other willing to establish connection)
  - agree on connection parameters
  
      


 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
