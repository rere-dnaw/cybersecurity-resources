# Hardening
---

## Least Functionality
Workstation configuration with only necessary software to reduce vectors of attack.  

- For large network best solution is to prevent users from installing necessary software. Utilize a secure baseline image when adding new workstation
- **SCCM (Microsoft System Center Configuration Management)** allows to update new configurations and policies across network 

## Restricting Applications
### Application Whitelist 
Only application listed in whitelist can be installed. 

### Application Blacklist
Only application listed in blacklist can **NOT** be installed. 

## Turn off unnecessary services
- Windows (services.msi)
- Mac OS (Activity Monitor)
- Linux (kill pid `number`)

## Trusted Operating Systems 
System which meets the requirements set by government.
- Windows 7 and later
- Mac OS X 10.6 and later
- FreeBSD (TrustedBSD)
- Red Hat Enterprise Server

## Patch Management 
Process of planning, testing, implementing and auditing of software patches. Microsoft tool for this purpose is called: **Microsoft Baseline Security Analyzer.** 
- ### planning
	- verify if is compatible with your systems and deploying plan
- ### testing 
	- testing before deployment (e.g. in lab network)
- ### implementing
	- manually or automatically
	- for large organization it's useful to have central control over updates
- ### audit
	- ensure that patches has been installed properly

## Group Policies
Set of rules/policies which can be applied to users or computers. The template can be created and loaded to multiple workstations.
- ### Windows command **`gpedit`**
	- password complexity
	- account lockout policy
	- software restriction
	- application restriction

## Baselining 
Process of measuring changes in the network, hardware and software environment

## [[Disk Encryption]] 