# Compréhension de liste

- La compréhension de liste est une syntaxe concise pour créer des listes en Python.
- Elle permet de générer une nouvelle liste en appliquant une expression à chaque élément d'une séquence (comme une liste ou un itérable) et en filtrant les éléments selon une condition.
- La syntaxe générale est : `[expression for item in iterable if condition]`.

```Python
nombres = [1, 2, 3, 4, 5]

# Au lieu de:
carres = []
for x in nombres:
    carres.append(x**2)

# Préférer:
carres = [x**2 for x in nombres]
print(carres)  # [1, 4, 9, 16, 25]

# Avec condition
pairs = [x for x in nombres if x % 2 == 0]
print(pairs)  # [2, 4]

# Avec transformation et condition
mots = ["python", "java", "javascript", "go"]
longs_maj = [mot.upper() for mot in mots if len(mot) > 4]
print(longs_maj)  # ['PYTHON', 'JAVASCRIPT']
```


