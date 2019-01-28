Story: Transporteurs automatiques d'espèces
===========================================

# Enoncé

La société FooBar© a décidé de développer un système révolutionnaire de transporteurs automatiques d'espèces, sur surfaces rectangulaires, et dédiés à approvisionner son modèle de caisses enregistreuses automatiques.

## Position
Chaque transporteurs peut être programmée pour parcourir l'intégralité de la surface.
Sa position est représentée par une combinaison de coordonnées **(x,y)** et d'une lettre indiquant l'orientation selon la notation cardinale anglaise **[N|E|W|S]**.

La surface de parcours est divisée en grille pour simplifier la navigation.
Par exemple, la position d'un transporteur peut être **0, 0, N**, ce qui signifie qu'il se situe dans le coin inférieur gauche de la zone marchande, et orientée vers le Nord.

## Contrôle du parcours
Pour contrôler le parcours, une séquence simple de lettres est transmise à chaque transporteurs.
Les lettres possibles sont **R**, **L** et **F**.
* **R** fait pivoter le transporteur de 90° à droite
* **L** fait pivoter le transporteur de 90° à gauche
* **F** fait avancer le transporteur d'une case dans la direction à laquelle elle fait face sans changer aucune autre propriété.

*Si la position après mouvement est en dehors de la surface, le transporteur ne bouge pas, conserve son orientation et traite la commande suivante.*


## Initialisation du parcours
Pour programmer un transporteur, un fichier en entrée est fourni. Il se construit comme suit :
* La première ligne correspond aux coordonnées du coin supérieur droit de la surface de commerce. Le format est **2 entiers séparés par un espace**. *Celles
du coin inférieur gauche sont supposées être (0, 0)*.
* La suite du fichier permet de piloter tous les transporteurs qui ont été déployés. Deux lignes permettent de les configurer :
    * La position initiale,  ainsi que son orientation, est définie sur la première ligne. Le format est **2 entiers et une lettre séparés par un espace**
    * Une série d'instruction, sur la deuxième ligne, permet de programmer le parcours du transporteur. Ces instructions sont une suite de caractères sans espaces.

Chaque transporteur se déplace de façon séquentielle, ce qui signifie que le second transporteur ne bouge que lorsque le premier a exécuté intégralement sa série d'instructions.

Lorsqu'un trasnporteur achève une série d'instruction, il communique sa **position et son orientation**.

# Objectif
Concevoir et écrire un programme implémentant la spécification ci-dessus et passant le test ci-après

## Input
Le fichier suivant est fourni en entrée :
```
5 5
1 2 N
LFLFLFLFF
3 3 E
FFLFFLFLLF
```

## Output
```
1 3 N
5 1 E
```
