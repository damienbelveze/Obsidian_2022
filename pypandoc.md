---
title: pypandoc
subtitle:
author: Damien Belvèze
date: 19-01-2022
link_citations: true
bibliography: mylibrary.bib
biblio_style: csl\ieee.csl
aliases: [Pandoc with Python, Pandoc avec Python]
tags: [Python, programmation]
---

# installation

pré-requis : avoir installé Python
Sur windows : 

``````bash
py -m pip install pypandoc
``````

# conversion simple

``````python
import pypandoc
pypandoc.convert_file('D:/Home/dbelveze/Desktop/titre.odt', format='odt', to='md', outputfile='D:/Home/dbelveze/Desktop/titre.md')
``````

# conversion avec suppression de caractères indésirables
``````python
import os
import pypandoc
fichier = input("Quel fichier voulez-vous convertir ?")
with open(fichier, 'r') as file :
  filedata = file.read()

# Replace the target string
filedata = filedata.replace('[[', '').replace(']]','')

# Write the file out again
with open('file.txt', 'w') as file:
  file.write(filedata)
# convert modified file into open document file
pypandoc.convert_file('file.txt', format='md', to='pdf', outputfile='new_file.pdf')
# delete file text
os.remove('file.txt')
``````




# bibliographie

