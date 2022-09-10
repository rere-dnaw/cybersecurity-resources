# Secure Software Development
---

## SDLC (Software Development Life Cycle) 
Organized process of developing secure application through the life of the project.

### Waterfall-model
![[waterfall-model.png]]
#### 1. Project planning and Analysis.
- from raw idea to formalized concept
- requirements
#### 2. Software/System Design.
- application is defined, outlined and diagram in details.
- concentrate on input and output of each function which is gonna make the final product
#### 3. Implementation.
- programmers develop all necessary code which is gonna make the final project
- for each piece of code developers/testers will conduct basic debugging and testing
#### 4. Formalized testing.
- check code against different testing methods
 #### 5. Integration. 
 - application integrated to larger network environment
 - testing end-to-end service
#### 6. Deployment.
- app is moved to production environment
#### 7. Maintenance.
- bug fixing, patches, updates
- **version control** (major, minor, build version number)
- **configuration management**

#### Drawback:
Takes long time to implement changes.


 ### Agile
 Software development is performed in time-boxed or small increments to be more adaptive to changes. It still uses **waterfall-model** but in a smaller development periods (2-4 weeks). The goal is to release smaller product more quickly and more often.  

- used to release features to products


## DevOps
Software development and information technology operation.


## SDLC principals:
- ### developers should think about CIA triad 
	- confidentiality, Integrity, availability
- ### thread modeling
	- helps prioritization of threads
- ### least privilege
- ### defense in depth 
	- layering security control
- ### never trust user input
- ### minimize attack surface
	- reduce amount of code used by program, authentication before running additional plugins
- ### create secure defaults
	- app include secure default configuration
- ### authenticity and integrity
	- signing code to ensure that program is not changed when delivered to the end user
- ### Fail Securely
	- app should be coded to proper conduct error handling (fail securely instead of crashing)
- ### fix security issues
	- vulnerability must be quickly and correctly patched
- ### relay on trusted SDK's (Software Development Kit)
	- make sure that used library are reliable  


## Testing Methods:
- ### System Testing
	- #### black box testing
		- tester knows **nothing** about the program or system before starting test 
	- #### white box testing
		- tester knows **details** about the program or system before starting test 
	- #### grey box testing
		- mixture of black box and white box
- ### Structured Exception Handling (SEH)
	- control over what app should do when encounter runtime or syntax error 
- ### Input validation
- ### Static analysis
	- source code is analyzed manually or with automated tool without running code
- ### Dynamic Analysis
	- analysis and testing is done while program is executed
- ### Fuzzing
	- injection of randomized data into software in attempt to find memory leaks, error handling issues and improper input validation