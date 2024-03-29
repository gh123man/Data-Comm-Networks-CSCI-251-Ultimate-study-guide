# Acronyms


Acronym  |   Definition
-------  |   ----------
HVAC     |   Heating ventilating and air conditioning
UTP      |   Unshielded twisted pair
TCP      |   Transmission Control Protocol
IP       |   Internet Protocol
OSI      |   Open Systems Interconnection model
STP      |   Spanning Tree Protocol
CATV     |   Cable television
UDP      |   User Datagram Protocol
RFC      |   Request for Comments
ASK      |   Amplitude Shift Keying
QAM      |   Quadrature amplitude modulation
DoD      |   Department of Defense (model)
ARPA     |   Advanced Research Projects Agency
LAN      |   Local Area Network
NSF      |   National Science Foundation (Network (NSFNET))
ISO      |   International Standards Organization
FTP      |   File Transfer Protocol
HTTP     |   Hypertext Transfer Protocol
SSB      |   ?????
FM       |   frequency modulation
WDM      |   Wavelength-division multiplexing
FDM      |   frequency-division multiplexing
CDMA     |   Code division multiple access
TDM      |   Time-division multiplexing
InterNIC |   Internet (NIC) Network Information Center
NRZ      |   Non-return-to-zero
NRZ-I    |   Non-return-to-zero inverted
MAC      |   Media Access Control
ARP      |   Address Resolution Protocol
NAT      |   Network Address Translation
NAPT     |   Network Address and Port Translation
ICMP     |   Internet Control Message Protocol
IANA     |   Internet assigned numbers authority
UPnP     |   Universal Plug and play
CIDR     |   Classless Inter-Domain Routing
IGMP     |   Internet Group Management Protocol
IPv      |   Internet Protocol Version
RARP     |   Reverse ARP
DHCP     |   Dynamic host control Protocol
CSMA     |   Carrier sense multiple access
MTU      |   maximum transmission unit (max packet size)
BMC      |   Biphase mark coding
CRC      |   cyclic redundancy check
EGP      |   Exterior Gateway Protocol
IGP      |   Interior Gateway Protocol
RIP      |   Routing Information Protocol
OSPF     |   Open Shortest Path First
BGP      |   Border Gateway Protocol (is internet standard)
iBGP     |   Internal Border Gateway Protocol
eBGP     |   External Border Gateway Protocol
RIPng    |   RIP next generation
IXP      |   Internet exchange point
AS       |   Autonomous Systems




# Various notes

### Comparing models

Layers         | OSI | DoD | TCP
------         | --- | --- | ---
Application    |  X  |  X  |  X
Presentation   |  X  |     |
Session        |  X  |     |
Transportation |  X  |  X  |  X
Network        |  X  |  X  |  X
Data Link      |  X  |  X  |
Physical       |  X  |  X  |  X

#### Random Access Protocols
 1. Aloha
 2. Slotted Aloha
 3. CSMA/CD
 4. CSMA

#### Network Layer Protocols
 1. ICMP
 2. IGMP
 3. TCP
 4. UDP
 5. EGP
 6. IGP

#### LAN standards (link layer)
 `802.xx`
 1. `11` - Wireless
 2. `3` - Ethernet
 3. `13` - Cat6
 4. `15` - Wireless personal Area network (Bluetooth)
 5. `14` - deprecated cable modem standard
 6. `1` - Architecture

#### Media Access Links/Protocols
 1. Point to Point
 2. Broadcast
 3. Switched

#### Types of Hubs
 1. Passive hub
    - Like a splitter
    - Signal is partially absorbed
 2. Active Hub
    - Like a passive hub, but powered
    - Amplifies the signal
    - Can increase effective distance with a good signal
    - Acts as a repeater
 3. Intelligent Hub
    - Does signal regeneration
    - network management
    - Intelligent path selection
    - Is aware of MAC address

#### Handling packet loss
 1. Go back `n`
    - Send packets, go back `n` times where `n` is the # of packets you missed
 2. Selective repeat
    - Only repeats the packets that were not ACK'd


#### IP routing
 - Intra AS (autonomus sytem) - inner
 - intr AS - outer

#### Problems with RIP
 - No subnetting
 - long time to stabilize
 - hop count is a bad metric
 - max of 15 hops


#### Distance vector protocol guide
![](http://upload.wikimedia.org/wikipedia/commons/thumb/4/46/Networkabcd.svg/250px-Networkabcd.svg.png)


from C | via A | via B | via C | via D
------ | ----- | ----- | ----- | -----
 to A  |  23   |   5   |       |  15
 to B  |  26   |   2   |       |  12
 to C  |       |       |       |  
 to D  |  33   |   9   |       |  5

 - http://en.wikipedia.org/wiki/Distance-vector_routing_protocol
 - Dijskstra's is used in some cases?

#### Packet transmission
![](http://homepages.herts.ac.uk/~comqrgd/docs/network-notes/network-notes-img101.png)
![](http://www.masterraghu.com/subjects/np/introduction/unix_network_programming_v1.3/files/02fig02.gif)

<br>

## Definitions
Term/Topic      | Definition
----------      | ----------
Baud Rate       | Measure of signal change per second
Data Rate       | Number of bits per second transmitted
Bounded Media   | Data is confined to a specific pathway
Unbounded Media | data is transmitted through space
Twisted Pair    | 2 insulated wires twisted together in a helix
Multiplexing    | sharing bandwidth on a channel
Hamming Distance| Number 9f bit positions two code words differ
Parity          | Simple error detection constructed by counting bits.
Hamming Code    | N bit codes that can correct single bit errors
Checksum        | (happens on link layer)
Hub             | Provides a single connection between a workstation and itself
Router          | Connects two networks, Is a computer itself, makes decisions about where packets go
Fragmentation   | Data Link can impose upper limit of frame size, so packets are fragmented
Host Routing    | if the destination is  a directly connected network, send it there otherwise send packet to default router
Router routing  | Hosts never forward packets
Dynamic routing | Routers talk to each other sharing info about connected networks
RIP             | Distance vector protocol - First in BSD in 1982 - exchanges every 30 seconds via advertisment - each distance vector can have 25 advertisements.
link-state routing protocol | router tests network through broadcast and updates table via link type condition.
OSPF            | If two routes have the same cost, load is shared
BGP             | Internet standard
Link state protocol | router tests network through a broadcast and updates its routing table based on the type link or condition
Sequence number | initial sequence number is based on the `k` number of low order bits. You can generate a sequence number from a clock






<br><br>

# Test 1 solutions

* An internetwork is formed when a computer connects two different networks, what is the computer called?
> Gateway

* The technology for NSFNet (National Science Foundation Network) and thus the internet came from what DoD project?
> ARPANet

* The internet as we know it was proceeded by NSFNet, which was turned over to the private sector on what date?
> 4/30/95     OR     April 30th 1995

* TCP/IP model
> 1. application
> 2. transport
> 3. network
> 4. physical

* What theorem determines the bandwidth of a noiseless channel?
> Nyquist

* What theorem determines the bandwidth of a noisy channel?
> Shannons

* Name of the transport protocol that is unreliable datagram:
> UDP

* Transport protocol that is reliable:
> TCP

* 4 Types of multiplexing that are commonly used?
> 1. CDMA
> 2. Time devision
> 3. frequency division
> 4. Wavelength-division multiplexing

* What is bandwidth?
> Information carrying capacity of a channel

* What is the name of the organization that assigns IP addresses?
> InterNIC

* What three properties of a carrier wave can be modulated in order to transmit a signal?
> 1. phase
> 2. amplitude
> 3. frequency

* what are some properties of an IPv4 Address?
> 32bit
> 4 8bit octets
> dot notation

### Encodings

Acronym                                          |   How-To
-------                                          |   ------
NRZ                                              |   Non-return-to-zero ![NZR](http://upload.wikimedia.org/wikipedia/commons/5/55/NRZcode.png)
NRZ-I                                            |   Non-return-to-zero inverted  ![nzri](http://upload.wikimedia.org/wikipedia/commons/e/e4/NRZI_example.png)<br>"One" is represented by a transition of the physical level.<br>"Zero" has no transition.
NRZ-L                                            |   Non-return-to-zero level  ![nrzL](http://upload.wikimedia.org/wikipedia/commons/2/23/Nrz-lb.gif)
Manchester<br>(IEEE and nromal)                  | ![](http://upload.wikimedia.org/wikipedia/commons/thumb/9/90/Manchester_encoding_both_conventions.svg/650px-Manchester_encoding_both_conventions.svg.png)
Manchester<br>(Differential)                     | ![](http://upload.wikimedia.org/wikipedia/commons/thumb/5/50/Differential_manchester_encoding.svg/600px-Differential_manchester_encoding.svg.png)<br> 1 - transition on the bit only <br> 0 - transition on the clock and bit
Manchester<br>(Differential Biphase mark coding) | ![](http://upload.wikimedia.org/wikipedia/commons/thumb/c/cb/Biphase_Mark_Code.svg/518px-Biphase_Mark_Code.svg.png)<br>Biphase mark coding transitions on every positive edge of the clock signal (when the clock goes from 0 to 1) and also translates on the negative edge of the clock signal when the data is a 1.

### CDMA

`Code0 = (1, -1), data0 = (1,1,0,0,1,1)`
`Code1 = (1, 1), data1 = (0,1,1,0,1,0)`

Steps
1. Multiply by 2
2. subtract 1
3. cross Product data with with code
4. add

#### Encoding

        Multiply by 2

        2  *   (1,1,0,0,1,1)  |  (0,1,1,0,1,0)
        =       2,2,0,0,2,2   |   0,2,2,0,2,0

        Subtract 1
        -1 +   (2, 2, 0, 0, 2, 2)  |  (0, 2, 2, 0, 2, 0)
        =       1, 1,-1,-1, 1, 1   |  -1, 1, 1,-1, 1,-1

        Cross Product
                (1,-1) (x) ( 1, 1,-1,-1, 1, 1)       |  (1, 1) (x) (-1, 1, 1,-1, 1,-1)
        =        1,-1, 1,-1,-1, 1,-1, 1, 1,-1, 1,-1  |  -1,-1, 1, 1, 1, 1,-1,-1, 1, 1,-1,-1

        Add

                1,-1, 1,-1,-1, 1,-1, 1, 1,-1, 1,-1
        +      -1,-1, 1, 1, 1, 1,-1,-1, 1, 1,-1,-1
                0,-2, 2, 0, 0, 2,-2, 0, 2, 0, 0 -2

#### Decoding
         0,-2, 2, 0, 0, 2,-2, 0, 2, 0, 0 -2
        (0,-2), (2, 0), (0, 2), (-2, 0), (2, 0), (0 -2) * each by (1, -1) code0
        (1 -1)  (1 -1)  (1 -1)  ( 1 -1)  (1 -1)  (1 -1)
         0  2    2  0    0 -2    -2  0    2  0    0  2

         +2 becomes 1
         -2 becomes 0
         Ignore the 0s

         so:  0 2 2 0 0-2-2 0 2 0 0 2
         Becomes 1 1 0 0 1 1 which is our original data0

         Do the same steps with Code1 to get data1




<br>
<br>

# Test 2 solutions

### Hamming Codes

#### Encoding
      Even Parity

         Message     1 0 0 1 1 0 1 1 0
     with spaces     1 0 0 1 1 _ 0 1 1 _ 0 _ _

               Px              8       4   2 1
        Code Word    1 0 0 1 1 _ 0 1 1 _ 0 _ _
        Take/skip    1   1   1   1   1   1   1
                         1 1     1 1     1 1
                     1 1 1       1 1 1 1
                     1 1 1 1 1 1


               P1    1 0 1 0 1 0      -    3 - Use 1
               p2    0 1 0 1 0        -    2 - Use 0
               p4    1 0 0 0 1 1      -    3 - Use 1
               p8    1 0 0 1 1        -    3 - Use 1


         ORIGINAL    1 0 0 1 1 _ 0 1 1 _ 0 _ _
       W/ Hamming    1 0 0 1 1 1 0 1 1 1 0 0 1

#### Decoding
      Even Parity (I used the same data from above. I flipped bit 7)


               Px              8       4   2 1
        Code Word    1 0 0 1 1 1 1 1 1 1 0 0 1
        Take/skip    1   1   1   1   1   1   1
                         1 1     1 1     1 1
                     1 1 1       1 1 1 1
                     1 1 1 1 1 1


               P1    1 0 1 1 1 0 1    -    5 - BAD
               p2    0 1 1 1 0 0      -    3 - BAD
               p4    1 0 0 1 1 1 1    -    5 - BAD
               p8    1 0 0 1 1 1      -    4 - GOOD

               1 + 2 + 4 = 7

                                 x
              BAD    1 0 0 1 1 1 1 1 1 1 0 0 1
            Fixed    1 0 0 1 1 1 0 1 1 1 0 0 1 - Original data :)


Hamming code calculator (Not helpful for decoding, only encoding): http://www.ecs.umass.edu/ece/koren/FaultTolerantSystems/simulator/Hamming/HammingCodes.html

### CRC

        Calculating g(x)
                 Bit Position   6 5 4 3 2 1 0
            x^6 + x^5 + x + 1 = 1 1 0 0 0 1 1

            Message: 1011010100


            Append len(g(x)) - 1 0s to the message
                       _______
            1011010100 0000000  added 0s

            divide (XOR)
                           __________________________________
            1 1 0 0 0 1 1 ) 1 0 1 1 0 1 0 1 0 0 0 0 0 0 0 0 0
                            1 1 0 0 0 1 1 | | | | | | | | | |
                       XOR  _____________ V | | | | | | | | |
                            0 1 1 1 0 0 1 1 | | | | | | | | |
                              1 1 0 0 0 1 1 | | | | | | | | |
                         XOR  _____________ V V | | | | | | |
                              0 0 1 0 0 0 0 0 0 | | | | | | |
                                  1 1 0 0 0 1 1 | | | | | | |
                             XOR  _____________ V | | | | | |
                                  0 1 0 0 0 1 1 0 | | | | | |
                                    1 1 0 0 0 1 1 | | | | | |
                               XOR  _____________ V | | | | |
                                    0 1 0 0 1 0 1 0 | | | | |
                                      1 1 0 0 0 1 1 | | | | |
                                 XOR  _____________ V | | | |
                                      0 1 0 1 0 0 1 0 | | | |
                                        1 1 0 0 0 1 1 | | | |
                                   XOR  _____________ V | | |
                                        0 1 1 0 0 0 1 0 | | |
                                          1 1 0 0 0 1 1 | | |
                                     XOR  _____________ V V V
                                          0 0 0 0 0 0 1 0 0 0

                                                      1 0 0 0 is our checksum

              So our message is:     1 0 1 1 0 1 0 1 0 0 0 0 0 1 0 0 0

CRC calculator (truncates after 5 bits): http://www4.ncsu.edu/~chou/course/Animations/Calculation%20of%20a%20CRC%20Checksum/crcinit.html

* What is the relationship between the generator polynomials length and the length of the frame that the CRC is being performed on?
> It has to be smaller

* What are the 4 types of topology that are used in networking?
> 1. Bus
> 2. star
> 3. ring
> 4. mesh

* The addressing done at the datalink layer uses what types of addresses?
> Media Access Control

* Name two protocols that use the Random Access Protocol system for sharing a line
> 1. Aloha
> 2. CSMA

* What does CSMA stand for, wahts a more common name?
> 1. Carrier sense multiple access
> 2. Ethernet

* Bridges operate at what level of the OSI model?
> Data Link

* What is hamming distance?
> The number of bit positions 2 code words differ

* If we have a message with 32 bits, how many parity bits do we need to correct 1 bit errors with hamming code?
> 6

* What layer of the network stack does a router operate on?
> Network

* How many bits in a MAC Address?
> 48

* A MAC Address is also known as what kind of address?
> Hardware Address

* Name the layers in the DoD reference model we use in class, list in order
> 1. Application
> 2. Transport
> 3. Network
> 4. Data Link
> 5. Physical

# Test 3 solutions

* Given the following IP and netmask (`42.112.67.212/18`), what is the range of IPs that are valid?
 `42.112.64.0 - 42.112.127.255`

CIDR calculator: http://www.subnet-calculator.com/cidr.php

* draw a picture of NAT (napt).
> LOOK IT UP

* what is the size of an IPv6 address in bits?
> 128

* what is the protocol which is typically used by IPv4 to get an IP address on a LAN?
> DHCP

* number of bits in an IPv4 Address?
> 32

* CIDR is also known as?
> supernetting

* what 3 primary services does IPv4 provide?
> 1. Routing
> 2. Addressing
> 3. Fragmentation

* What is the local loopback Address for IPv4 and IPv6?
> 1. `127.0.0.1`
> 2. `::1`

* What are the private IPv4 Blocks?
> 1. `192.168.x.x`
> 2. `10.x.x.x`
> 3. `172.16-31.x.x`

* All Unicast IPv6 Address start with what 3 bits? What possible Hex values does this correspond to (aka, what numbers must unicast addresses start with)?
> 1. `001x`
> 2. 2 OR 3

* Link local IPv6 Addresses all start with what 16bit numbers? (in hex)
> `FE80`

* use IPv6 shorthand to shorten the following address: `LONG:ASSS:ADDRESS:0000:0000:0000:SOMETHING`
> `LONG:ASSS:ADDRESS::SOMETHING`

* How is fragmentation different in IPv4 vs IPv6? How does MTU come into play?
> - IPv4: fragmentation happens on a router on its way to the destination. MTU: 64 bytes
> - Ipv6: Fragmentation happens on the host, not at the router. MTU: 1280 bytes

* What problem did CIDR aim to solve? How does it accomplish this?
> LOOK UP
