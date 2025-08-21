# Strings

## Création d'une chaîne de caractères

```python
# Guillemets simples
nom = 'Mario'
message = 'Mamma Mia!'

# Guillemets doubles
titre = "Paddington au Pérou"
phrase = "Il a dit : 'Bonjour !'"

# Guillemets triples (multilignes)
texte_long = """
Ceci est un texte
sur plusieurs lignes
avec des retours à la ligne
"""

# Guillemets triples avec simple quote
documentation = '''
Documentation avec des "guillemets doubles"
et des apostrophes dans le texte
'''

# String vide
vide = ""
vide2 = str()
```

## Accès aux caractères d'une chaîne

```python
mot = "Python"

# Indices positifs
print(mot[0])    # 'P' (premier caractère)
print(mot[1])    # 'y'
print(mot[5])    # 'n' (dernier caractère)

# Indices négatifs (depuis la fin)
print(mot[-1])   # 'n' (dernier)
print(mot[-2])   # 'o' (avant-dernier)
print(mot[-6])   # 'P' (premier, équivalent à mot[0])

# Vérification des limites
try:
    print(mot[10])  # IndexError
except IndexError:
    print("Index hors limites")
```

## F-Strings (Python 3.6+)

```python
nom = "Mario"
age = 25
score = 95.6789

# F-string
message = f"Bonjour {nom}, vous avez {age} ans"
print(message)

# Avec expressions
print(f"L'année prochaine, vous aurez {age + 1} ans")
print(f"Votre nom en majuscules: {nom.upper()}")

# Formatage numérique
print(f"Score: {score:.2f}")           # "Score: 95.68"
print(f"Score: {score:8.2f}")          # "Score:    95.68"
print(f"Pourcentage: {score/100:.1%}") # "Pourcentage: 95.7%"

# Formatage avec largeur
print(f"Nom: {nom:>10}")    # Aligné à droite
print(f"Nom: {nom:<10}")    # Aligné à gauche
print(f"Nom: {nom:^10}")    # Centré

# F-strings avec dictionnaires
personne = {"nom": "Bob", "age": 30}
print(f"Info: {personne['nom']} a {personne['age']} ans")

# F-strings multilignes
info = f"""
Nom: {nom}
Âge: {age}
Score: {score:.1f}
"""
print(info)
```
