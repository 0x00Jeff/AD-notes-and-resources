# AD-notes-and-resources
my notes for studying AD/ADCS exploitation (work in progress)

sorta not-so-awesome awesome AD resources repo where I share articles/papers/tools I read about AD/ADCS exploitation, should be a mess untill I figure out the format and put all my notes here, pull request are more than welcome, I'll accept them as soon as I read the new resources

you may also find some of these attacks discussed on my htb writeups or future posts on [my blog](http://0x00jeff.github.io)

# AD
## general knowledge (needed for other attacks)
- [make your own AD homelab](https://activedirectorypro.com/create-active-directory-test-environment/): extremely recommended to learn the attack mentioned here, good tutorial to follow but I'd skip importing the users and OUs and manually create a few, <b>more than one DC is recommended to practise relaying attacks</b>, if physical resources are a limit you could go with the server option (desktopless), pretty light and your fvrt AI can help seeting it up, <b>an external CA host is recommended for practising ADCS attack</b> (thanks `0xTr4c3`!)
- [[English] You Do (Not) Understand Kerberos](https://www.youtube.com/watch?v=4LDpb1R3Ghg): kerberos authentication
## foothold
- [time roast attack](https://cybersecurity.bureauveritas.com/uploads/whitepapers/Secura-WP-Timeroasting-v3.pdf): can be done with `nxc -M timeroast` module or [timeroast.py](https://github.com/bvcyber/Timeroast/tree/main)
## priv esc
- [A Red Teamer’s Guide to GPOs and OUs](https://wald0.com/?p=179) (thanks `orakib`!): 
  - [OUs and GPOs and WMI Filters, Oh My!](https://rastamouse.me/ous-and-gpos-and-wmi-filters-oh-my/) (pics not wroking sadgely)
  - [Persistence With GPP Item-level Targeting](https://pentest.party/posts/2024/persistence-with-wmi-filters/)

# ADCS
  - [Certified Pre-Owned](https://specterops.io/wp-content/uploads/sites/3/2022/06/Certified_Pre-Owned.pdf): the paper that started everything (includes esc1-16)
  - [ADCS exploitation bible](https://github.com/ly4k/Certipy/wiki/06-%E2%80%90-Privilege-Escalation)
  - [ESC17](https://blog.digitrace.de/2026/01/using-adcs-to-attack-https-enabled-wsus-clients/)
  - [No PKINIT? No Problem](https://hwah.us/2025/04/12/no-pkinit-no-problem/)
