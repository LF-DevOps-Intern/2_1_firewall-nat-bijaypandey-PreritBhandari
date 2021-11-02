
## Description

1. Ensuring that the Firewall is already installed and running correctly in our Centos 7 machine;

``` systemctl status firewalld ```

2. Blocking ip using firewalld permanently;

``` 
sudo firewall-cmd --permanent --add-rich-rule="rule family='ipv4' source address='xxx.xxx.xxx.xxx' reject"
sudo firewall-cmd --reload
sudo firewall-cmd --list-all 
```
3. Allow http, https and ssh connections using firewall;

```
# sudo firewall-cmd --zone=public --permanent --add-service=http

# sudo firewall-cmd --zone=public --permanent --add-service=https

# sudo firewall-cmd --zone=public --permanent --add-service=ssh

# sudo firewall-cmd --zone=public --permanent --list-services
```
