# Itérations

## Itérations sur une string


```python
for caractere in texte:
    print(f"'{caractere}'")
# Résultat : 'P', 'y', 't', 'h', 'o', 'n'

# Avec enumerate pour avoir l'index
for index, caractere in enumerate(texte):
    print(f"Position {index}: '{caractere}'")
# 0: 'P', 1: 'y', 2: 't', etc.

```
## Itérations sur une liste

```python

ma_liste = [10, 20, 30, 40, 50]

for element in ma_liste:
    print(element)

# index et valeur de chaque élément
for index, element in enumerate(ma_liste):
    print(f"Index {index}: {element}")

# Avec un numéro de départ pour l'index
for numero, element in enumerate(ma_liste, start=1):
    print(f"Élément {numero}: {element}")

# modification conditionnelle
nombres = [1, 2, 3, 4, 5]
for i, nombre in enumerate(nombres):
    if nombre % 2 == 0:
        nombres[i] = nombre * 10
print(nombres)  # [1, 20, 3, 40, 5]

# Itération en sens inverse
for element in reversed(ma_liste):
    print(element)  # 50, 40, 30, 20, 10

# Itération avec slicing
for element in ma_liste[1:4]:  # de l'index 1 à 3
    print(element)  # 20, 30, 40

## Itération sur un dictionnaire

```python
###
# Itérations Essentielles sur les Dictionnaires

film = {
    "titre": "Paddington au Pérou",
    "annee": 2024,
    "directeur": "Doug Wilson",
    "genre": "Comédie familiale",
    "note": 8.5
}

```python
# Itération directe sur les clés 
for cle in film:
    print(f"Clé: {cle}")
    print(f"Valeur: {film[cle]}")

# Avec .keys()
for cle in film.keys():
    print(f"{cle}: {film[cle]}")

# Avec enumerate pour numéroter
for index, cle in enumerate(film.keys()):
    print(f"{index+1}. {cle}")

# Itération sur les valeurs
for valeur in film.values():
    print(f"Valeur: {valeur} (type: {type(valeur).__name__})")

# Avec enumerate
for index, valeur in enumerate(film.values()):
    print(f"Valeur {index}: {valeur}")

## Itération sur les Paires Clé-Valeur

for cle, valeur in film.items():
    print(f"{cle}: {valeur}")

# Avec enumerate pour numéroter
for index, (cle, valeur) in enumerate(film.items(), 1):
    print(f"{index}. {cle}: {valeur}")


```
