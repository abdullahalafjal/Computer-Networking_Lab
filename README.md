## RIP Configuration Guide

This document provides the configuration examples for RIP (Routing Information Protocol) version      1 and version     2. RIP is a distance-vector routing protocol used for exchanging routing information within an autonomous system.

---

### RIP

RIP is a simple routing protocol based on the Bellman-Ford algorithm. It uses hop count as the routing metric and has a maximum allowable hop count of 15.

---

### RIP1

RIP1 is a **classful** routing protocol that does not support subnet masks. This makes it unsuitable for discontiguous networks and networks using Variable Length Subnet Masking (VLSM).

### Configuration Steps for RIP1:
1. Access the router's configuration mode.
2. Enter RIP routing configuration.
3. Specify the networks to advertise.
4. Save the configuration.

### RIPv2 Configuration
1.Key Features of RIPv2   
2.Classless routing protocol (supports subnet masks).   
3.Supports authentication.  
4.Multicast updates instead of broadcast.  

### Example Configuration for RIP1-RIP2:
```bash
Router> enable
Router# configure terminal
Router(config)# router rip
Router(config-router)# version 1
Router(config-router)# network 192.168.1.0
Router(config-router)# network 10.0.0.0
Router(config-router)# exit
Router(config)# end
Router# write memory

Router> enable
Router# configure terminal
Router(config)# router rip
Router(config-router)# version 2
Router(config-router)# network 192.168.1.0
Router(config-router)# network 10.1.1.0
Router(config-router)# no auto-summary
Router(config-router)# exit
Router(config)# end
Router# write memory

