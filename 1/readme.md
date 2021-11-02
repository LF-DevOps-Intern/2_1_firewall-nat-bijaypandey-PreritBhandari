
## Description

1. Ensuring that the Firewall is already installed and running correctly in our Centos 7 machine;

``` systemctl status firewalld ```

2. Blocking ip using firewalld permanently;

``` 
sudo firewall-cmd --permanent --add-rich-rule="rule family='ipv4' source address='xxx.xxx.xxx.xxx' reject"
sudo firewall-cmd --reload
sudo firewall-cmd --list-all 

```
