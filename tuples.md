# Tuples

- Les tuples sont des collections ordonnées et immuables d'éléments en Python. Contrairement aux listes, les tuples ne peuvent pas être modifiés après leur création, ce qui les rend utiles pour stocker des données constantes.

## Création de tuples

```python
# Création
coordonnees = (10, 20)
vide = ()
un_element = (42,)  # ⚠️ Virgule obligatoire pour un seul élément

# Sans parenthèses (tuple packing)
point = 10, 20, 30
personne = "Mario", 25, "Nintendo"

# Conversion depuis autres types
liste_vers_tuple = tuple([1, 2, 3])
string_vers_tuple = tuple("abc")  # ('a', 'b', 'c')

# Tuple hétérogène
mixed = ("Mario", 25, True, [1, 2, 3])

# ✅ IMMUTABLE - caractéristique clé
# coordonnees[0] = 15  # ❌ TypeError!
```
## Unpacking de tuples

```python
# Unpacking
point = (10, 20)
x, y = point  # x=10, y=20

# Unpacking multiple
personne = ("Mario", 25, "Nintendo", "Héros")
nom, age, ville, metier = personne

# Unpacking avec * (Python 3+)
nombres = (1, 2, 3, 4, 5)
premier, *milieu, dernier = nombres
# premier=1, milieu=[2,3,4], dernier=5

# Échange de variables 
a, b = 10, 20
a, b = b, a 
print(f"a={a}, b={b}")  # a=20, b=10

# Unpacking partiel
donnees = ("Mario", 25, "Nintendo", "Python", "SQL")
nom, age, *reste = donnees
# nom="Mario", age=25, reste=["Nintendo", "Python", "SQL"]
```