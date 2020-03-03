# John the ripper

- website : <https://www.openwall.com/john>
- github : <https://github.com/magnumripper/JohnTheRipper>

La doc est dans le dossier `doc` du github.

## Installation

Ça pique un peu mais il faut compiler le programme soi même.
Après on en sort vivant ya pas de soucis ;)

Il faut lire la doc sur `doc/INSTALL` et `doc/INSTALL-UBUNTU` et tout se passe bien.

Vous pouvez le mettre dans votre `HOME` et ajouter un alias dans votre `.bashrc` pour avoir la commande `john` accessible de partout ;)

```bash
echo "alias john='/path/to/john/the/ripper/install/folder/run/john'" >> ~/.bashrc
```

## Utilisation 101

Généralemnet John est assez grand pour comprendre ce qu'on attend de lui.
Il risque de donner des conseils d'utilisation, il ne faut pas hésiter à l'écouter.

```bash
echo "<le password à hash>" > file
john file
```

Pour tester les strings d'une liste (un mot par ligne) :

```bash
john --wordlist=/path/to/the/list file
```

Pour afficher les passwords crackés :

```bash
john --show file
```
