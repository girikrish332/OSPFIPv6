# OSPFIPv6

IPv6 OSPF Configuration README

This document provides guidance on configuring IPv6 OSPF (Open Shortest Path First) routing protocol for the network setup described below.
Network Topology

The network consists of four routers (R1, R2, R3, R4) interconnected as follows:

    R1 is connected to R2 and R4
    R2 is connected to R1 and R3
    R3 is connected to R2 and R4
    R4 is connected to R1 and R3

Router Configuration
R1 Configuration

bash

en
conf t

ipv6 unicast-routing
ipv6 router ospf 10
router-id 1.1.1.1

interface Ethernet0/0
ipv6 enable
ipv6 address 2001::10/64
no shutdown
ipv6 ospf 10 area 1

interface Ethernet0/1
ipv6 enable
ipv6 address 2004::20/64
no shutdown
ipv6 ospf 10 area 1

R2 Configuration

bash

en
conf t

ipv6 unicast-routing
ipv6 router ospf 10
router-id 2.2.2.2

interface Ethernet0/0
ipv6 enable
ipv6 address 2001::20/64
no shutdown
ipv6 ospf 10 area 1

interface Ethernet0/1
ipv6 enable
ipv6 address 2002::10/64
no shutdown
ipv6 ospf 10 area 1

R3 Configuration

bash

en
conf t

ipv6 unicast-routing
ipv6 router ospf 10
router-id 3.3.3.3

interface Ethernet0/0
ipv6 enable
ipv6 address 2003::10/64
no shutdown
ipv6 ospf 10 area 1

interface Ethernet0/1
ipv6 enable
ipv6 address 2002::20/64
no shutdown
ipv6 ospf 10 area 1

R4 Configuration

bash

en
conf t

ipv6 unicast-routing
ipv6 router ospf 10
router-id 4.4.4.4

interface Ethernet0/0
ipv6 enable
ipv6 address 2004::10/64
no shutdown
ipv6 ospf 10 area 1

interface Ethernet0/1
ipv6 enable
ipv6 address 2003::20/64
no shutdown
ipv6 ospf 10 area 1

Notes

    Each router is configured with IPv6 unicast routing enabled.
    OSPF routing process ID is set to 10 for all routers.
    Router IDs are set accordingly.
    Each interface participating in OSPF is assigned to OSPF area 1.
    Interfaces are enabled and assigned IPv6 addresses as per the provided configuration.

This README provides a clear overview of the network topology and configuration steps for each router involved in setting up IPv6 OSPF routing. Make sure to apply these configurations correctly to achieve desired routing behavior in the network.
