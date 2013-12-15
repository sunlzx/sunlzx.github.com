---
layout: post
title: "IP Protocol Numbers"
description: ""
category: "net"
tags: [net, linux]
---
{% include JB/setup %}


##IPIP
	
	IPIP协议号是4，不是94

## Internet (IP) protocols

	/etc/protocols 文件

	elb@114-113-199-46:~$ cat /etc/protocols 
	# Internet (IP) protocols
	#
	# Updated from http://www.iana.org/assignments/protocol-numbers and other
	# sources.
	# New protocols will be added on request if they have been officially
	# assigned by IANA and are not historical.
	# If you need a huge list of used numbers please install the nmap package.

	ip	0	IP		# internet protocol, pseudo protocol number
	#hopopt	0	HOPOPT		# IPv6 Hop-by-Hop Option [RFC1883]
	icmp	1	ICMP		# internet control message protocol
	igmp	2	IGMP		# Internet Group Management
	ggp	3	GGP		# gateway-gateway protocol
	ipencap	4	IP-ENCAP	# IP encapsulated in IP (officially ``IP'')
	st	5	ST		# ST datagram mode
	tcp	6	TCP		# transmission control protocol
	egp	8	EGP		# exterior gateway protocol
	igp	9	IGP		# any private interior gateway (Cisco)
	pup	12	PUP		# PARC universal packet protocol
	udp	17	UDP		# user datagram protocol
	hmp	20	HMP		# host monitoring protocol
	xns-idp	22	XNS-IDP		# Xerox NS IDP
	rdp	27	RDP		# "reliable datagram" protocol
	iso-tp4	29	ISO-TP4		# ISO Transport Protocol class 4 [RFC905]
	dccp	33	DCCP		# Datagram Congestion Control Prot. [RFC4340]
	xtp	36	XTP		# Xpress Transfer Protocol
	ddp	37	DDP		# Datagram Delivery Protocol
	idpr-cmtp 38	IDPR-CMTP	# IDPR Control Message Transport
	ipv6	41	IPv6		# Internet Protocol, version 6
	ipv6-route 43	IPv6-Route	# Routing Header for IPv6
	ipv6-frag 44	IPv6-Frag	# Fragment Header for IPv6
	idrp	45	IDRP		# Inter-Domain Routing Protocol
	rsvp	46	RSVP		# Reservation Protocol
	gre	47	GRE		# General Routing Encapsulation
	esp	50	IPSEC-ESP	# Encap Security Payload [RFC2406]
	ah	51	IPSEC-AH	# Authentication Header [RFC2402]
	skip	57	SKIP		# SKIP
	ipv6-icmp 58	IPv6-ICMP	# ICMP for IPv6
	ipv6-nonxt 59	IPv6-NoNxt	# No Next Header for IPv6
	ipv6-opts 60	IPv6-Opts	# Destination Options for IPv6
	rspf	73	RSPF CPHB	# Radio Shortest Path First (officially CPHB)
	vmtp	81	VMTP		# Versatile Message Transport
	eigrp	88	EIGRP		# Enhanced Interior Routing Protocol (Cisco)
	ospf	89	OSPFIGP		# Open Shortest Path First IGP
	ax.25	93	AX.25		# AX.25 frames
	ipip	94	IPIP		# IP-within-IP Encapsulation Protocol
	etherip	97	ETHERIP		# Ethernet-within-IP Encapsulation [RFC3378]
	encap	98	ENCAP		# Yet Another IP encapsulation [RFC1241]
	#	99			# any private encryption scheme
	pim	103	PIM		# Protocol Independent Multicast
	ipcomp	108	IPCOMP		# IP Payload Compression Protocol
	vrrp	112	VRRP		# Virtual Router Redundancy Protocol [RFC5798]
	l2tp	115	L2TP		# Layer Two Tunneling Protocol [RFC2661]
	isis	124	ISIS		# IS-IS over IPv4
	sctp	132	SCTP		# Stream Control Transmission Protocol
	fc	133	FC		# Fibre Channel
	mobility-header 135 Mobility-Header # Mobility Support for IPv6 [RFC3775]
	udplite	136	UDPLite		# UDP-Lite [RFC3828]
	mpls-in-ip 137	MPLS-in-IP	# MPLS-in-IP [RFC4023]
	manet	138			# MANET Protocols [RFC5498]
	hip	139	HIP		# Host Identity Protocol
	shim6	140	Shim6		# Shim6 Protocol [RFC5533]
	wesp	141	WESP		# Wrapped Encapsulating Security Payload
	rohc	142	ROHC		# Robust Header Compression

##Protocol Numbers

	Decimal    Keyword     Protocol
	=======    =======     ==============
	     0     HOPOPT      IPv6 Hop-by-Hop Option            
	     1     ICMP        Internet Control Message           
	     2     IGMP        Internet Group Management         
	     3     GGP         Gateway-to-Gateway                 
	     4     IP          IP in IP (encapsulation)          
	     5     ST          Stream                     
	     6     TCP         Transmission Control               
	     7     CBT         CBT                             
	     8     EGP         Exterior Gateway Protocol     
	     9     IGP         any private interior gateway         
	                       (used by Cisco for their IGRP)
	    10     BBN-RCC-MON BBN RCC Monitoring                    
	    11     NVP-II      Network Voice Protocol         
	    12     PUP         PUP                             
	    13     ARGUS       ARGUS                                
	    14     EMCON       EMCON                                 
	    15     XNET        Cross Net Debugger            
	    16     CHAOS       Chaos                                 
	    17     UDP         User Datagram                  
	    18     MUX         Multiplexing                    
	    19     DCN-MEAS    DCN Measurement Subsystems           
	    20     HMP         Host Monitoring                
	    21     PRM         Packet Radio Measurement              
	    22     XNS-IDP     XEROX NS IDP               
	    23     TRUNK-1     Trunk-1                              
	    24     TRUNK-2     Trunk-2                              
	    25     LEAF-1      Leaf-1                               
	    26     LEAF-2      Leaf-2                               
	    27     RDP         Reliable Data Protocol         
	    28     IRTP        Internet Reliable Transaction  
	    29     ISO-TP4     ISO Transport Protocol Class 4 
	    30     NETBLT      Bulk Data Transfer Protocol    
	    31     MFE-NSP     MFE Network Services Protocol  
	    32     MERIT-INP   MERIT Internodal Protocol             
	    33     SEP         Sequential Exchange Protocol        
	    34     3PC         Third Party Connect Protocol         
	    35     IDPR        Inter-Domain Policy Routing Protocol 
	    36     XTP         XTP                                   
	    37     DDP         Datagram Delivery Protocol            
	    38     IDPR-CMTP   IDPR Control Message Transport Proto 
	    39     TP++        TP++ Transport Protocol               
	    40     IL          IL Transport Protocol            
	    41     ISATAP      ISATAP                              
	    42     SDRP        Source Demand Routing Protocol       
	    43     IPv6-Route  Routing Header for IPv6           
	    44     IPv6-Frag   Fragment Header for IPv6          
	    45     IDRP        Inter-Domain Routing Protocol   
	    46     RSVP        Reservation Protocol           
	    47     GRE         General Routing Encapsulation     
	    48     MHRP        Mobile Host Routing Protocol
	    49     BNA         BNA                          
	    50     ESP         Encap Security Payload for IPv6   
	    51     AH          Authentication Header for IPv6    
	    52     I-NLSP      Integrated Net Layer Security  TUBA 
	    53     SWIPE       IP with Encryption                    
	    54     NARP        NBMA Address Resolution Protocol  
	    55     MOBILE      IP Mobility                       
	    56     TLSP        Transport Layer Security Protocol   
	                       using Kryptonet key management
	    57     SKIP        SKIP                              
	    58     IPv6-ICMP   ICMP for IPv6                     
	    59     IPv6-NoNxt  No Next Header for IPv6           
	    60     IPv6-Opts   Destination Options for IPv6      
	    61                 any host internal protocol           
	    62     CFTP        CFTP                            
	    63                 any local network                    
	    64     SAT-EXPAK   SATNET and Backroom EXPAK             
	    65     KRYPTOLAN   Kryptolan                            
	    66     RVD         MIT Remote Virtual Disk Protocol      
	    67     IPPC        Internet Pluribus Packet Core         
	    68                 any distributed file system          
	    69     SAT-MON     SATNET Monitoring                     
	    70     VISA        VISA Protocol                        
	    71     IPCV        Internet Packet Core Utility          
	    72     CPNX        Computer Protocol Network Executive  
	    73     CPHB        Computer Protocol Heart Beat         
	    74     WSN         Wang Span Network                     
	    75     PVP         Packet Video Protocol                 
	    76     BR-SAT-MON  Backroom SATNET Monitoring            
	    77     SUN-ND      SUN ND PROTOCOL-Temporary             
	    78     WB-MON      WIDEBAND Monitoring                   
	    79     WB-EXPAK    WIDEBAND EXPAK                        
	    80     ISO-IP      ISO Internet Protocol                 
	    81     VMTP        VMTP                                 
	    82     SECURE-VMTP SECURE-VMTP                          
	    83     VINES       VINES                                 
	    84     TTP         TTP                                   
	    85     NSFNET-IGP  NSFNET-IGP                            
	    86     DGP         Dissimilar Gateway Protocol     
	    87     TCF         TCF                                  
	    88     EIGRP       EIGRP                           
	    89     OSPFIGP     OSPFIGP                      
	    90     Sprite-RPC  Sprite RPC Protocol            
	    91     LARP        Locus Address Resolution Protocol     
	    92     MTP         Multicast Transport Protocol          
	    93     AX.25       AX.25 Frames                         
	    94     IPIP        IP-within-IP Encapsulation Protocol   
	    95     MICP        Mobile Internetworking Control Pro.   
	    96     SCC-SP      Semaphore Communications Sec. Pro.    
	    97     ETHERIP     Ethernet-within-IP Encapsulation     
	    98     ENCAP       Encapsulation Header         
	    99                 any private encryption scheme        
	   100     GMTP        GMTP                                 
	   101     IFMP        Ipsilon Flow Management Protocol   
	   102     PNNI        PNNI over IP                       
	   103     PIM         Protocol Independent Multicast  
	   104     ARIS        ARIS                              
	   105     SCPS        SCPS               
	   106     QNX         QNX              
	   107     A/N         Active Networks                    
	   108     IPComp      IP Payload Compression Protocol   
	   109     SNP         Sitara Networks Protocol          
	   110     Compaq-Peer Compaq Peer Protocol                
	   111     IPX-in-IP   IPX in IP                
	   112     VRRP        Virtual Router Redundancy Protocol 
	   113     PGM         PGM Reliable Transport Protocol  
	   114                 any 0-hop protocol                   
	   115     L2TP        Layer Two Tunneling Protocol        
	   116     DDX         D-II Data Exchange (DDX)           
	   117     IATP        Interactive Agent Transfer Protocol  
	   118     STP         Schedule Transfer Protocol            
	   119     SRP         SpectraLink Radio Protocol       
	   120     UTI         UTI            
	   121     SMP         Simple Message Protocol            
	   122     SM          SM                
	   123     PTP         Performance Transparency Protocol   
	   124     ISIS over IPv4               
	   125     FIRE                      
	   126     CRTP        Combat Radio Transport Protocol  
	   127     CRUDP       Combat Radio User Datagram    
	   128     SSCOPMCE                  
	   129     IPLT                  
	   130     SPS         Secure Packet Shield             
	   131     PIPE        Private IP Encapsulation within IP       
	   132     SCTP        Stream Control Transmission Protocol   
	   133     FC          Fibre Channel                        
	   134-254             Unassigned                           
	   255                 Reserved       


## 参考资料

[Protocol Numbers](http://www.iana.org/assignments/protocol-numbers/protocol-numbers.xhtml)

[Internet Protocol Numbers](http://support.microsoft.com/kb/289892)