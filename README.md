# Previous requierements
##  VNX Instalation
For the deployment of the scenarios, it is necessary to have the VNX software installed on our Linux system beforehand. You can follow the installation guide at the following link: https://web.dit.upm.es/vnxwiki/index.php/Vnx-install

## Download openBSD filesystems
Once we have installed VNX, we can download the filesystem with the command:
```
sudo vnx_download_rootfs
```

Then, choose the option vnx_rootfs_kvm_openbsd64-7.2.qcow2.bz2  , **IMPORTANT choose yes to create direct link rootfs_openbsd64**

![Screenshot from 2024-01-07 11-53-42](https://github.com/avillaseca01/VNXOpenBSDMPLS/assets/121334055/ea95cdfd-4add-46ec-aa70-25eba06021b1)


# Network deployment

To deploy the network, first we need to choose wich network we want to run. 

## Basic scenario
To deploy the basic network you just need to run the next commands:

``` 
cd mpls-openbsd-basic
sudo vnx -f mpls-openbsd.xml -t
````

## Advanced scenario
To deploy the advanced network you just need to run the next commands:

``` 
cd mpls-openbsd-advanced
sudo vnx -f mpls-openbsd.xml -t
```
# Using the network
Once you have the network deployed, first you have to login on every system with user: **root** and password: **xxxx**

## MPLS Routing tables
To see the MPLS forwarding tables in openBSD you can use:
``` 
route show -mpls
````
## VPLS Configuration

In the advanced scenario, two VPLS instances, **CUST_A** and **CUST_B**, have been configured. The assignment of systems to each VPLS instance is as follows:

- Systems with odd numbers (CE1, CE3, CE5) belong to **CUST_A**.
- Systems with even numbers (CE2, CE4) belong to **CUST_B**.

### IP Addresses for Each System

Here is the mapping of IP addresses to each system:

- **CE1**: 172.16.1.1
- **CE2**: 172.16.1.2
- **CE3**: 172.16.1.3
- **CE4**: 172.16.1.4
- **CE5**: 172.16.1.5

Feel free to explore the routing tables and configurations to understand the MPLS networking setup in more detail.



