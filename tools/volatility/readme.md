# Volatility

- website : <https://www.volatilityfoundation.org>
- github : <https://github.com/volatilityfoundation/volatility>
- wiki : <https://github.com/volatilityfoundation/volatility/wiki>

## Installation

1. Prendre une release standalone [ici](https://www.volatilityfoundation.org/releases)
2. La copier sur votre machine et l'ajouter dans votre PATH

> on va considérer qu'on peut joindre l'exécutable via la commande `vol`

## Utilisation 101

Il faut trouver le profil du dump

```bash
vol -f /path/to/dump imageinfo
```

ça va donner quelque chose comme ça :

```text
Volatility Foundation Volatility Framework 2.6
INFO    : volatility.debug    : Determining profile based on KDBG search...
          Suggested Profile(s) : Win7SP1x86_23418, Win7SP0x86, Win7SP1x86
                     AS Layer1 : IA32PagedMemoryPae (Kernel AS)
                     AS Layer2 : FileAddressSpace (/home/latour/Documents/Unamur/Security/playground/forensics-rootme/comand_and_control/data/ch2.dmp)
                      PAE type : PAE
                           DTB : 0x185000L
                          KDBG : 0x82929be8L
          Number of Processors : 1
     Image Type (Service Pack) : 0
                KPCR for CPU 0 : 0x8292ac00L
             KUSER_SHARED_DATA : 0xffdf0000L
           Image date and time : 2013-01-12 16:59:18 UTC+0000
     Image local date and time : 2013-01-12 17:59:18 +0100
```

Ce qui nous indique qu'on peut essayer 3 profils :

- Win7SP1x86_23418
- Win7SP0x86
- Win7SP1x86

Ensuite il y a une série d'outils qui s'utilisent généralement comme suit :

```bash
vol -f /path/to/dump --profile=<le profil> <tool>
```
