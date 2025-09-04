Visit https://fire.windcorp.thm/.

There's a list of staff's members.
![[Web server fire.windcorp.thm-20250904114608129.webp]]

## Getting the emails

- Show the page source.
- You'll see a section like the following:
	![[Web server fire.windcorp.thm-20250904192312852.webp]]

#Attacking_machine 
- Create a file with that section. (i.e. `xmpp_info.txt`)
- Run the following code to extract the emails to a file. (i.e. `xmpp_users`)
```
cat xmpp_info.txt| cut -d ":" -f4 | cut -d '"' -f1 > xmpp_users
```

- You'll have all the emails on that file.
	organicfish718@fire.windcorp.thm
	organicwolf509@fire.windcorp.thm
	tinywolf424@fire.windcorp.thm
	angrybird253@fire.windcorp.thm
	buse@fire.windcorp.thm
	Edeltraut@fire.windcorp.thm
	Edward@fire.windcorp.thm
	Emile@fire.windcorp.thm
	tinygoose102@fire.windcorp.thm
	brownostrich284@fire.windcorp.thm
	sadswan869@fire.windcorp.thm
	sadswan869@fire.windcorp.thm
	whiteleopard529@fire.windcorp.thm
	happymeercat399@fire.windcorp.thm
	orangegorilla428@fire.windcorp.thm


## Powershell Web Access

Visit https://fire.windcorp.thm/powershell/en-US/logon.aspx?ReturnUrl=%2fpowershell%5D.

![[Web server-20250903212259106.webp]]

organicfish718@fire.windcorp.thm
organicwolf509@fire.windcorp.thm
tinywolf424@fire.windcorp.thm
angrybird253@fire.windcorp.thm
buse@fire.windcorp.thm
Edeltraut@fire.windcorp.thm
Edward@fire.windcorp.thm
Emile@fire.windcorp.thm
tinygoose102@fire.windcorp.thm
brownostrich284@fire.windcorp.thm
sadswan869@fire.windcorp.thm
sadswan869@fire.windcorp.thm
whiteleopard529@fire.windcorp.thm
happymeercat399@fire.windcorp.thm
orangegorilla428@fire.windcorp.thm


**Next step:** [[Web Server selfservice.windcorp.thm-20250904113326560.webp]]
