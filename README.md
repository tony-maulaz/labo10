# labo 10 - Number

- **Durée**: 4 périodes + travail à la maison

## Objectifs

Les principaux buts de ce travail de laboratoire sont :

- Apprendre à utiliser le générateur de nombres aléatoires.
- Apprendre à programmer un problème ludique et un peu plus complexe.
- Etudier et coder l’algorithme de la dichotomie sur un exemple concret.

Vous ne devez pas utiliser de tableaux.

## Cahier des charges

On vous demande de concevoir puis d’écrire un programme qui permet de jouer au jeu "le juste prix" de
deux manières :

- L’utilisateur doit deviner un nombre entre `0` et `1000`.
- L’ordinateur doit deviner un nombre entre `0` et `1000`.

`0` et `1000` sont des valeurs possibles.

La valeur max doit être définie par un `#define`.

Le choix de l’opération doit être effectué par l’intermédiaire d’un menu.
- Choisir le type de jeu
- Afficher la version
- Afficher l'aide
- Quitter

En utilisant le programme avec l'option `-n` on doit pouvoir fixer le nombre que
l'ordinateur choisi.

Sans option, programme standard
```console
$ ./number
```

Avec option
```console
$ ./number -n300
```

Si une option invalide est entrée, il faut retourner un code d'erreur.

Comme la taille d'une fonction est limitée à 30 lignes, il faut découper le programme en petites fonctions.

## Descriptif

### Jeu 1
- L'ordinateur choisit un nombre entier entre 0 et la valeur max définie (bornes incluses).
- L'utilisateur est invité à saisir un nombre entre les bornes définies.
- L'ordinateur indique si le nombre est trop grand, trop petit ou juste.
- Le système compte le nombre d’essais.
- Une fois le nombre trouvé, le programme affiche le nombre d'essai.
- Le jeu s'arrête et retourne au menu si le nombre est trouvé ou que l’utilisateur saisit la valeur `-1`.


### Jeu 2
- L'ordinateur doit deviner un nombre, il va le faire par dichotomie. C'est à dire qu'il va à chaque fois diviser
  le nombre à trouver par 2.
- L'utilisateur est invité à saisir `+`, `-`, `=`.
- Le système compte le nombre d’essais.
- Une fois le nombre trouvé, le programme affiche le nombre d'essai.
- Le jeu s'arrête et retourne au menu si le nombre est trouvé ou que l’utilisateur saisit la valeur `q`.

## Nombre aléatoire

Pour générer un nombre aléatoire, nous allons utiliser le générateur de la libraire `C`.

Pour utiliser le générateur, vous devez inclure :

```c
# include <stdlib .h>
# include <time.h>
```

Une seule fois au début du programme, il faut initialiser le générateur :

```c
srand (( unsigned int) time( NULL ));
```

Ensuite pour obtenir un nombre il faut faire :

```c
i = rand (); // nombre aléatoire entre 0 et RAND_MAX
```

### Questions

Répondez aux questions suivantes en commentaire dans votre code :

1. Quelle est la valeur de `RAND_MAX` ?
1. Que se passe-t-il si la fonction `srand` n'est pas appelée ?

1. Appel de `srand`
    - Appeler la fonction `srand` avec `1` et noter les 4 premiers chiffres obtenu par `rand()`
    - Recommencer l'opération
    - Que constater vous ?

1. Pourquoi utilise-t-on `time` avec la fonction `srand` ?

## Qualité du code

La qualité du code est évaluée. Pour mémoire :

- Un **en-tête** en début de programme décrit le fonctionnement du programme.
- Les variables sont nommées de façon **appropriées**.
- La **visibilité** (*scope*) des variables est minimum.
- Les **constantes littérales** sont nommées pour une meilleure compréhension.
- Les **types** de données doivent être appropriés au contenu ciblé.
- Le programme doit être **robuste**, les cas d'exception doivent être traités.
- Le nom des fonctions **doivent** être explicite et non trop générique.
- Les fonctions **doivent** avoir un commentaire explicatif.
- Une fonction ne doit pas dépasser 30 lignes de codes.
- Attention à la longueur des lignes.

## Liste des livrables

Mettre les fichiers suivant dans une archive **`zip`** (**pénalité pour les archives `rar`**) et la placer sur Cyberlearn
-  Code source
-  Le fichier exécutable

L’archive doit être déposée dans le répertoire "Labo10" de Cyberlearn (à la date
demandée sur le site INFO1 de Cyberlearn).

