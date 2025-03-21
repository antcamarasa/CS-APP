# Contenu
## Une Introduction aux Systèmes Informatiques
Un système informatique se compose de matériel et de logiciels systèmes qui fonctionnent ensemble pour exécuter des programmes d'application. Les implémentations spécifiques des systèmes changent au fil du temps, mais les concepts sous-jacents ne changent pas. Tous les systèmes informatiques possèdent des composants matériels et logiciels similaires qui accomplissent des fonctions similaires. Ce livre est destiné aux programmeurs qui veulent améliorer leur savoir-faire en comprenant comment ces composants fonctionnent et comment ils influent sur la justesse et la performance de leurs programmes.

Vous êtes sur le point de commencer un voyage passionnant. Si vous vous consacrez à l'apprentissage des concepts de ce livre, vous serez en route pour devenir un "super programmeur" rare, éclairé par la compréhension du système informatique sous-jacent et de son impact sur vos programmes d'application.

Vous apprendrez des compétences pratiques telles que comment éviter les erreurs numériques étranges causées par la façon dont les ordinateurs représentent les nombres. Vous apprendrez à optimiser votre code C en utilisant des astuces intelligentes qui exploitent les conceptions des processeurs et des systèmes de mémoire modernes. Vous apprendrez comment le compilateur implémente les appels de procédures et comment utiliser cette connaissance pour éviter les failles de sécurité liées aux vulnérabilités de débordement de tampon qui touchent les logiciels réseau et Internet. Vous apprendrez à reconnaître et éviter les erreurs de liaison qui embrouillent le programmeur moyen. Vous apprendrez à écrire votre propre shell Unix, votre propre package d'allocation dynamique de mémoire, et même votre propre serveur Web. Vous découvrirez les promesses et les pièges de la concurrence, un sujet de plus en plus important à mesure que plusieurs cœurs de processeur sont intégrés sur une seule puce.

Dans leur texte classique sur le langage de programmation C [61], Kernighan et Ritchie présentent aux lecteurs le programme "hello" illustré à la Figure 1.1. Bien que "hello" soit un programme très simple, chaque partie majeure du système doit fonctionner de concert pour qu'il puisse s'exécuter jusqu'à sa fin. En un sens, l'objectif de ce livre est de vous aider à comprendre ce qui se passe et pourquoi lorsque vous exécutez "hello" sur votre système.

Nous commençons notre étude des systèmes en suivant la durée de vie du programme "hello", depuis le moment où il est créé par un programmeur, jusqu'à son exécution sur un système, l'impression de son simple message et son arrêt. À mesure que nous suivons la durée de vie du programme, nous introduirons brièvement les concepts clés, la terminologie et les composants qui interviennent. Les chapitres suivants développeront ces idées.

### code/intro/hello.c
```c
#include <stdio.h>

int main() {
    printf("hello, world\n");
    return 0;
}

```
```c
| Décimal | Hex  | Binaire    | Caractère |
|---------|------|-----------|-----------|
| 32      | 0x20 | 00100000  | (espace)  |
| 33      | 0x21 | 00100001  | !         |
| 34      | 0x22 | 00100010  | "         |
| 35      | 0x23 | 00100011  | #         |
| 36      | 0x24 | 00100100  | $         |
| 37      | 0x25 | 00100101  | %         |
| 38      | 0x26 | 00100110  | &         |
| 39      | 0x27 | 00100111  | '         |
| 40      | 0x28 | 00101000  | (         |
| 41      | 0x29 | 00101001  | )         |
| 42      | 0x2A | 00101010  | *         |
| 43      | 0x2B | 00101011  | +         |
| 44      | 0x2C | 00101100  | ,         |
| 45      | 0x2D | 00101101  | -         |
| 46      | 0x2E | 00101110  | .         |
| 47      | 0x2F | 00101111  | /         |
| 48      | 0x30 | 00110000  | 0         |
| 49      | 0x31 | 00110001  | 1         |
| 50      | 0x32 | 00110010  | 2         |
| 51      | 0x33 | 00110011  | 3         |
| 52      | 0x34 | 00110100  | 4         |
| 53      | 0x35 | 00110101  | 5         |
| 54      | 0x36 | 00110110  | 6         |
| 55      | 0x37 | 00110111  | 7         |
| 56      | 0x38 | 00111000  | 8         |
| 57      | 0x39 | 00111001  | 9         |
| 58      | 0x3A | 00111010  | :         |
| 59      | 0x3B | 00111011  | ;         |
| 60      | 0x3C | 00111100  | <         |
| 61      | 0x3D | 00111101  | =         |
| 62      | 0x3E | 00111110  | >         |
| 63      | 0x3F | 00111111  | ?         |
| 64      | 0x40 | 01000000  | @         |
| 65      | 0x41 | 01000001  | A         |
| 66      | 0x42 | 01000010  | B         |
| 67      | 0x43 | 01000011  | C         |
| 68      | 0x44 | 01000100  | D         |
| 69      | 0x45 | 01000101  | E         |
| 70      | 0x46 | 01000110  | F         |
| 71      | 0x47 | 01000111  | G         |
| 72      | 0x48 | 01001000  | H         |
| 73      | 0x49 | 01001001  | I         |
| 74      | 0x4A | 01001010  | J         |
| 75      | 0x4B | 01001011  | K         |
| 76      | 0x4C | 01001100  | L         |
| 77      | 0x4D | 01001101  | M         |
| 78      | 0x4E | 01001110  | N         |
| 79      | 0x4F | 01001111  | O         |
| 80      | 0x50 | 01010000  | P         |
| 81      | 0x51 | 01010001  | Q         |
| 82      | 0x52 | 01010010  | R         |
| 83      | 0x53 | 01010011  | S         |
| 84      | 0x54 | 01010100  | T         |
| 85      | 0x55 | 01010101  | U         |
| 86      | 0x56 | 01010110  | V         |
| 87      | 0x57 | 01010111  | W         |
| 88      | 0x58 | 01011000  | X         |
| 89      | 0x59 | 01011001  | Y         |
| 90      | 0x5A | 01011010  | Z         |
```
## 1.1 L'Information est des Bits + du Contexte
Notre programme "hello" commence sa vie en tant que programme source (ou fichier source) que le programmeur crée avec un éditeur et enregistre dans un fichier texte appelé "hello.c". Le programme source est une séquence de bits, chacun ayant une valeur de 0 ou 1, organisés en morceaux de 8 bits appelés octets. Chaque octet représente un caractère texte dans le programme.
La plupart des systèmes informatiques représentent les caractères texte à l'aide de la norme ASCII qui attribue à chaque caractère une valeur entière de taille octet unique. Par exemple, la Figure 1.2 montre la représentation ASCII du programme hello.c.
Le programme hello.c est stocké dans un fichier comme une séquence d'octets. Chaque octet a une valeur entière qui correspond à un caractère. Par exemple, le premier octet a la valeur entière 35, qui correspond au caractère ‘#’. Le deuxième octet a la valeur entière 105, qui correspond au caractère ‘i’, et ainsi de suite. Notez que chaque ligne de texte est terminée par le caractère invisible de nouvelle ligne ‘\n’, qui est représenté par la valeur entière 10. Les fichiers tels que hello.c qui sont exclusivement constitués de caractères ASCII sont appelés fichiers texte. Tous les autres fichiers sont appelés fichiers binaires.
La représentation de hello.c illustre une idée fondamentale : Toutes les informations dans un système — y compris les fichiers sur disque, les programmes stockés en mémoire, les données utilisateur stockées en mémoire et les données transférées à travers un réseau — sont représentées par une série de bits. La seule chose qui distingue les différents objets de données est le contexte dans lequel nous les observons. Par exemple, dans différents contextes, la même séquence d'octets peut représenter un entier, un nombre à virgule flottante, une chaîne de caractères ou une instruction machine.

En tant que programmeurs, nous devons comprendre les représentations machines des nombres car elles ne sont pas les mêmes que les entiers et les nombres réels. Elles sont des approximations finies qui peuvent se comporter de manière inattendue. Cette idée fondamentale est explorée en détail au chapitre 2.

## 1.2 Les Programmes sont Traduits par d'autres Programmes en Différentes Formes

## 1.3 Il est Prudent de Comprendre Comment Fonctionnent les Systèmes de Compilation
## 1.4 Les Processeurs Lisent et Interprètent les Instructions Stockées en Mémoire
### 1.4.1 Organisation Matérielle d'un Système
### 1.4.2 Exécution du Programme "hello"
## 1.5 Les Caches Comptent
## 1.6 Les Dispositifs de Stockage forment une Hiérarchie
## 1.7 Le Système d'Exploitation Gère le Matériel
### 1.7.1 Processus
### 1.7.2 Threads
### 1.7.3 Mémoire Virtuelle
### 1.7.4 Fichiers
## 1.8 Les Systèmes Communiquent avec d'Autres Systèmes via des Réseaux
## 1.9 Thèmes Importants
### 1.9.1 La Loi d'Amdahl
### 1.9.2 Concurrence et Parallélisme
### 1.9.3 L'Importance des Abstractions dans les Systèmes Informatiques
### 1.10 Résumé
#### Solutions aux Problèmes Pratiques
