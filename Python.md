---
title: Python
subtitle: programmer en Python
author: Damien Belvèze
date: 08-02-2021
link_citations: true
bibliography: mylibrary.bib
biblio_style: csl\ieee.csl
aliases: [Py]
tags: [Programmation]
---

# ouvrir, écrire, modifier, fermer un fichier
Ouvre un fichier et le lit tout d'un coup
"r" = read ([[@SchultzPythonpourSHS2021]], p81)
> ouvre un fichier avec la fonction *open* en donnant le chemin du fichier et le mode lecture "r" puis stocke le lien vers le fichier ouvert dans la variable **fichier** 


``````
fichier=open("data1.txt", "r")
contenu=fichier.read()
``````

``````
fichier.close()
print(contenu[0:40])
``````

ferme le fichier, imprime les premières lignes (de la première ligne à la ligne 40)

# modifier des caractères dans un fichier

``````
# ouvre et lit le fichier titre.md
with open('titre.md', 'r') as file :
  filedata = file.read()

# remplace dans ce fichier le e par un a
filedata = filedata.replace('e', 'a')

# écrit un fichier avec le texte modifié dont le nom est file.txt
with open('file.txt', 'w') as file:
  file.write(filedata)
``````

# supprimer des lignes qui contiennent une suite de caractères

Programme utilisé et testé dans le cadre de la [[faire une revue de littérature avec Zotero|revue de littérature avec Zotero]]

Contexte : les exports en RIS des bases de données comme Cochrane ou WOS contiennent des descripteurs qui sont indésirables (KW) lors de l'import des fichiers dans [[Zotero]]. Pour plus de clarté, aucun marqueur ne doit être hérité au cours de l'import. 
Il s'agit donc d'effacer ces descripteurs qui se présentent comme suit dans les fichiers d'import : 

KW   - descripteurs

Le script suivant permet de générer un fichier (output.txt) qui copie toutes les lignes du fichier d'import (input.txt) à l'exception de celles qui contiennent la chaîne de caractères "KW   -" (prendre en compte le tirer de telle sorte de ne pas éléminer de faux positifs, par exemple dans les noms d'auteur)

``````python
with open('input.txt', 'r') as inp, open('output.txt', 'w') as out:
    for line in inp:
        if 'KW  -' not in line:
            out.write(line)
``````


# bibliographie



langage de programmation

voir tutoriel de base sur [Focus](https://focus.univ-rennes1.fr/python1)

