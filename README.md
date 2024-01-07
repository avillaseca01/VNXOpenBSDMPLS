# Previous requierements
##  VNX Instalation
For the deployment of the scenarios, it is necessary to have the VNX software installed on our Linux system beforehand. You can follow the installation guide at the following link: https://web.dit.upm.es/vnxwiki/index.php/Vnx-install

## Download openBSD filesystems
Once we have installed VNX, we can download the filesystem with the command:
```sudo vnx_download_rootfs```

Then, choose the option vnx_rootfs_kvm_openbsd64-7.2.qcow2.bz2  , **IMPORTANT say yes to create direct access rootfs**   

# Network deployment

To deploy the network, first we need to choose wich network we want to run. 

## Basic scenario

```cd mpls-openbsd-basic
sudo vnx -f mpls-openbsd.xml -t````

## Advanced scenario

```cd mpls-openbsd-advanced
sudo vnx -f mpls-openbsd.xml -t```
