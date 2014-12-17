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
ICMP     |   Internet Control Message Protocol
IANA     |   Internet assigned numbers authority
UPnP     |   Universal Plug and play
CIDR     |   Classless Inter-Domain Routing
IGMP     |   Internet Group Management Protocol
IPv      |   Internet Protocol Version
RARP     |   Reverse ARP
DHCP     |   Dynamic host control Protocol
CSMA     |   Carrier sense multiple access


<br>
<br>


# Test 1 solutions

* An internetwork is formed when a computer connects two different networks, what is the computer called?
> Gateway

* The techonolgy for NSFNet (National Science Foundation Network) and thus the interenet came from what DoD project?
> ARPANet

* The internet as we know it was proceeded by NSFNet, which was turned over to the private sector on what date?
> 4/30/95     OR     April 30th 1995

* TCP/IP model
> 1. application
> 2. transport
> 3. network
> 4. physical

* What therom determines the bandwidth of a noiseless channel?
> Lanknist? Nyquist?

* What therom determines the bandwidth of a noisy channel?
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

Acronym    |   How-To
-------    |   ------
NRZ        |   Non-return-to-zero ![NZR](http://upload.wikimedia.org/wikipedia/commons/5/55/NRZcode.png)
NRZ-I      |   Non-return-to-zero inverted  ![nzri](http://upload.wikimedia.org/wikipedia/commons/e/e4/NRZI_example.png)<br>"One" is represented by a transition of the physical level.<br>"Zero" has no transition.
Manchester<br>(IEEE and nromal) | ![](http://upload.wikimedia.org/wikipedia/commons/thumb/9/90/Manchester_encoding_both_conventions.svg/650px-Manchester_encoding_both_conventions.svg.png)
Manchester<br>(Differential) | ![](http://upload.wikimedia.org/wikipedia/commons/thumb/5/50/Differential_manchester_encoding.svg/600px-Differential_manchester_encoding.svg.png)<br> 1 - transition on the bit only <br> 0 - transition on the clock and bit

### CDMA

`Code0 = (1, -1), data0 = (1,1,0,0,1,1)`
`Code1 = (1, 1), data1 = (0,1,1,0,1,0)`

Steps
1. Multiply by 2
2. subtract 1
3. cross Product data with with code
4. add


        Multiply by 2

        2  *   (1,1,0,0,1,1)  |  (0,1,1,0,1,0)
        =       2,2,0,0,2,2   |   0,2,2,0,2,0

        Subtract 1
        -1 +   (2, 2, 0, 0, 2, 2)  |  (0, 2, 2, 0, 2, 0)
        =       1, 1,-1,-1, 1, 1   |  -1, 1, 1,-1, 1,-1

        Cross Product
                (1,-1) (x) ( 1, 1,-1,-1, 1, 1)          |    (1, 1) (x) (-1, 1, 1,-1, 1,-1)
        =        1,-1, 1,-1,-1, 1,-1, 1, 1,-1, 1,-1          -1,-1, 1, 1, 1, 1,-1,-1, 1, 1,-1,-1

        Add

                1,-1, 1,-1,-1, 1,-1, 1, 1,-1, 1,-1
        +      -1,-1, 1, 1, 1, 1,-1,-1, 1, 1,-1,-1
                0,-2, 2, 0, 0, 2,-2, 0, 2, 0, 0 -2



<br>
<br>

# Test 2 solutions

### Hamming Codes
#### Decoding
      Even Parity


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
            Fixed    1 0 0 1 1 1 0 1 1 1 0 0 1



Hamming code calculator: http://www.ecs.umass.edu/ece/koren/FaultTolerantSystems/simulator/Hamming/HammingCodes.html

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
