# IPTABLES
---
## It can be used for filtering incoming and outgoing packages. Also it can be used for routing packages (like router) and NAT connections. It manage and control netfilter. 

### iptables key components:
- #### tables (filter, nat, mangle)
- #### chains (rules)
- #### matches (conditions)
- #### targets


### **Table in IPTABLES is a collection of chains that serves particular function ** 
![[iptables.png.png]]

### **Filter Table** - is used for firewall aspect
### **NAT table** - is used to redirect connections to different interfaces
##### (Network Address Translation)
### **Mangle table** - is used to changing/modifying aspects of packets or connections 


# Packet flow:
## Request to server -> check against input rules* - > Set target based on rules
#####  * packet will be checked against input chains from the top to the bottom 
#### If packet doesn't match any rule, it will use default rules.  If there is no default rule, the package will be accepted by the system.

## TARGET - defines what is gonna to happen to the packet 
- ACCEPT -> will allow packet flow 
- REJECT -> will drop the packet and send feedback to user
- DROP -> will drop the packet (like no packer was even send)


# Before start setting up IPTABLES
# **KEEP IN MIND THAT WHEN SETTING IPTABLES SOME OTHER APPS MAY AFFECT THEM e.g. [[UFW]], [[docker]]**

# **Flush IPTABLES** 
```bash
sudo iptables -F
```

```text
-flush   -F [chain]		Delete all rules in  chain or all chains
```

# **When you add rules you can append(-A) or insert(-I) rule (remember rules order matter)**


# Few simply examples:

### For dropping connections into port 80
```bash
sudo iptables -I INPUT -p tcp --dport 80 -j DROP
```

### Drop all input connection (this will stop ssh connection!)
```bash
sudo iptables -I INPUT -j DROP
```

### Drop connections from provided IP:
```bash
sudo iptables -I INPUT -s 192.168.3.91 -j DROP

```


## When you are done with settings rules, type following command to save the rules.
```bash
sudo /sbin/iptables-save
```


