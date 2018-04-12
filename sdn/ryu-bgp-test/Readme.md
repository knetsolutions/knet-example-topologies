RYU BGP APP Verification
==========================

This tutorial demonstates the RYU BGP application.  
We used this below topology for this demonstation. we deployed this topology in KNet.

![Topology Diagram](img/bgp_topology.png?raw=true) 


Prerequisties:

KNet and RYU must have installed in your system.


Step1: Deploy the topology in KNet 
-----------------------------------

Topology file name : bgp_topology.yaml

In the Knet CLI, 

```
CreateTopology  bgp_topology.yaml
```


Step2: Copy the Bird router config files (BGP enabled) to all Routers
----------------------------------------------------------------------

Router configuration files are present in this folder(RtrA_bird.conf,...)

```
sudo docker cp RtrA_bird.conf Rtr-A:/etc/bird.conf
sudo docker cp RtrB_bird.conf Rtr-B:/etc/bird.conf
sudo docker cp RtrC_bird.conf Rtr-C:/etc/bird.conf
sudo docker cp RtrD_bird.conf Rtr-D:/etc/bird.conf
```


Step3: Start the Bird Routing daemon in each Router:
-------------------------------------------------------


```
sudo docker exec -it Rtr-A sh
bird -c /etc/bird.conf
ps -ef
exit
```

Repeat the same for all routers(Rtr-B,Rtr-C,Rtr-D)

Now, the topology is converged with BGP Router.


Step4: Start the RYU BGP Application in the host:
-------------------------------------------------------

RYU BGP configuration is file is present in this folder(ryu_bgp_router.conf)

```
sudo ryu-manager ryu.services.protocols.bgp.application --bgp-app-config-file ryu_bgp_router.conf

```

Step5: Verification(RYU)
-------------------------

```
ssh localhost -p 4990
show neighbor
show rib all
```
