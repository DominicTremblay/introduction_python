# Python Lists

## Lists

- Les Listes (Array dans d'autres langages) en Python sont des collections ordonnées et modifiables d'éléments.
- Elles peuvent contenir des éléments de différents types, y compris d'autres listes.
- Les listes sont dynamiques, ce qui signifie que leur taille peut changer au cours de l'exécution du programme.
- On utilise couramment des méthodes comme `append()`, `remove()`, `sort()`, `filter()`, `map()` pour manipuler les listes.

## Création d'une liste

```python
# Création d'une liste vide
ma_liste = []
# Création d'une liste avec des éléments
ma_liste = [1, 2, 3, 4, 5]
# Création d'une liste avec différents types d'éléments
ma_liste = [1, "deux", 3.0, True, [5, 6]]
```
- Déclaration des types de données dans une liste :

```python
from typing import List, Union

# Liste d'entiers
notes: List[int] = [12, 15, 18]

# Liste de chaînes
noms: List[str] = ["Peach", "Mario", "Luigi"]

# Liste contenant des entiers OU des chaînes
mix: List[Union[int, str]] = [1, "Peach", 2, "Mario"]

# Version Python 3.10+
mix2: list[int | str] = [1, "Peach", 2, "Mario"]
```

## Accès aux éléments d'une liste

- par index :
```python
ma_liste = [1, 2, 3, 4, 5]
# Accès au premier élément
premier_element = ma_liste[0]  # 1
# Accès au derniers eléments  
dernier_element = ma_liste[-1]  # 5
avant_dernier_element = ma_liste[-2]  # 4
```
- par tranche (slicing) :
```python
print(ma_liste[1:4])   # [1, 2, 3]
print(ma_liste[:3])    # [1, 2, 3] (début jusqu'à index 3)
print(ma_liste[2:])    # [3, 4, 5] (index 2 jusqu'à la fin)
print(ma_liste[::2])   # [1, 3, 5] (tous les 2 éléments)
print(ma_liste[::-1])  # [5, 4, 3, 2, 1] (inverser)

# Slicing pour modifier
ma_liste[1:3] = [10, 20]  # Remplace éléments aux indices 1 et 2

# Slicing pour effacer
del ma_liste[1:3]         # efface index de 1 à 3 [1, 4, 5]
```

## Unpacking d'une liste

- Équivalent à destructuration en JavaScript.

```python
film = ["Paddington au pérou", 2024, "Doug Wilson"]
titre, annee, realisateur = film
print(titre)          # Paddington au pérou
print(annee)          # 2024
print(realisateur)    # Doug Wilson

# Unpacking avec *
nombres = [1, 2, 3, 4, 5]
premier, *milieu, dernier = nombres
# premier=1, milieu=[2,3,4], dernier=5
```

## Modification et suppression d'éléments
- Modification d'un élément :
```python
ma_liste = [1, 2, 3, 4, 5]
ma_liste[2] = 10          # Change le troisième élément en 10
# Slicing pour modifier
ma_liste[1:3] = [10, 20]  # Remplace éléments aux indices 1 et 2


# Suppression d'un élément
ma_liste.remove(10)       # Supprime le premier élément égal à 10
# Suppression par index
del ma_liste[1]           # Supprime l'élément à l'index 1
# Suppression du dernier élément
ma_liste.pop()            # Supprime et retourne le dernier élément
# Suppression de tous les éléments
ma_liste.clear()          # Vide la liste
# Slicing pour effacer
del ma_liste[1:3]         # efface index de 1 à 3 [1, 4, 5]
```

## Itération sur une liste

```python
ma_liste = [1, 2, 3, 4, 5]
for element in ma_liste:
    print(element)
# Itération avec index
for index, element in enumerate(ma_liste):
    print(f"Index {index}: {element}")
```
## Opérations courantes sur les listes

```python
ma_liste = [1, 2, 3, 4, 5]
# Longueur de la liste
longueur = len(ma_liste)  # 5
# Vérifier la présence d'un élément
est_present = 3 in ma_liste  # True
# Concaténation de listes
nouvelle_liste = ma_liste + [6, 7, 8]  # [1, 2, 3, 4, 5, 6, 7, 8]
# Répétition de listes
repetition = ma_liste * 2  # [1, 2, 3, 4, 5, 1, 2, 3, 4, 5]
```




