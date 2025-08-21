# Dictionnaire

- le dictionnaire est une structure de données qui stocke des paires clé-valeur (équivalent à un objet en JavaScript).
- les dictionnaires sont utiles pour stocker des données associatives, où chaque clé est associée à une valeur spécifique.
- les clés sont uniques et immuables (par exemple, des chaînes de caractères ou des nombres).
- les valeurs peuvent être de n'importe quel type, y compris d'autres dictionnaires.


## Création d'un dictionnaire

```python
# Création d'un dictionnaire vide
mon_dictionnaire = {}
# Création d'un dictionnaire avec des paires clé-valeur
film = {
    "titre": "Paddington au Pérou",
    "annee": 2024,
    "directeur": "Doug Wilson"
}
```

## Accès aux éléments d'un dictionnaire

###
# Accès et Modification de Dictionnaires - Exemples Pratiques

film = {
    "titre": "Paddington au Pérou",
    "annee": 2024,
    "directeur": "Doug Wilson"
}

## 1. Accès aux Valeurs

```python
# Méthode 1: Accès direct avec [] (lève KeyError si absent)
titre = film["titre"]                    # "Paddington au Pérou"
annee = film["annee"]                    # 2024
directeur = film["directeur"]            # "Doug Wilson"

# ⚠️ Attention : KeyError si la clé n'existe pas
# genre = film["genre"]                  # ❌ KeyError!

# Méthode 2: get() - plus sûre (retourne None si absent)
titre = film.get("titre")                # "Paddington au Pérou"
genre = film.get("genre")                # None (pas d'erreur)

# get() avec valeur par défaut
genre = film.get("genre", "Non spécifié")       # "Non spécifié"
budget = film.get("budget", 0)                  # 0
note = film.get("note", "Pas encore noté")     # "Pas encore noté"

# Vérification avant accès
if "titre" in film:
    print(f"Le titre est: {film['titre']}")

if "genre" not in film:
    print("Genre non spécifié")

```
## Modification d'un dictionnaire

```python
# Modification directe
film["annee"] = 2025                     # Change l'année
film["directeur"] = "Dougal Wilson"      # Corrige le nom du réalisateur

# Modification conditionnelle
if film["annee"] < 2024:
    film["annee"] = 2024

# Modification avec get() pour éviter les erreurs
film["titre"] = film.get("titre", "").replace("au Pérou", "3")
# "Paddington 3"

print(film)
# {'titre': 'Paddington 3', 'annee': 2025, 'directeur': 'Dougal Wilson'}
```

## Ajout de Nouvelles Clés

```python
# Ajout direct
film["genre"] = "Comédie familiale"
film["duree"] = 106                      # en minutes
film["pays"] = "Royaume-Uni"
film["langue"] = "Anglais"

# Ajout avec setdefault() - ajoute seulement si absent
film.setdefault("note", 8.5)             # Ajoute note = 8.5
film.setdefault("titre", "Autre titre")   # Ne change pas le titre existant

# Ajout conditionnel
if "budget" not in film:
    film["budget"] = 50000000  # 50 millions

print(film)
# {
#     'titre': 'Paddington 3',
#     'annee': 2025,
#     'directeur': 'Dougal Wilson',
#     'genre': 'Comédie familiale',
#     'duree': 106,
#     'pays': 'Royaume-Uni',
#     'langue': 'Anglais',
#     'note': 8.5,
#     'budget': 50000000
# }
```

## Suppression d'éléments d'un dictionnaire

```python
# del - supprime une clé (lève KeyError si absent)
del film["pays"]                         # Supprime la clé "pays"

# pop() - supprime et retourne la valeur
duree = film.pop("duree")                # Supprime et retourne 106
langue = film.pop("langue", "Inconnu")   # Avec valeur par défaut

# popitem() - supprime et retourne le dernier élément (Python 3.7+)
derniere_cle, derniere_valeur = film.popitem()
print(f"Supprimé: {derniere_cle} = {derniere_valeur}")

# Suppression conditionnelle
if "budget" in film:
    del film["budget"]

# clear() - vide tout le dictionnaire
# film.clear()  # ⚠️ Vide complètement le dictionnaire
```

