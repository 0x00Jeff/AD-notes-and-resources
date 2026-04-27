# AD-notes-and-resources
my notes for studying AD/ADCS exploitation (work in progress)

sorta not-so-awesome awesome AD resources repo where I share articles/papers/tools I read about AD/ADCS exploitation, should be a mess untill I figure out the format and put all my notes here, pull request are more than welcome, I'll accept them as soon as I read the new resources

you may also find some of these attacks discussed on my htb writeups or future posts on [my blog](http://0x00jeff.github.io)

# AD
## Full on guides
- [Attacking Active Directory: 0 to 0.9](https://zer1t0.gitlab.io/posts/attacking_ad/): grants HUGE amount of knowldge for AD and has LOADS of resources that would take weeks to really dive in, although personally I think it's better used as a reference or to know what to learn next since it has a nice roadmap that assumes 0 pre-knowledge (thanks `g0rchy`!)

## (Home)labs
- [make your own AD homelab](https://activedirectorypro.com/create-active-directory-test-environment/): extremely recommended to learn the attacks mentioned here as well how to imeplement them, good tutorial to follow but I'd skip importing the users and OUs and manually create a few, <b>more than one DC is recommended to practise relaying attacks</b>, if physical resources are a limit you could go with the server option (desktopless), pretty light and your fvrt AI can help seeting it up, <b>an external CA host is recommended for practising ADCS attack</b> (thanks `0xTr4c3`!)
- [game of active directory](https://github.com/Orange-Cyberdefense/GOAD): ready labs of all sizes, just install and attack
- [Extreme Red Team Laboratories](https://extremeredlab.0x29a.it/): free AD cert of extreme difficulty, includes networks with both linux and AD machines, cloud misconfigs across AWS/Azure/GCP, extreme pivoting etc

## General knowledge (needed for other attacks)
- [[English] You Do (Not) Understand Kerberos](https://www.youtube.com/watch?v=4LDpb1R3Ghg): basic kerberos authentication in depth

## Foothold
- AS-REP Roasting (kerberos knowledge needed):
  - [attacking from a linux machine](https://www.thehacker.recipes/ad/movement/kerberos/asreproast)
  - [implementing the attack in a windows homelab and attacking from windows](https://asma-altayyari.gitbook.io/ad-attack)
- [time roast attack](https://cybersecurity.bureauveritas.com/uploads/whitepapers/Secura-WP-Timeroasting-v3.pdf): can be done with `nxc -M timeroast` module or [timeroast.py](https://github.com/bvcyber/Timeroast/tree/main)
- [TR19: Fun with LDAP and Kerberos: Attacking AD from non-Windows machines](https://www.youtube.com/watch?v=2Xfd962QfPs): the talk behind [kerbrute](https://github.com/ropnop/kerbrute), the fastest tool for AD credentials bruteforce, can used to enumerate valid usernames on a domain as well as password spraying
## Priv esc
### kerberos delegation
- kerberos delegation playlist: (refer to kerberos auth reource first)
  - [1 - [English] You Do (Not) Understand Kerberos Delegation - Introduction](https://www.youtube.com/watch?v=p9QFdITuvgU)
  - [2 - [English] You Do (Not) Understand Kerberos Delegation - Unconstrained Delegation](https://www.youtube.com/watch?v=xDFRUYv1-eU)
  - [3 - [English] You Do (Not) Understand Kerberos Delegation - Constrained Delegation](https://www.youtube.com/watch?v=gzqq2r6cZjc)
  - [4 - [English] You Do (Not) Understand Kerberos Delegation - RBCD](https://www.youtube.com/watch?v=vlKwCTvp5_w)
- [Wagging the Dog: Abusing Resource-Based Constrained Delegation to Attack Active Directory](https://shenaniganslabs.io/2019/01/28/Wagging-the-Dog.html)
- [S4U2Pwnage](https://harmj0y.medium.com/s4u2pwnage-36efe1a2777c)
- [Delegating Kerberos To Bypass Kerberos Delegation Limitation by Charlie Bromberg](https://www.youtube.com/watch?v=byykEId3FUs)


### GPOs and WMI filters
- [A Red Teamer’s Guide to GPOs and OUs](https://wald0.com/?p=179) (thanks `orakib`!):
  - [OUs and GPOs and WMI Filters, Oh My!](https://rastamouse.me/ous-and-gpos-and-wmi-filters-oh-my/) (pics not wroking sadgely)
  - [Persistence With GPP Item-level Targeting](https://pentest.party/posts/2024/persistence-with-wmi-filters/)

### Recycle bin
- [Have You Looked in the Trash? Unearthing Privilege Escalations from the Active Directory Recycle Bin](https://cravaterouge.com/articles/ad-bin/)

## persistence
### golden gMSA
- [gMSA Active Directory Attacks](https://www.semperis.com/blog/golden-gmsa-attack/): performing the attack from windows
- [pyGoldenGMSA - Reversing Windows DLLs to Compute gMSA Passwords on Linux](https://felixbillieres.github.io/posts/pygoldengmsa-reversing-windows-dlls/): performing the attack from linux

# ADCS
  - [Certified Pre-Owned](https://specterops.io/wp-content/uploads/sites/3/2022/06/Certified_Pre-Owned.pdf): the paper that started everything (includes esc1-16)
  - [ADCS exploitation bible](https://github.com/ly4k/Certipy/wiki/06-%E2%80%90-Privilege-Escalation)
  - [ESC17](https://blog.digitrace.de/2026/01/using-adcs-to-attack-https-enabled-wsus-clients/)
  - [No PKINIT? No Problem](https://hwah.us/2025/04/12/no-pkinit-no-problem/)
