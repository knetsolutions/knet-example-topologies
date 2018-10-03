# Learn Traditional Routing & Switching with KNET Network Emulator.


## 1. Switching Introduction:

**OBJECTIVE:**

This exercise helps you to learn Layer2 Switching.

**Learn neighbor discovery(ARP):**

- capture the tcpdump traces and analyze the ARP packets in Wireshark
- Check the ARP entries/ARP Timeout in the HOST systems

**Learn Layer2 Switch functionalities:**

- OVS mac table learning process.

```
sudo ovs-vsctl show
sudo ovs-appctl fdb/show switch1
sudo ovs-dpctl dump-flows
```

### a). Single Switch

![Topology Diagram](imgs/ex1_switch1.jpg?raw=true) 



**Topology file [ex1_switch1.yaml](https://github.com/knetsolutions/knet-example-topologies/blob/master/traditional/ex1_switch1.yaml)**


### b). MultiSwitch environment

To be updated.


## 2. Routing Introduction

**OBJECTIVE:**

This exercises helps you to learn Layer3 Routing Datapath funtionality. Control Plane(routing protocols and routing table updates ) will be covered in the consecutive exercises.


**Learn routing:**

- routing table lookup
- mac rewriting (capture the tcpdump traces and analyze  MAC header in wireshark)
- ttl decrement (capture the tcpdump traces and analyze the IP header in wireshark)


```
ip route
```


![Topology Diagram](imgs/ex2_router.jpg?raw=true) 



**Topology file [ex2_router.yaml](https://github.com/knetsolutions/knet-example-topologies/blob/master/traditional/ex2_router.yaml)**


## 3. Routing - Static Routes

**OBJECTIVE:**

This exercises helps you to learn by manipulating the routing table by adding static route.

```
sudo ip route add 10.20.21.0/24 dev eth1
```

![Topology Diagram](imgs/ex3_router1.jpg?raw=true) 



**Topology file [ex3_router1.yaml](https://github.com/knetsolutions/knet-example-topologies/blob/master/traditional/ex3_router1.yaml)**


## 4. Routing - OSPF




### a). Single area

This exercises helps you to learn the OSPF routing protocol with single area configuration topology.

bird routing sofware is used . Hence use birdc command to check the routing protocol status.

```
birdc show protocols
birdc show protocols all
birdc show route
ip route
```


![Topology Diagram](imgs/ex4_ospf1.jpg?raw=true) 


**Topology file [ex4_ospf1.yaml](https://github.com/knetsolutions/knet-example-topologies/blob/master/traditional/ex4_ospf1.yaml)**

### b). Mutli area


This exercises helps you to learn the OSPF routing protocol with multi area configuration(backbone/transition area).


![Topology Diagram](imgs/ex4_ospf2.jpg?raw=true) 


**Topology file [ex4_ospf2.yaml](https://github.com/knetsolutions/knet-example-topologies/blob/master/traditional/ex4_ospf2.yaml)**


**Bird configuration files [ex4_ospf2](https://github.com/knetsolutions/knet-example-topologies/blob/master/traditional/bird_configs/ex4_ospf2)**


## 5. Routing - BGP

### a). IBGP


This exercises helps you to learn the Interior BGP routing protocol. 

http://www.enterprisenetworkingplanet.com/netsp/article.php/3617346/Networking-101--Understanding-iBGP.htm

![Topology Diagram](imgs/ex5_ibgp.jpg?raw=true) 


**Topology file [ex5_ibgp.yaml](https://github.com/knetsolutions/knet-example-topologies/blob/master/traditional/ex5_ibgp.yaml)**

### b). IBGP with Route Reflector 


This exercises helps you to learn the Interior BGP routing protocol with Route Reflector configuration.

![Topology Diagram](imgs/ex5_ibgp_rr.jpg?raw=true) 

**Topology file [ex5_ibgp_route_reflector.yaml](https://github.com/knetsolutions/knet-example-topologies/blob/master/traditional/ex5_ibgp_route_reflector.yaml)**


### c). EBGP

This exercises helps you to learn the Exterior BGP routing protocol.


![Topology Diagram](imgs/ex5_ebgp.jpg?raw=true) 

**Topology file [ex5_ebgp.yaml](https://github.com/knetsolutions/knet-example-topologies/blob/master/traditional/ex5_ebgp.yaml)**


## 6. Route Redistribution (BGP & OSPF)

This exercises helps you to learn route redistribution across different routing protocol (OSPF & BGP)routing protocol.



![Topology Diagram](imgs/ex6_route_redistribution.jpg?raw=true) 


**Topology file [ex6_route_distribution.yaml](https://github.com/knetsolutions/knet-example-topologies/blob/master/traditional/ex6_route_distribution.yaml)**


**Bird configuration files [ex6_route_distribution](https://github.com/knetsolutions/knet-example-topologies/blob/master/traditional/bird_configs/ex6_route_distribution)**