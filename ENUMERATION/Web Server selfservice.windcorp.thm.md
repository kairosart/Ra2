Visit https://selfservice.windcorp.thm/.

![[Web Server selfservice.windcorp.thm-20250904113326560.webp]]

You don't have any credentials so far.

## Dirb

#Attacking_machine 
- Enumerte the directories on this server.
```
dirb https://selfservice.dev.windcorp.thm
```

![[Web Server selfservice.windcorp.thm-20250904193802993.webp]]

Visit https://selfservice.dev.windcorp.thm/backup/.

![[Web Server selfservice.windcorp.thm-20250904193905028.webp]]

You can see there is a certificate: `cert.pfx`.

**Next step:** [[Certificate]]
