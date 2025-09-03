
Enumerate the directories .

#Attacking_machine 
```
gobuster dir -u https://fire.windcorp.thm -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -k
```

![[Gobuster-20250903211749240.webp]]

The interesting thing here is `/powershell/default.aspx?ReturnUrl=%2fpowershell]`.


**Next step:** [[Web server]]
