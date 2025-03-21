# Contenu
## Une Introduction aux Systèmes Informatiques
Un système informatique se compose de matériel et de logiciels systèmes qui fonctionnent ensemble pour exécuter des programmes d'application. Les implémentations spécifiques des systèmes changent au fil du temps, mais les concepts sous-jacents ne changent pas. Tous les systèmes informatiques possèdent des composants matériels et logiciels similaires qui accomplissent des fonctions similaires. Ce livre est destiné aux programmeurs qui veulent améliorer leur savoir-faire en comprenant comment ces composants fonctionnent et comment ils influent sur la justesse et la performance de leurs programmes.

Vous êtes sur le point de commencer un voyage passionnant. Si vous vous consacrez à l'apprentissage des concepts de ce livre, vous serez en route pour devenir un "super programmeur" rare, éclairé par la compréhension du système informatique sous-jacent et de son impact sur vos programmes d'application.

Vous apprendrez des compétences pratiques telles que comment éviter les erreurs numériques étranges causées par la façon dont les ordinateurs représentent les nombres. Vous apprendrez à optimiser votre code C en utilisant des astuces intelligentes qui exploitent les conceptions des processeurs et des systèmes de mémoire modernes. Vous apprendrez comment le compilateur implémente les appels de procédures et comment utiliser cette connaissance pour éviter les failles de sécurité liées aux vulnérabilités de débordement de tampon qui touchent les logiciels réseau et Internet. Vous apprendrez à reconnaître et éviter les erreurs de liaison qui embrouillent le programmeur moyen. Vous apprendrez à écrire votre propre shell Unix, votre propre package d'allocation dynamique de mémoire, et même votre propre serveur Web. Vous découvrirez les promesses et les pièges de la concurrence, un sujet de plus en plus important à mesure que plusieurs cœurs de processeur sont intégrés sur une seule puce.

Dans leur texte classique sur le langage de programmation C [61], Kernighan et Ritchie présentent aux lecteurs le programme "hello" illustré à la Figure 1.1. Bien que "hello" soit un programme très simple, chaque partie majeure du système doit fonctionner de concert pour qu'il puisse s'exécuter jusqu'à sa fin. En un sens, l'objectif de ce livre est de vous aider à comprendre ce qui se passe et pourquoi lorsque vous exécutez "hello" sur votre système.

Nous commençons notre étude des systèmes en suivant la durée de vie du programme "hello", depuis le moment où il est créé par un programmeur, jusqu'à son exécution sur un système, l'impression de son simple message et son arrêt. À mesure que nous suivons la durée de vie du programme, nous introduirons brièvement les concepts clés, la terminologie et les composants qui interviennent. Les chapitres suivants développeront ces idées.

###code/intro/hello.c
```c
#include <stdio.h>

int main() {
    printf("hello, world\n");
    return 0;
}

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
