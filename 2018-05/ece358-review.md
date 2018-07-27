# Notes taken in an attempt to pass ECE 358

In which I go through every slide and consciously summarize it.

## Chapter 1: Introduction

- 1: Presented by Dr. Albert Wasef
- 2: -
- 3: Chapter 1 roadmap
- 4: Nuts-and-bolts view of the internet
  - It consists of:
    - Hosts running network apps
    - Communication links (including fiber, copper, radio, and satellite)
    - Packet switches (routers and switches)
- 5: Fun internet appliances
- 6: Nuts-and-bolts view (2)
  - Internet standards are made by:
    - RFC: Request for Comments
    - IETF: Internet Engineering Task Force

- 7: Service view
- 8: A protocol is a definition of what messages mean and how they should be
  handled.
- 9: -
- 10: -

- 11. Network structure
  - Network edge: Consists of hosts (clients and servers)
  - Access networks and physical media: Communication links
  - Network core: Interconnected routers that form a network of networks.

- 12. Access networks
  - They're how end systems are connected to an edge router.
  - Three types: Residential, Institutional, and Mobile
  - We will talk about DSL and Cable
- 13. DSL access networks
  - Uses the telephone line to transmit data
  - DSLAM: DSL access multiplexer that decides whether the signal is passed on
    to the ISP or the telephone network
  - Max speeds: 2.5 Mbps up, 24 Mbps down
- 14. Cable access networks
  - FDM: Frequency division multiplexing.
  - 15.
    - HFC: Hybrid fiber coax. Mixed fiber optic and coaxial cable that attaches
      homes to ISPs.
- 16. Home network
- 17. Enterprise access networks: Often use ethernet switches
- 18. Wireless access networks
  - Wireless LAN: Wifi. Typically within building.
  - Wide-area wireless access: Cell signal. 10s of km. 3G, 4G.

- 19. Host sending
  - L: Packet length (bits)
  - R: Transmission rate (bits/sec)
  - Transmission delay = L/R (sec)
- 20-22. Physical media includes coaxial cable, fiber optic, and radio
- 23. -
- 24. Network core: Uses packet switching.
- 25. Packet switching
  - "Store and forward": The entire packet must arrive before it can be
    transmitted to the next link.
- 26. Queueing and loss
  - Packets can be dropped if a queue is full
- 27. Routing and forwarding
  - [Routing] is determining the route that should be taken by packets
  - [Forwarding] is actually forwarding the packets
- 28. Circuit switching
  - Resources are reserved end-to-end for a dedicated connection between two
    end hosts
  - 29. FDM vs TDM:
    - Frequency division vs. time division
- 30. Packet vs. circuit switching
  - Packet switching allows more users to use the network
  - 31. Packet switching allows for congestion
  - Packet switching is simpler

- 32. Internet structure
- 33. How do we connect millions of access ISPs?
- 34. O(N²) doesn't scale
- 35. Global ISP? Too hard to coordinate
- 36. Multiple Tier-1 ISPs? Okay
- 37. Now just add IXPs (internet exchange points) and peering links (inter-ISP
      links) to interconnect those Tier-1 ISPs
- 38. Sprinkle some regional networks under each Tier-1 ISP
- 39. Add some CDNs because companies want more speed
- 40. And that's the internet!
- 41. Sprint: example of Tier-1 ISP
- 42. -
- 43. Loss and delay happen because routers are buffers and switching takes time
- 44-45: dproc, dqueue, dtrans, and dprop
- 46: Caravan analogy of packets
- 47. -
- 48. Queueing delay
  - R: Link bandwidth (bps)
  - L: Packet length (bits)
  - a: Average packet arrival rate (Hz)
  - Queueing delay depends on La/R.
    - 0: small
    - →1: large
    - >1: infinite
- 49. Packet loss: Happens if finite-length queue is full when packet arrives
- 50. Real delays and routes with traceroute
- 51. Traceroute example
- 52. Throughput is bits/sec, can be instantaneous or average
- 53. Throughput example. Bottleneck is smallest throughput.
- 54. Throughput example 2. Effective throughput of pipe with n users is R/n.

- 55. -
- 56. Protocol layers motivation
- 57. Air travel analogy
- 58. Air travel analogy part 2
- 59. Layers are good because they make things explicit, easier to maintain,
      and easier to update
- 60-61. Internet protocol stack
  - Application
  - "PrEsEnTaTiOn"
  - "SeSsIoN"
  - Transport
  - Network
  - Link
  - Physical
  - Presentation and session are fake layers that are really part of
    Application
- 62. Encapsulation is wrapping layer on top of each other

- 63. -
- 64. Network security is important
- 65. Bad guys
  - Virus: self-replicates by being actively executed
  - Worm: self-replicates by being passively executed
  - Spyware: smuggles your measurements to some server
  - Botnet: what your computer can become a part of
- 66. DoS attack: coordinated flood to overwhelm server
- 67. Packet sniffing
  - Broadcast media especially vulnerable
  - Wireshark is one
- 68. IP spoofing: you can send packets with fake source addresses

- 69. -
- 70-74: History that probably won't be on the exam
  - 1961-1972: early packet switching
    - 1961: Queueing theory by Kleinrock
    - 1969: First ARPAnet node
    - 1972: ARPAnet public demo w/ 15 nodes
  - 1972-1980: Internetworking
    - 1979: ARPAnet has 200 nodes
  - 1980-1990: New protocols
    - 1982: SMTP
    - 1983: TCP/IP
    - 1983: DNS
  - 1990-2000: Browsers and the .com bubble
  - up to now: Internet is suddenly everything

## Chapter 2: Application layer

- 1. Presented by Dr. Albert Wasef
- 2. -
- 3. -
- 4. Examples of network apps
- 5. Network apps are apps that communicate over the network
- 6. Client-server and P2P are things
- 7. Client-server: is a thing
- 8. P2P: is also a thing
- 9. Process communication
  - IPC: inter-process communication
  - Client process: Initiates communication
  - Server process: Waits to be contacted
  - P2P apps have client and server processes
- 10. Sockets: are like doors
- 11. Addressing processes
  - IP address and port number oughta do it

- 12. Application protocols define message types, syntax, semantics, and
      processing rules, and can be open or proprietary
- 13. Transport services apps may need
  - Data integrity
  - Throughput
  - Timing
  - Security
- 14. Examples
- 15. TCP vs. UDP
- 16. TCP for reliability, UDP for low ping or media streaming (bitrate
      requirement)
- 17. SSL provides encrypted TCP connections
- 18. -
- 19. Websites refer to objects like images
- 20. HTTP
- 21. ... is on TCP port 80
- 22. ... connections can be persistent or non-persistent
  - 23-25. Non-persistent example
  - 26. Persistent example
- 27-28. HTTP request format
- 29. POST vs GET for uploading data
- 30. HTTP/1.0 vs. HTTP/1.1
- 31. HTTP response
- 32. HTTP status codes:
  - 200: OK
  - 301: Moved permanently
  - 400: Bad request
  - 401: Unauthorized
  - 403: Forbidden
  - 404: Not found
  - 505: HTTP version not supported
- 33. You can use telnet as a browser!
- 34-36. Cookies are used to keep "state" on the client that's transmitted
  every time
- 37-38. Web caches cache websites
- 39-42: Web cache example calculations
- 43. Conditional GET
  - Use the If-modified-since: header
  - Server may then respond with 304: Not modified

- 44. -
- 45. DNS is a distributed database that maps names to IP addresses
- 46. The Four DNS Services are:
  - Host→IP address translation
  - Host aliasing
  - Mail server aliasing
  - Load distribution
- 47. DNS is a hierarchy with root servers at the top
- 48. Root servers are contacted by local servers that can't resolve a name,
      and contact the authoritative name server if they don't know either
- 49.
  - TLD servers: Are responsible for TLDs
  - Authoritative DNS servers: Are an organization's own DNS servers
- 50. Local DNS name server: Caches results for you
- 51-52: Iterated vs. recursive queries
- 53. Caches must be updated. RFC 2136 is a proposed mechanism to do that
- 54. DNS resource records are in the format (name, value, type, ttl)
  - Example: (blah.com, 69.69.69.69, A)
- 55-56. DNS protocol is in the format questions, answers, authority, additional
      info
- 57. DNS registration example
- 58. Attacking DNS
  - DDOS
  - Redirect attacks, DNS poisoning where you send bogus replies to poison caches

## Chapter 3: Transport layer

- 1. Presented by Dr. Albert Wasef
- 2. goals
- 3. -
- 4. Transport layer goals
- 5. Whereas the network layer connects hosts, the transport layer connects
     processes. Household analogy.
- 6. TCP provides reliable, in-order delivery. UDP is fast.

- 7. -
- 8. Data is multiplexed at the sender and demultiplexed at the receiver
- 9. How demultiplexing works: it's based on IP and port, bruh
- 10-11. Connectionless demux: For UDP. Socket based only on dest IP/port.
- 12-14. Connection-oriented demux: For TCP. Socket based on src AND dest IP/port.

- 15. -
- 16. UDP
- 17. UDP segment header has only src port, dest port, length, and checksum
- 18. UDP checksum is one's complement sum of 16-bit segment chunks
- 19. UDP checksum example

- 20. -
- 21-24. Reliable data transfer
  - We must implement `rdt_send` and `rdt_rcv` in terms of `udt_send`
- 25. And we'll do it using FSMs
- 26. rdt1.0: You just assume the channel is reliable and you're done
- 27-28. rdt2.0
  - Bit errors but no loss.
  - Receiver responds with ACKs and NAKs.
  - 29. FSM
  - 30-31. FSM example operation
  - 32. This doesn't work because ACK/NAK may be corrupted
- 33-34. rdt2.1 FSMs
  - Fixes rdt2.0 by adding sequence numbers
  - 35. Discussion
- 36. rdt2.2
  - Instead of NAK, tag ACK with sequence number
  - 37. FSM
- 38. Now loss can also happen
  - Timeouts seem reasonable
  - 39. Sender FSM
  - 40-41. Example
  - 42. Performance calculation.
  - 43. Performance is bad because stop-and-wait.

- 44. Pipelined protocols: GBN and SR
  - 45. They increase utilization
- 46. GBN vs SR
- 47-49. GBN FSM
- 50. GBN example
- 51-53. SR definition
- 54. SR example
- 55. SR dilemma: Sequence number space needs to be at least twice the size of
      the window, or duplicate data can be accepted.
- 56. Performance
  - Utilization `U = min(1, W * tI / tT)`
    - Where `tT` is time from sending a frame to receiving an ACK
    - and `tI` is time to transmit one frame

- 57. -
- 58. TCP
- 59. TCP segment structure
- 60-61. TCP sequence numbers and ACKs
- 62-64. TCP timeout is set by EstimatedRTT + 4*DevRTT
  - Where EstimatedRTT is an EWMA of sampled RTTs with α=0.125
  - And DevRTT is an EWMA of how much sampled RTTs differ from EstimatedRTT,
    with β=0.25

- 65. -
- 66. TCP reliable data transfer
  - Involves:
    - Pipelined segments
    - Cumulative ACKs
    - Single retransmission timer
  - Retransmissions triggered by:
    - Timeouts
    - Duplicate ACKs
- 67. TCP sender events: are data received, timeout, and ACK received
- 68. simplified TCP sender FSM
- 69-70. TCP retransmission scenarios
  - Lost ACK
  - Premature timeout
  - Cumulative ACK

- 71. TCP ack generation table
- 72-73. TCP fast retransmit: Triple duplicate ACKs cause immediate retransmission

- 74. -
- 75. TCP flow control
- 76. ... is done using rwnd (receiver window)
  - Sender limits amount of unacked in-flight data to rwnd

- 77. -
- 78. TCP connection management
  - A handshake establishes a connection
- 79. 2-way handshake doesn't always work
- 80. 2-way handshake failure scenarios
  - If client retransmits `req_conn` early and it arrives after the connection
    finishes, there can be a half-open connection with no client
  - This can be even worse if data also arrives after the duplicate `req_conn`
- 81. 3-way handshake works
  - SYN, SYNACK, ACK
  - Intermediate SYN SENT state for client and SYN RCVD state for server
- 82. 3-way handshake FSM
- 83. Closing a connection: FIN, FINACK, ACK
  - 84. Example

- 85. Congestion control principles
  - 86. -
  - 87. Scenario 1: Shows that a congested network can result in large queueing
        delay with an infinite queue
  - 88-93. Scenario 2: Shows that a congested network can result in lost
    packets with a finite queue, and wasted bandwidth due to retransmissions
  - 94-95. Scenario 3: Shows that with multiple routers, congestion can result
    in even more wasted network effort, since upstream transmission capacity is
    wasted whenever a packet is dropped

- 96. Congestion control approaches
  - End-to-end: This is TCP. No feedback from network, only inferred from loss
    and delay observed by the end hosts.
  - Network-assisted: Routers provide feedback. Can be a single bit indicating
    congestion, or an explicit rate that senders should send at.

- 97. -
- 98. TCP congestion control
  - Based on additive increase, multiplicative decrease
- 99. cwnd is used to dynamically adjust the sending window size
- 100. TCP slow start
  - At the beginning of the connection, increase rate exponentially until loss
    to quickly ramp up
- 101. Reacting to loss
  - Upon timeout: set cwnd = 1 MSS and grow exponentially
  - Upon triplicate ACK:
    - RENO cuts cwnd in half then grows linearly
    - Tahoe sets cwnd to 1 and does slow start
- 102. ssthresh variable represents when the increase should switch from
       exponential to linear
- 103. TCP congestion control state machine
  - 104. Scenario

- 105. TCP throughput is 3/4 W/RTT on average
- 106. Future of TCP:
  - New kinds of TCP are needed for fat long pipes
- 107. TCP fairness
  - TCP congestion control is fair since N TCP connections sharing a link of
    bandwidth R will eventually converge to using R/K each
- 108. Chart that demonstrates the above
- 109. More about fairness
  - Multimedia often uses UDP for constant bitrates
  - Parallel TCP connections can get you more of the pipe

- 110. Summary

## Chapter 4: Network layer

- 1. Presented by Dr. Albert Wasef
- 2. Chapter goals

- 3. -
- 4. Network layer: responsible for transporting segments from sending to
     receiving host through the network
- 5. Key functions
  - Forwarding: Pushing packets through the appropriate output
  - Routing: Determining route
- 6. Routing and forwarding are connected because a forwarding table is the
     next hop in the route

- 7. Connection setup
  - Used in SOME network architectures, like ATM, Frame Relay, and X.25
  - Establishes a virtual connection involving all intermediate routers
  - Connection can be established at the network or transport level

- 8. Service model
- 9. Service models
  - IP only supports best effort. No bandwidth, loss, order, or timing
    guarantees and no congestion feedback.
  - ATM supports CBR, VBR, ABR, and UBR, with various guarantees.

- 10. -
- 11. Connection vs. connectionless.
  - Is like datagram vs. virtual-circuit.
  - Is like TCP/UDP distinction, but connects hosts instead of services,
    there's no choice between them, and it's implemented in the network core
    rather than on end hosts.

- 12. Virtual circuits
  - Need call setup
  - Packets carry a VC id rather than a destination address
  - Routers must maintain state for every passing connection
  - Resources may be allocated to a VC, so it's more predictable
- 13. VC implementation
  - VC consists of:
    - Path from source to destination
    - One VC number for each link along the path
    - Entries in forwarding tables in the routers along the path
- 14. VC forwarding table: Maps incoming (link, VC #) to outgoing (link, VC #)
- 15. VC signalling protocols: Used for setup, maintenance, and teardown of a VC

- 16. Datagram networks
  - No calls
  - Routers carry no state
  - Packets carry destination address rather than VC id
- 17. Datagram forwarding table
  - Maps address RANGES to output links
  - Can have an "otherwise" entry
- 18. Datagram forwarding table example
- 19. Longest prefix matching: Exactly what it sounds like

- 20. Datagram vs. VC networks
  - Datagram networks permit many link types of varying characteristics
  - VC networks were inspired by telephony and have strict requirements
  - VC networks assume dumb end systems, datagram networks push complexity to
    the edge

- 21. -
- 22. Router architecture overview
  - Routing protocols are RIP, OSPF, BGP
  - Routing processor controls a high-speed switching fabric
- 23. Input ports
  - Goes through these stages:
    - Line termination (Physical)
    - Link layer protocol (Link)
    - Lookup, forwarding, and queueing
    - Into the switching fabric
- 24. Switching fabrics
  - Job is to shunt input ports to correct output ports
  - Types of switching fabric:
    - 25. Memory
      - Like an ordinary computer, controlled by CPU.
      - Old, slow.
    - 26. Bus
      - Shared bus connects all input ports with all output ports.
      - Can result in **bus contention**.
    - 27. Interconnection network
      - Examples: banyan networks, crossbars
      - Basically ASICs
- 28. Output ports
  - Re-wraps packets in the link and physical layers
  - Buffers from fabric into a queue (loss can occur with congestion)
  - Schedules datagrams (priority can happen here)
- 29. Output port queuing
  - Queues can happen at both input and output ports
  - At output ports, queues can get filled up if lots of arriving packets need
    to go to the same destination
- 30. Buffering amount
  - RFC 3439 says: Average buffering = RTT × C
  - More recent results say: Average buffering = RTT × C / √N
- 31. Input port queueing
  - If the fabric is slower than the combined input ports, queueing and loss
    may happen at the input ports.
  - Head-of-the-line blocking (HOL) happens to datagrams which are behind a
    datagram at the front of a queue that is not moved forward due to output
    port contention.

- 32. -
- 33. Recall the Internet layer contains RIP, OSPF, BGP, IP, and ICMP.
- 34. IP datagram format
  - An IP header contains:
    - version, header length, type of service, total datagram length
    - 16-bit fragmentation identifier, flags, fragment offset
    - TTL, upper layer protocol, header checksum
    - Source IP
    - Destination IP
    - Options (optional)
  - 20 bytes total, just like TCP. (So TCP/IP packets have 40 bytes of TCP/IP
    overhead.)
- 35. IP fragmentation
  - MTU is the Maximum Transmission Unit, max size of an IP packet. This varies
    between link types.
  - When MTU changes, datagrams can be fragmented or reassembled.
  - IPv6 gets rid of it.
- 36. IP fragmentation example
  - A single 4000 byte datagram, pushed through a network with MTU 1500 bytes,
    becomes three packets:
    - Length=1500, fragflag=1, offset=0
    - Length=1500, fragflag=1, offset=185
    - Length=1040, fragflag=0, offset=370
  - Total length increased by 40 bytes because there are now two extra IP headers
  - Offset is # of data bytes ÷ 8. 1480 ÷ 8 = 185

- 37. -
- 38. IP addresses
  - 32 bits, soon to be 128 bits with IPv6
  - Every interface (not device!) has an IP address. A router can have a
    different IP address for each of its interfaces.
- 39. IP addressing introduction: We'll learn more about interfaces in the link
      layer
- 40. Subnets
  - An IP address has a host part (lower bits) and a subnet part (higher bits).
  - Subnets are sets of devices that can physically reach each other without an
    intervening router.
- 41. Recipe for finding subnets
- 42. Subnet example with six subnets
- 43. CIDR
  - Classless InterDomain Routing
  - With IP a.b.c.d/x, there are x bits in the subnet
  - Supersedes classful addressing, where subnets are only 8, 16, or 24 bits
  - 255.255.255.255 is broadcast, which sends to all hosts on the subnet
- 44. Obtaining an IP address
  - Can be hard-coded in a system config file
  - Can call up your ISP and ask for one
  - Can get one via DHCP
- 45. DHCP
  - It's the Dynamic Host Configuration Protocol
  - How it works:
    - Host broadcasts "DHCP discover" (optional)
    - DHCP server responds with "DHCP offer" (optional)
    - Host requests IP address with "DHCP request"
    - DHCP server sends address with "DHCP ack"
- 46-47. DHCP simple example
- 48. DHCP also returns:
  - First-hop router for client
  - Name and IP of DNS server
  - Network mask
- 49-51: DHCP example
- 52. How networks get a subnet part: ISP give it a portion
- 53. Hierarchical addressing allows efficient advertising of routing information
- 54. Hierarchical addressing allows for more specific routes
- 55. IP address authority
  - ICANN (Internet Corporation for Assigned Names and Numbers)
  - They dole out IPs
  - They manage DNS
  - They assign domain names and resolve disputes
- 56. NAT
  - Network Address Translation
  - Your home is assigned only a single IP address
  - Within your home, devices have distinct IPs
  - Outside, they all appear as one IP
- 57. NAT motivation
  - ISPs can just give you a single address
  - You can change local device addresses without notifying the outside world
  - You can change ISP without changing local addresses
  - Security: Local devices aren't explicitly addressable
- 58. NAT implementation
  - Outgoing datagrams have source IP/port replaced with NAT IP/new port
  - NAT translation table must remember mapping from NAT IP/new port back to
    source IP/port
  - Incoming datagrams are translated back using the NAT table
- 59. NAT example
- 60. NAT limits
  - 16-bit ports mean you can have 65k simultaneous connections
  - Controversy:
    - Routers should only process up to Layer 3
    - End-to-end no longer true (breaks P2P, hosting servers)
    - Should instead solve address shortage with IPv6
- 61. NAT traversal problem
  - Hard to host servers behind a NAT router
  - Solution 1: Configure port forwarding on your NAT router
  - 62. Solution 2: UPnP IGD protocol automatically configures port forwards.
  - 63. Solution 3: Relaying. Both clients connect to non-NATted server.

- 64. -
- 65. ICMP
  - Internet Control Message Protocol
  - Used to communicate network-level information, such as unreachable host,
    port, echos
  - ICMP message consists of type, code, and first 8 bytes of IP datagram
    causing error
- 66. Traceroute
  - Sends UDP segments of increasing TTL to the destination at an unlikely port
  - Looks at ICMP responses to get intermediate router information

- 67: IPv6
  - Motivation:
    - 32-bit addresses gon run out
    - Better header format speeds processing and forwarding
    - Header changes allow QoS
  - Fixed 40 byte header with no fragmentation
- 68. IPv6 format
  - version, priority, flow label (not well defined)
  - payload len, next header (upper layer protocol), hop limit
  - source address (128 bits)
  - destination address (128 bits)
- 69. Other differences from IPv4
  - Anycast addresses
  - Checksum removed
  - Options indicated by "next header" field
  - ICMPv6 adds additional message types like Message Too Big, multicast group
    management
- 70. IPv4 → IPv6 transition
  - Tunneling: Carrying IPv6 datagram as payload in IPv4 datagram
- 71-72. Tunneling example
- 73. IPv6 adoption: is slow

- 74. Routing algorithms
- 75. Recall that forwarding tables are the next-hop in routes
- 76. Weighted-edge graph abstraction of a network
- 77. Routing algorithms find least cost paths
- 78. Routing algorithm classification
  - Global vs. decentralized
    - Global: Complete topology is known. "Link state" algorithms
    - Decentralized: Each router only knows neighbors. "Distance vector"
      algorithms
  - Static vs. dynamic
    - Static: Routes change slowly over time
    - Dynamic: Routes change more quickly

- 79. Link state algorithms
- 80. Dijkstra's finds single-source shortest paths
- 81. Algorithm definition
- 82. Dijkstra's table example
- 83. Dijkstra's table example
- 84. Dijkstra's shortest path tree
- 85. Dijkstra's details
  - Bad version is O(n²), efficient is O(n log n)
  - With multiple hosts running Dijkstra's, oscillations can happen

- 86. -
- 87. Distance vector algorithm
  - It's Bellman-Ford
  - Distance to x is min of distance to x via v for all neighbors v
  - 88. Example
  - 89. Details
    - Node x maintains vector Dx(y) for y in neighbors
    - Node x also maintains its neighbors' distance vectors
    - 90. Each node sends its distance vector to its neighbors once in a while
  - 91. Properties
    - Iterative, asynchronous
    - Distributed
- 92-93. Distance vector example
- 94-95. Link cost changes
  - Good news travels fast, but
  - Bad news travels slow
    - **Count to infinity** problem, resulting in routing loop
    - Fix using **poisoned reverse**:
      - If A routes to B to get to C, then A tells B that its distance to C is
        infinite.
      - Does not fully solve count-to-infinity problem, since there can still
        be routing loops of three or more nodes.
- 96. LS vs. DV
  - Message complexity: LS is O(nE), DV only has exchange between neighbors
  - Speed of convergence: LS: O(n²) algorithm. DV: Routing loops and count-to-infinity
  - Robustness: LS: Node advertises incorrect link cost. DV: Node advertises
    incorrect path cost, and error propagates through network.

- 97. -
- 98. Hierarchical routing
  - Turns out, Link State and Distance Vector both kinda suck
  - They assume identical routers in a flat network, which isn't true
  - Hierarchical routing allows for:
    - Scale
    - Administrative autonomy
- 99. Works by:
  - Aggregating routers into Autonomous Systems (AS)
  - Within an AS, routers run an intra-AS routing protocol
  - **Gateway routers** are at the edge of an AS and link to routers in
    different ASes
- 100. Interconnected ASes
  - Each router's forwarding table is configured by both intra-AS and inter-AS
    routing algorithms
- 101. Inter-AS routing tasks
  - Each AS learns destinations reachable through connected ASes and propagate
    this information to all routers in the AS
- 102. Example
- 103. Example: Inter-AS must also decide between different gateways
  - 104. Hot potato routing: Choose gateway of least cost from current router.
         Thus the AS gets rid of the packet as quickly as possible.

- 105. -
- 106. Intra-AS routing
  - aka IGP: Interior gateway protocols
  - Include RIP, OSPF, IGRP

- 107. RIP: Routing Information Protocol
  - 1982, BSD Unix
  - Uses distance vector, where distance in # of hops.
  - DVs are exchanged every 30sec in advertisements, and advertisements contain
    up to 25 destination subnets
- 108-109. RIP example
- 110. RIP link failure
  - Neighbors are assumed dead if no advertisements after 180 sec
  - Poison reverse prevents ping-pong loops
- 111. RIP table processing
  - route-d: Application-level process that manages RIP routing tables
  - Advertisements are sent in UDP packets

- 112. OSPF: Open Shortest Path First
  - Uses link state
  - Advertisements carry one entry per neighbor, and are flooded to the entire
    AS
  - OSPF messages are directly on IP
  - IS-IS protocol is very similar
- 113. OSPF advanced features
  - Security: All messages are authenticated
  - Multiple same-cost paths allowed
  - Each link has different cost metrics for different ToS
  - Unicast and multicast support
  - Hierarchical OSPF
- 114-115. Hierarchical OSPF
  - Two-level hierarchy: Local area and backbone.
    - Link-state advertisements stay within area.
    - Area border routers summarize distances to nets in their own area.
    - Backbone routers: OSPF limited to backbone.
    - Boundary routers: Connect to other ASes.

- 116. BGP: Border gateway protocol
  - The de factor inter-AS routing protocol
  - Extremely complex
  - eBGP: Obtain subnet reachability from neighbor ASes
  - iBGP: Propagate reachability to AS-internal routers
  - Allows subent to advertise existence to wider Internet

- 117. BGP basics
  - Path-vector protocol
  - Routers share semi-permanent BGP sessions over TCP port 179
  - When an AS advertises a prefix, it promises that it will forward datagrams
    toward that prefix
    - Prefixes can be aggregated

- 118. BGP basics: distributing path information
  - eBGP used to send prefix reachability between ASes, and iBGP used to
    propagate prefix reachability to all routers within an AS

- 119. Path attributes and BGP routes
  - Advertisements come with attributes
  - Two most important attributes are:
    - AS-PATH: List of ASes through which the prefix advertisement has passed.
    - NEXT-HOP: The IP of the router that begins the AS-PATH.
  - Import policy: Used to accept or decline route advertisements.

- 120. BGP route selection
  - If a router learns more than one route to a destination AS, it selects a
    route based on:
    - 1. The local preference value
    - 2. The shorest AS-PATH
    - 3. The closest NEXT-HOP router
    - 4. BGP identifiers

- 121. BGP messages
  - OPEN: Initiates the semi-permanent TCP connection and authenticates the
    sender.
  - UDPATE: Advertise a new path or withdraw an old one.
  - KEEPALIVE: Keeps the connection alive. ACKs OPEN.
  - NOTIFICATION: Reports errors in a previous message. Also used to close
    connection.

- 122. Putting it together: How an entry gets into a router's forwarding table
  - Uses hierarchical routing, BGP, and OSPF
  - 123. Scenario
  - 124. High level overview is:
    - 1. The router becomes aware of the prefix.
    - 2. The router determines the output interface for the prefix.
    - 3. The router maps the prefix to the interface in the forwarding table.
  - 125. Router becomes aware of prefix
    - A BGP message contains routes, which consist of a prefix and attributes
      including AS-PATH and NEXT-HOP.
    - 126. If a router receives multiple routes for the same prefix, it has to
           choose one.
      - 127. It generally selects the one with the shortest AS-PATH.
    - 128. Router uses OSPF to find the shortest path to the NEXT-HOP.
    - 129. Router identifies the interface and adds it to the forwarding table.
  - 130. Hot potato routing
    - If there are multiple shortest AS-PATHs, then pick the route with the
      closest NEXT-HOP.
  - 131. Summary

- 132. BGP routing policy example
  - Let A, B, C: interconnected provider networks
  - Let W, X, Y: customers of A, (B,C), and Y respectively
    - with X a dual-homed network
  - X does not want traffic from B to C to go through X, so X does not
    advertise that route
- 133. (2)
  - A advertises to B: AW
  - B advertises to X: BAW
  - B does NOT advertise BAW to C, since B gets no revenue for a CBAW route --
    neither W nor C are customers of B

- 134. Reason for distinction between intra- and inter-AS routing
  - Policy:
    - Inter-AS admins want control over traffic that goes through its network.
    - Intra-AS only has a single admin, so we don't need policy decisions.
  - Scale:
    - Hierarchy is good for saving table size and update traffic.
  - Performance:
    - Intra-AS can focus on performance, whereas inter-AS may prioritize policy.

## Chapter 5: Link Layer

- 1. Presented by Dr. Albert Wasef
- 2. Goals

- 3. -
- 4. Link layer introduction
  - Nodes are connected by links, over which frames travel
- 5. Link layer context
  - Princeton→JFK→Geneva→Lausanne analogy
- 6. Link layer services
  - Framing: Putting datagrams into frames
  - Link access: Control access to a shared medium
  - Reliable delivery: More efficient than waiting for higher level protocol to
    do this on a high error link like wireless
- 7.
  - Flow control: Pacing sending and receiving nodes
  - Error detection
  - Error correction
  - Half duplex vs. full duplex
    - Half: Both ends can transmit, but not simultaneously
- 8. Link layer implementation
  - Implemented on the NIC (Network Interface Card)
- 9. Adaptors communicating

- 10. -
- 11. Error detection
  - EDC: Error detection and correction bits
  - Not 100% reliable
- 12. Parity checking
  - Single bit parity: Use a single bit. Can detect single bit errors.
  - Two-dimensional parity: Transmit parity of each row and column. Can
    detect and correct single bit errors.
- 13. Recall: Internet checksum (two's complement sum of 16-bit chunks)
- 14-15. CRC: Cyclic redundancy check
  - More powerful error detection.
  - D: d data bits
  - R: r CRC bits
  - G: r+1 bit generator
  - Want (concat DR) divisible by G
  - Compute R = D×2^r / G
  - Can detect all burst errors of at most r bits.

- 16. -
- 17. Multiple access links
  - Point-to-point links connect two things
  - Some media connect three or more things together
- 18. Multiple access protocols
  - With a single broadcast channel, nodes can collide if they transmit at the
    same time
  - Multiple access protocol helps coordinate against this
- 19. Ideal multiple access protocol
  - If the channel has rate R bps, we want:
    - 1. Single transmitting node can send at rate R.
    - 2. M transmitting nodes can send at average rate R/M.
    - 3. Fully decentralized. No special node, no clock sync or slots.
    - 4. Simple.
- 20. Taxonomy of MAC protocols
  - Channel partitioning:
    - Channel is divided across time, frequency, or code
  - Random access:
    - Channel is not divided. Collisions are allowed, but you recover from
      them.
  - Taking turns:
    - Nodes take turns, weighted by amount node has to send.

<!-- Channel partitioning -->
- 21. TDMA: Time division multiple access
  - Channels take turns. Each channel has a fixed-length slot.
  - Pros: Fair, collision free
  - Cons: Bandwidth wasted, unnecessary waiting
- 22. FDMA: Frequency division multiple access
  - Same pros/cons as TDMA.

<!-- Random access -->
- 23. Random access protocols
  - Nodes that have data transmit at full rate
  - Collisions are detected and recovered from
- 24. Slotted ALOHA
  - Equal size frames, each timeslot can fit one frame, synchronized slots
    between nodes
  - Nodes immediately transmit when they get data
  - If there's a collision, node retransmits in subsequent frames with
    probability p until success
  - 25.
    - Pros:
      - Single active node can fully use channel
      - Decentralized
      - Simple
    - Cons:
      - Collisions waste slots
      - Idle slots with bad luck
      - Collisions can be detected earlier
      - Requires clock synchronized nodes
  - 26. Efficiency
    - Probability of success in a given frame is Np(1-p)^(N-1)
    - Want to find p' that maximizes that
    - As N→∞, max efficiency approaches 1/e = 0.37
- 27. Pure ALOHA
  - Just like Slotted ALOHA, but don't synchronize clocks
  - Collision probability increases
  - 28. Efficiency
    - Probability of success for a given node is p(1-p)^(2(N-1))
    - As N→∞, max efficiency approaches 1/(2e) = 0.18
- 29. CSMA: Carrier sense multiple access
  - Don't interrupt others! Listen before transmitting
  - 30. Collisions can still occur due to propagation delay, and they waste the
        entire packet transmission time.
- 31. CSMA/CD: CSMA with collision detection
  - When you detect a collision, stop transmitting
  - 32. Ethernet CSMA/CD algorithm
    - Basically, if you detect a collision, send a jam signal and use binary
      backoff to decide when to retransmit
  - 33. Flowchart for above
  - 34. Ethernet details:
    - Medium sensing done for 96 bit times
    - Jamming signal 48 bits long
    - Tp = 512 bit times
    - Maximum i is 10; fails afterward
  - 35. Chart for above
  - 36. Efficiency
    - Is 1/(1 + 5tprop/ttrans), where:
    - tprop = max propagation delay between 2 nodes
    - ttrans = time to transmit max-size frame

- 37. Taking-turns MAC protocols
  - Look for the best of both worlds between channel partitioning and random
    access
  - 38. Polling
    - Master node invites slave nodes to transmit in turn
    - Pros: No collisions, no empty slots
    - Cons: Polling overhead, latency, and master is single point of failure
  - 39. Token passing
    - Token is passed to nodes successively
    - Cons: Token overhead, latency, and token is single point of failure
- 40. Cable access network
- 41. DOCSIS: Data Over Cable Service Interface Spec
  - Divides upstream and downstream channels using FDM
  - Additionally TDMs upstream channels
  - Downstream MAP frames assign upstream slots
  - Upstream slot requests and data are transmitted random access with binary
    backoff
- 42. MAC protocols summary

- 43. -
- 44. MAC addresses and ARP
  - 48-bit MAC address is burned into the NIC (though can sometimes be set by
    software)
- 45. LAN addresses and ARP
  - Each adapter on a LAN has a unique LAN address
- 46. More
  - IEEE allocates MAC addresses
  - Manufacturers buy MAC address space
- 47. ARP: Address Resolution Protocol
  - Used to determine an interface's MAC address from its IP address
  - Every IP node has an ARP table that maps IP→MAC with a TTL
- 48. ARP protocol
  - Suppose A wants to send to B, but A doesn't know B's MAC address.
  - A broadcasts an ARP query with B's IP address.
    - (Broadcast MAC address = FF-FF-FF-FF-FF-FF)
  - B replies with its MAC address (unicast).
  - ARP is plug and play.
- 49-54. Addressing example

- 55. -
- 56. Ethernet
- 57. Ethernet physical topology
  - Bus: Popular in mid 90s. All computes share a cable.
  - Star: Popular today. Active switch in the center, so spokes don't collide.
- 58. Ethernet frame structure
  - Preamble: [10101010]×7 + [10101011] to synchronize clock rates
  - 59. Destination MAC address
  - Source MAC address
  - Type (higher layer protocol; usually IP)
  - CRC
- 60. Ethernet properties
  - Connectionless
  - Unreliable: No ACKs or NAKs
  - MAC protocol is unslotted CSMA/CD with binary backoff (as previously
    mentioned)
- 61. 802.3 Ethernet standards
  - There are many of them of various speeds and for fiber and cable

- 62. -
- 63. Ethernet switch
  - Plug-and-play, transparent, self-learning link layer device
- 64. Each link is full duplex and its own collision domain
- 65. Switch forwarding table
  - Maps MAC address to interface, with a timestamp
- 66. Self-learning
  - Switches automatically learn which hosts are available through which
    interface by recording information sent from each interface
- 67. Frame filtering/forwarding
  - If destination link = incoming link, frame is dropped. Otherwise forwarded.
  - If no entry found, flood.
- 68. Example
- 69. Interconnecting switches: Self learning just works!
- 70. Self-learning multi-switch example
- 71. Institutional networks typically have a tree of internal switches with a
      router to the outside
- 72. Switches vs. routers
  - Both are store-and-forward, but:
    - Routers are network-layer, switches are link-layer
    - Router pros:
      - Routers have hierarchical addressing and traffic isolation
      - Routers route from source to destination directly
    - Router cons:
      - Routers have a larger processing time
      - Routers need IP configuration
    - Switch pros: Fast, Plug and play
    - Switch cons:
      - Broadcast storms
      - ARP tables can become very large
  - Both have forwarding tables, but
    - Routers use complex routing algorithms and forward based on IP address
    - Switches learn the forwarding table by flooding and forward based on MAC
      address

- 73. VLANs
- 74. A feature of switches that lets them operate as separate virtual switches
- 75. Port-based VLAN
  - Allows for traffic isolation
  - And dynamic membership
  - And forwarding between VLANs via routing
    - Many vendors sell combined switches + routers
- 76. Multi-switch VLANs
  - Cross-switch frames are carried by a trunk port
  - 802.1q adds header fields for trunk ports
- 77. 802.1q VLAN frame format

- 78. -
- 79. MPLS: Multiprotocol label switching
  - High-speed IP forwarding using a fixed length label
  - Similar to virtual circuit approach
- 80. MPLS capable routers
  - Don't inspect IP address
  - Flexible: Forwarding decisions can be different from IP for traffic
    engineering, pre-computed backup paths
- 81-82. MPLS vs. IP paths
  - IP routing determines next hop based on destination address alone
  - MPLS routing can use source and destination address
- 83. MPLS signaling
  - OSPF, IS-IS are modified to carry information used by MPLS routing
  - RSVP-TE signaling protocol used to set up MPLS forwarding downstream
- 84. MPLS forwarding tables
  - Contain in label, out label, destination, and out interface

- 85. -
- 86. Data center networking
  - Big companies have many many hosts in close proximity
  - 87. Load balancer: Application-layer routing
  - 88. Rich interconnection between switches and racks
    - Tier 1 switches → Tier 2 switches → TOR switches → Racks

- 89. A day in the life of a web request
- 90. Student opens laptop, connects to campus wifi, requests/receives
      www.google.com
- 91. Scenario diagram
- 92. Laptop uses DHCP to get an IP address
  - DHCP request <: UDP <: IP <: 802.3 Ethernet
  - Ethernet frame broadcast received by DHCP server
  - 93. DHCP server responds with DHCP ACK
- 94. Laptop uses ARP to get MAC address of router
- 95. Laptop sends DNS query, forwarded to DNS server, which responds
- 96. Laptop opens TCP socket to web server, SYN SYNACK ACK
- 97. Reply is received from web server and the page is finally displayed!!

- 98. Chapter 5 summary
- 99. Let's take a breath
