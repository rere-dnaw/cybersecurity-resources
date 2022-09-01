# Supply Chain Assessment
---
Investigating source and components of:
- firmware
- software
- hardware


## Due Diligence 
A legal principle of best practice and reasonable care when setting up, configuring and maintaining a system. When doing **Due Diligence** you have to make sure that supplier have:
-  a proper cybersecurity program 
- security assurance and risk management process
- product life cycle 
- security control for personal data
- customer support 
- supplier history and reputation

## Trusted Foundry
It's a way to make sure that microprocessors are secure and it's run by department of defense 

## Hardware Source Authenticity
The process of ensuring that hardware is produced tamper-free from trustworthy suppliers. 
(think about place from where you get the device)

## ROT (Root of Trust)
A hardware root of trust is used to scan boot metrics ans OS files (it's digital certificate).

## Trusted Platform Module (TPM)
Port of system which make sure that when you boot up system, it's done securely. 

## Hardware Security Module (HSM)
Physical device which acts as cryptoprocessor during the encryption process. Commonly PCI extension module.

## Anti-Tamper
Method to increase difficulty for an attacker to alter the authorized execution software.
- ### Field Programmable Gate Array (FPGA)
- ### Physical Unclonable Function (PUF) 

## Trusted Firmware
- ### Unified Extensible Firmware Interface (UEFI)
	- providing support for 64-bit CPU operation at boot, full GUI and mouse operation at boot and better boot security
- ### Secure Boot 
	- A UEFI feature that prevents unwanted processes from executing during the boot operation. It's gonna check digital signatures.
- ### Measured Boot
	- A UEFI feature that gathers secure metrics to validate the boot process in an attestation report (e.g. data about booting time)
- ### Attestation
	- validate data presented in report by signing it with TPM's key
- ### eFUSE
	- one time programming which is used to seal cryptographic keys and other secure information during development process. If fuse is "blown" the firmware is not longer trusted.
- ### Trusted Firmware Update
	- A firmware signed by vendor and trusted by system before installation
- ### Self-Encrypting Drive
	- make sure that firmware on the device is trusted 

## Secure Processing
A mechanism to provide: confidentiality, integrity and availability of software code and data when it's executed in volatile memory. 
 - ### Processor Security Executions
	 - Low level CPU changes and instructions that enables secure processing
	 - for **AMD** it's: Secure Memory Extension (**SEM**), Secure Encrypted Visualization (**SEV**)
	 - for **Intel** it's: Trusted Execution Technology (**TXT**), Software Guard Extensions (**SGX**)
 - ### Trusted Execution
	 - The CPU's security extension invoke a TPM and secure boot.
 - ### Secure Enclave
	 - The extension which allows to create an encrypted container for sensitive data
 - ### Atomic Execution
	 - Certain operations should be performed only one time (e.g. initialization memory location) 
 - ### Bus Encryption
	 - Data is encrypted by application before being placed on the data bus



#ROT #TPM #HSM #PUF #FPGA #UEFI