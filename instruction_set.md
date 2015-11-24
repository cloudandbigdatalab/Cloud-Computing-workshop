
Openstack Horizon Dashboard
```
http://10.241.1.107
```

login into the hoizon dashboard with the given credentials

```
user : 
password : 
```
## Excercise 1 
Create a network

```
> Network 
> Network Topology
> Create Network
> Add your network name > click next
> Add your Sub net name
> Add the network CIDR provided > click next
> Add 10.241.1.1 to DNS Name Servers 
```

Create a Router

```
> Network 
> Network Topology
> Create a Router
> Add you router name 
> Select utsa_net for external network
> Create router
```

Add the network you created to router as an interface

```
> Network 
> Router
> Click on your router
> Click on the interfaces 
> Click on add interface 
> Select your subnet from the drop down menu
```

Create an instance using oci_ubuntu_1404 image
Assosciate floating Ip and access the instance
```
ssh ociuser@<IP-address>
password: abigsecret
```

## Excercise 2
### Creating two VLAN's and connecting them with routers
Create another network and add it to the same router as before using the second CIDR
Create another VM or Instance on the second network 
Login to the second instance from the first instance 

## Excercise 3
### Create a Network File System on first instance and mount it to second instance 
Login to the first server and change as root user

```
ssh ociuser@<first-instance-ip>
sudo -i
cd nfs_demo
chmod +x setup_nfs_server.sh
./setup_nfs_server.sh  <second-instance-private-ip>
```

Login to the second server from the first server and change as root user

```
ssh ociuser@<second-instance-private-ip>
sudo -i
cd nfs_demo
chmod +x setup_nfs_client.sh
./setup_nfs_client.sh <first-instance-private-ip>
```

Now create a file at ```/mnt/nfs/var/nfs```

```
echo "This is a cool file " >> /mnt/nfs/var/nfs/cool.txt 
```

Now login to the first instance and check in ```/var/nfs``` folder for the cool.txt file

If you reached this point

### Congratualation !!! 
You successfully completed the exercises





