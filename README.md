# Enveloppe Convexe 2D

## Description

Ce projet implémente plusieurs algorithmes de calcul d'enveloppe convexe pour un ensemble de points dans le plan.

L'objectif est de comparer différentes approches algorithmiques permettant de déterminer le plus petit polygone convexe contenant l'ensemble des points d'entrée.

Le programme lit un ensemble de points depuis un fichier texte, calcule l'enveloppe convexe selon l'algorithme choisi puis écrit le résultat dans un fichier de sortie.

## Algorithmes implémentés

### 1. Slow Convex Hull

Algorithme naïf reposant sur l'examen de l'ensemble des couples de points.

Chaque segment candidat est testé afin de déterminer s'il appartient à l'enveloppe convexe.

Cette méthode possède une complexité élevée mais constitue une référence simple pour valider les résultats.

### 2. Convex Hull par tri

Algorithme incrémental basé sur le tri des points selon leurs coordonnées.

Trois méthodes de tri peuvent être utilisées :

* Tri par tas utilisant une structure arborescente.
* Tri par tas utilisant un tableau.
* Tri par sélection.

Cette approche permet d'obtenir une meilleure efficacité que la méthode naïve.

### 3. Rapid Convex Hull

Version optimisée du calcul de l'enveloppe convexe.

L'algorithme ne considère que les points susceptibles d'appartenir à l'enveloppe et réduit fortement le nombre de calculs nécessaires.

## Fonctionnalités

* Lecture d'un ensemble de points 2D depuis un fichier.
* Calcul de l'enveloppe convexe.
* Écriture de la solution dans un fichier.
* Tri des points selon différentes stratégies.
* Manipulation de structures de données dynamiques.
* Gestion de listes chaînées, arbres et tas.
* Comparaison de plusieurs approches algorithmiques.

## Structure du projet

### Dossier `src`

* `main.c` : point d'entrée du programme.
* `algo.c` : implémentation des algorithmes d'enveloppe convexe.
* `geometry.c` : primitives géométriques (points, segments, orientation, etc.).
* `sort.c` : algorithmes de tri.
* `heap.c` : implémentation des tas.
* `tree.c` : structures arborescentes.
* `list.c` : listes chaînées.
* `util.c` : fonctions utilitaires.

### Dossier `include`

Contient les fichiers d'en-tête associés aux différents modules :

* `algo.h`
* `geometry.h`
* `heap.h`
* `tree.h`
* `sort.h`
* `list.h`
* `util.h`

## Compilation

Le projet fournit un Makefile.

Compilation :

```bash
make
```

Nettoyage :

```bash
make clean
```

## Utilisation

Exécution générale :

```bash
make run in=fichier_entree.txt out=fichier_sortie.txt algo=<algorithme> [sort=<tri>]
```

### Choix de l'algorithme

| Valeur | Algorithme           |
| ------ | -------------------- |
| 1      | Slow Convex Hull     |
| 2      | Convex Hull avec tri |
| 3      | Rapid Convex Hull    |

### Choix du tri (algorithme 2 uniquement)

| Valeur | Méthode                |
| ------ | ---------------------- |
| 1      | Heap Sort avec arbre   |
| 2      | Heap Sort avec tableau |
| 3      | Tri par sélection      |

### Exemples

Algorithme naïf :

```bash
make run in=test.txt out=resultat.txt algo=1
```

Algorithme incrémental avec tri par tas :

```bash
make run in=test.txt out=resultat.txt algo=2 sort=2
```

Algorithme rapide :

```bash
make run in=test.txt out=resultat.txt algo=3
```

## Format des fichiers

### Entrée

Le fichier d'entrée contient :

```text
N
x1 y1
x2 y2
...
xN yN
```

où `N` représente le nombre de points.

### Sortie

Le fichier de sortie contient les sommets de l'enveloppe convexe dans l'ordre de parcours du polygone.

## Technologies utilisées

* Langage C
* Makefile
* Structures de données dynamiques
* Géométrie algorithmique
* Listes chaînées
* Tas binaires
* Arbres

## Auteurs

Projet réalisé dans le cadre d'un enseignement d'algorithmique et de géométrie computationnelle.
