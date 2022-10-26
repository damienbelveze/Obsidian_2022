---
title: 
subtitle:
author: Damien Belvèze
date: 01-12-2021
link_citations: true
bibliography: mylibrary.bib
biblio_style: csl\ieee.csl
aliases: []
tags: []
---

pandoc "D:\Home\dbelveze\OneDrive - Université de Rennes 1\notes\Notes personnelles\XXXXXXXXXX.md" --bibliography=mylibrary.bib --csl=.\csl\nature.csl --pdf-engine=xelatex --citeproc -f markdown+smart -o mypdf\XXXXXXXXXXX.pdf

Convertir un document markdown en html en utilisant une feuille de style 

pandoc  -s document.md -c feuille.css -o document.html

-s s'impose quand il faut obtenir un fichier avec la compilation de plusieurs fichiers (ici une feuille de style et un texte en markdown)

-s est l'équivalent de --standalone

Pour que le bloc [[YAML]] soit pris en compte dans une conversion vers le HTML, il faut recourir au -s dans la ligne de commande. 

-c est suivi par le nom de fichier de la [[feuille de style]]

autres arguments : 

-f et -t désignent les formats d'entrée et de sortie. 

Obtenir un fichier en markdown depuis une page web en ligne : 

`pandoc -f html -t markdown https://ateliers-du-midi.univ-rennes1.fr/les-ateliers-de-la-bu -o pageweb.md`






# bibliographie

