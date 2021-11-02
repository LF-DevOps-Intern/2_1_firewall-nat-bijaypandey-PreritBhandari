# Description

1) In the first VM (named as, Centos1) we set up two network interfaces:

i) Bridged Adapter (enp0s3)
ii) Host-Only Adapter (enp0s8)

2) Similarly, we set up another network interface in the second VM (named as, Centos2):

i) Host-Only Adapter (enp0s3)


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


