# Exemple complet illustrant les concepts de base de Python avec le thème de Super Mario

```Python
# 1. STRINGS - Dialogues et noms
nom_heros = "Mario"
message_princesse = "Merci Mario ! Mais notre princesse est dans un autre château !"
dialogue_bowser = """
Grrr ! Je suis Bowser, le roi des Koopas !
Tu ne sauveras jamais la princesse !
Mouahahaha !
"""

print(f"Bonjour, je suis {nom_heros} !")
print(f"Message: {message_princesse}")

# 2. TUPLES - Coordonnées fixes des châteaux
chateau_1 = (100, 50)
chateau_2 = (250, 75)
chateau_final = (500, 100)

# Unpacking des coordonnées
x, y = chateau_1
print(f"Château 1 situé en ({x}, {y})")

# 3. LISTES - Inventaire de Mario (modifiable)
inventaire_mario = ["champignon", "fleur de feu", "étoile"]
pieces_collectees = [100, 200, 500, 1000]

# Ajouter des objets
inventaire_mario.append("champignon 1-UP")
inventaire_mario.extend(["cape", "bottes"])

# Opérations sur les listes
print(f"Mario a {len(inventaire_mario)} objets")
print(f"Premier objet: {inventaire_mario[0]}")
print(f"Derniers objets: {inventaire_mario[-2:]}")

# Slicing pour organiser l'inventaire
objets_speciaux = inventaire_mario[2:4]  # étoile et champignon 1-UP

# 4. DICTIONNAIRES - Profils des personnages
mario = {
    "nom": "Mario",
    "profession": "plombier",
    "vies": 3,
    "score": 0,
    "niveau_actuel": 1,
    "power_up": "normal"
}

luigi = {
    "nom": "Luigi",
    "profession": "plombier",
    "vies": 3,
    "score": 0,
    "couleur_preference": "vert"
}

princesse_peach = {
    "nom": "Princesse Peach",
    "statut": "capturée",
    "château": "Château de Bowser",
    "royaume": "Royaume Champignon"
}

# Modifier le profil
mario["score"] += 500
mario["power_up"] = "Super Mario"

# Vérifier les clés
if "vies" in mario:
    print(f"{mario['nom']} a {mario['vies']} vies restantes")

# 5. ITÉRATIONS - Parcourir les niveaux
mondes = ["Monde 1-1", "Monde 1-2", "Monde 1-3", "Monde 1-4"]

print("\n=== AVENTURE DE MARIO ===")
for niveau in mondes:
    print(f"🏃 Mario entre dans {niveau}")

# Avec enumerate pour numéroter
for numero, monde in enumerate(mondes, 1):
    print(f"Niveau {numero}: {monde}")

# Parcourir l'inventaire avec index
for i, objet in enumerate(inventaire_mario):
    print(f"Slot {i+1}: {objet}")

# Itérer sur le profil de Mario
print(f"\n=== PROFIL DE {mario['nom'].upper()} ===")
for cle, valeur in mario.items():
    print(f"{cle.replace('_', ' ').title()}: {valeur}")

# 6. COMPRÉHENSIONS DE LISTE - Génération rapide
# Créer une liste des scores par niveau
scores_niveaux = [x * 100 for x in range(1, 9)]  # [100, 200, 300, ..., 800]

# Filtrer les gros scores
gros_scores = [score for score in pieces_collectees if score >= 500]

# Transformer les noms en majuscules
personnages = ["mario", "luigi", "peach", "bowser"]
noms_majuscules = [nom.upper() for nom in personnages]

# Power-ups avec condition
objets_magiques = ["champignon", "fleur", "étoile", "cape", "bottes"]
power_ups = [obj for obj in objets_magiques if len(obj) > 5]

print(f"Power-ups spéciaux: {power_ups}")

# 7. FONCTIONS - Actions de Mario
def saluer(nom="Mario", action="saute"):
    """Fonction pour faire saluer Mario"""
    return f"{nom} fait l'action de {action} !"

def collecter_piece(joueur_dict, valeur_piece=100):
    """Ajoute une pièce au score du joueur"""
    joueur_dict["score"] += valeur_piece
    print(f"🪙 {joueur_dict['nom']} collecte une pièce ! Score: {joueur_dict['score']}")

def changer_power_up(joueur_dict, nouveau_power_up):
    """Change le power-up du joueur"""
    ancien = joueur_dict.get("power_up", "normal")
    joueur_dict["power_up"] = nouveau_power_up
    return f"{joueur_dict['nom']} passe de {ancien} à {nouveau_power_up}"

def verifier_victoire(score_actuel, score_objectif=5000):
    """Vérifie si Mario a gagné"""
    if score_actuel >= score_objectif:
        return "🎉 Félicitations ! Mario a sauvé la princesse !"
    else:
        return f"Continue ! Il te faut {score_objectif - score_actuel} points de plus."

# 8. SIMULATION DE JEU
print("\n=== 🎮 SIMULATION DE JEU ===")

# Mario commence son aventure
print(saluer())
print(saluer("Luigi", "court"))

# Collecte des pièces
for _ in range(3):
    collecter_piece(mario, 200)

# Changement de power-up
print(changer_power_up(mario, "Mario Feu"))

# Vérification de victoire
print(verifier_victoire(mario["score"]))

# Combat final avec Bowser
ennemis_vaincus = ["Goomba", "Koopa", "Piranha", "Bowser Jr.", "Bowser"]
for ennemi in ennemis_vaincus:
    print(f"⚔️ Mario affronte {ennemi}")
    collecter_piece(mario, 500)

print("\n=== 👑 RÉSULTAT FINAL ===")
print(f"Score final de Mario: {mario['score']}")
print(verifier_victoire(mario["score"]))

# Création d'un tableau des scores avec compréhension
tableau_scores = [
    f"{monde}: {score} pts" 
    for monde, score in zip(mondes, scores_niveaux)
]

print("\n=== 📊 TABLEAU DES SCORES ===")
for ligne in tableau_scores:
    print(ligne)

# String finale avec f-string multiligne
rapport_final = f"""
🏆 RAPPORT DE MISSION
====================
Héros: {mario['nom']}
Power-up final: {mario['power_up']}
Score total: {mario['score']} points
Vies restantes: {mario['vies']}
Statut: {'VICTOIRE !' if mario['score'] >= 5000 else 'Mission en cours...'}

Objets collectés: {', '.join(inventaire_mario)}
Pièces d'or ramassées: {sum(pieces_collectees)}

"Merci Mario ! Tu es notre héros !" - Princesse Peach 👑
"""

print(rapport_final)
```