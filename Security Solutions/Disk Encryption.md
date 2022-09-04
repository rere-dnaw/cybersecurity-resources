# Disk Encryption
---
## Encryption types:
- self-encrypting drive
- encryption software
	- FileVault (uses symetric AES encryption)
	- BitLocker (uses symetric AES encryption)

## Keys for encryption:
- ### TPM (Trusted Platform Module) 
	- Chip on motherboard containing an encryption key (data **CAN NOT** be decrypted on other machine)
- ### External USB containing encryption key 
	- if USB drive lost, data **CAN NOT** be recover


## HSM (Hardware Security Module)
Physical device which acts as cryptoprocessor during the encryption process. Commonly PCI extension module.


#TPM #HSM