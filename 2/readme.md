# Description

1) In the first VM (named as, Centos1) we set up two network interfaces:

  - Bridged Adapter (enp0s3)
  - Host-Only Adapter (enp0s8)

2) Similarly, we set up another network interface in the second VM (named as, Centos2):

  - Host-Only Adapter (enp0s3)


3) Configuring the enp0s8 on Centos1 as,

```
# ifconfig ethp0s8 192.168.56.101 netmask 255.255.255.0

# route
```
4) Similarly, we configure the enp0s3 on Centos2 as,
```
ifconfig ethp0s3 192.168.56.102 netmask 255.255.255.0

# route
```
5) Ping from each device to another one inorder to verify that the connection is established between Centos1 and Centos2 .

7) Now we have to tell Centos2 to use enp0s8 from Centos1, for that on Centos2 device:
```
 # route add default gw 192.168.56.101

`# route
 ```
8) We can now share our connection from Centos1 to Centos2 with the following commands:

```
# modprobe iptable_nat
# echo 1 > /proc/sys/net/ipv4/ip_forward
# iptables -t nat -A POSTROUTING -o enp0s3 -j MASQUERADE
# iptables -A FORWARD -i enp0s8 -j ACCEPT
```
9) Thus, in this way we shared the internet connection from Centos1 to Centos2 through NAT. This can be verified by executing the ping command in the Centos2 device as below,
```
# ping 31.13.79.35
 ```





