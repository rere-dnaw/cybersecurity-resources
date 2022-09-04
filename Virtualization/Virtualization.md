# Virtualization
---
Allows to create multiple virtual instances which share same hardware. Also the virtual devices can bind together hardware. e.g. NIC

## Virtual network devices:
- #### Virtual servers
- #### [[Hypervisor]] (allows for creating VMs)
	- Type 1
		- e.g.
			- KVM
	- Type 2
		- e.g. 
			- Virtual Box
- #### Virtual Storage Solution 
	- NAS
		- single point of failure  
	- SAN (Storage Area Network)
		- specialized LAN designed for storage and transfer data (not affected by other network traffic)
		- transfer data on the block level (reason why faster than NAS)
		-  connected through
			- FC (Fiber Channel) most expensive, most popular, fastest
			- iSCSI (IP Small Computer Interface) cheaper, 10Gbps
				- uses Jumbo [[Frame]] (larger frame 9000 MTU)
		- redundant, scaleable, expensive
	- InfiniBand
		- virtualization storage technology 
		- direct special connection between storage solution and server
- #### Virtual Firewall
- #### Virtual switch
- #### Virtual router
- #### Virtual Desktop
- #### SDN (Software Defined Network)
	- provides network administrators with easy way to configure virtual and physical devices
- #### [[Cloud Computing]]

## VM types:
- ### System
	- complete platform (physical computer and fully operating system) 
- ### Processor
	- designed to run single application (e.g. web server)


#jumbo-frame