# Environnement virtuel Python

## Qu'est-ce qu'un environnement virtuel ?

Un environnement virtuel est un espace isolé pour vos projets Python, avec ses propres packages et dépendances, séparé de votre installation Python système.
Pourquoi utiliser un environnement virtuel ?

### 1. Éviter les conflits de versions

- Projet A utilise Django 3.2
- Projet B utilise Django 4.1
- Sans environnement virtuel : conflit impossible à résoudre

### 2. Isolation des projets

- Chaque projet a ses propres dépendances
- Pas d'interférence entre projets

### 3. Faciliter le déploiement

- Liste exacte des packages nécessaires
- Reproduction de l'environnement ailleurs

## Création d'un environnement virtuel

```bash
# Créer l'environnement virtuel (Python 3.3+)

python -m venv nom_du_projet

# Activer l'environnement

# Sur Windows :
nom_du_projet\Scripts\activate
# Sur Mac/Linux :
source nom_du_projet/bin/activate

# Désactiver l'environnement
deactivate
```
## Installation de packages

```bash
# 1. Créer le projet
mkdir mon_projet
cd mon_projet

# 2. Créer l'environnement virtuel
python -m venv venv

# 3. Activer

venv\Scripts\activate  # Windows
# ou source venv/bin/activate  # Mac/Linux

# 4. Installer les packages
pip install requests pandas

# 5. Sauvegarder les dépendances
pip freeze > requirements.txt

# 6. Plus tard, recréer l'environnement
pip install -r requirements.txt
```