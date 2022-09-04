# [[Shell]] connections
---
Each type of shell has its use case, and the same way there are many ways to obtain a shell, the helper program that we use to get a shell can be written in many languages (`Python`, `Perl`, `Go`, `Bash`, `Java`, `awk`, `PHP`, etc.). These can be small scripts or larger, more complex programs to facilitate a connection from the target host back to our attacking system and obtain "shell" access.

| **Shell Type**    |  **Description** |
|:--------------:|:-----------|
| Reverse shell | Initiates a connection back to a "listener" |
| Bind Shell | "Binds" to a specific port on the target host and waits for a connection |
| Web shell | Runs operating system commands via the web browser,|
|| e.g. uploading a `PHP` script to run a single command. |
