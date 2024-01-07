# Final degree project: VPLS Implementation with VNX

Welcome to my final degree project project. This repository revolves around the implementation of Virtual Private LAN Service (VPLS) using Virtual Network over Linux (VNX). In this project, I've created simulated networks to delve into the fundamental configuration and operation of Multiprotocol Label Switching (MPLS) and the VPLS service.

## Project Overview

The primary objective is to provide a practical and controlled environment for exploring the configuration and interactions of MPLS, as well as gaining a detailed understanding of the VPLS service. The simulated networks enable experiments to observe the behavior of these protocols in a virtual laboratory environment.

## Previous requierements
### Installation Guide

For the deployment of the scenarios, it is necessary to have the VNX software installed on our Linux system beforehand. You can follow the [installation guide](https://web.dit.upm.es/vnxwiki/index.php/Vnx-install) for detailed instructions.

### Download openBSD filesystems
Once we have installed VNX, we can download the filesystem with the command:
```
sudo vnx_download_rootfs
```

Then, choose the option vnx_rootfs_kvm_openbsd64-7.2.qcow2.bz2  , **IMPORTANT choose yes to create direct link rootfs_openbsd64**

![Screenshot from 2024-01-07 11-53-42](https://github.com/avillaseca01/VNXOpenBSDMPLS/assets/121334055/ea95cdfd-4add-46ec-aa70-25eba06021b1)


## Network deployment

To deploy the network, first we need to choose which network we want to run.
### Basic scenario
To deploy the basic network you just need to run the next commands:
``` 
cd mpls-openbsd-basic
sudo vnx -f mpls-openbsd.xml -t
````
![Screenshot from 2024-01-07 13-53-18](https://github.com/avillaseca01/VNXOpenBSDMPLS/assets/121334055/ce5016a2-44c6-4b9c-a7bc-b95d1c5a3c9e =250x250) 

### Advanced scenario
To deploy the advanced network you just need to run the next commands:
``` 
cd mpls-openbsd-advanced
sudo vnx -f mpls-openbsd.xml -t
```
![Screenshot from 2024-01-07 13-53-03](https://github.com/avillaseca01/VNXOpenBSDMPLS/assets/121334055/2e87008f-5461-46ef-b77f-271942c5d429 =250x250)

## Using the network
Once you have the network deployed, first you have to log in to every system with user: **root** and password: **xxxx**

### MPLS Routing tables
To see the MPLS forwarding tables in openBSD you can use:
``` 
route show -mpls
````
### VPLS Configuration

In the advanced scenario, two VPLS instances, **CUST_A** and **CUST_B**, have been configured. The assignment of systems to each VPLS instance is as follows:

- Systems with odd numbers (CE1, CE3, CE5) belong to **CUST_A**.
- Systems with even numbers (CE2, CE4) belong to **CUST_B**.

#### IP Addresses for Each System

Here is the mapping of IP addresses to each system:

- **CE1**: 172.16.1.1
- **CE2**: 172.16.1.2
- **CE3**: 172.16.1.3
- **CE4**: 172.16.1.4
- **CE5**: 172.16.1.5

Feel free to explore the routing tables and configurations to understand the MPLS networking setup in more detail.

## Acknowledgements

This project drew inspiration from [OpenBSD-ldpd VPLS Basic Test Setup](https://github.com/rwestphal/openbsd-ldpd/wiki/VPLS-basic-test-setup) and the MPLS laboratory in the RECO subject at UPM university.
