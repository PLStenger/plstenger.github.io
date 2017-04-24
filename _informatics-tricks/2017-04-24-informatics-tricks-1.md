---
title: 'Informaticks tricks 1'
date: 2017-04-24
permalink: /informatics-tricks/2017/04/informatics-tricks-1/
tags:
  - Informaticks tricks
  - Latex
  - Docx
---

Je propose ici un tuto avec un exemple très simple. Il faut au préalable télécharger LibreOffice (ou Apache OpenOffice) et l’exécutable Pandoc (Windows, MacOsx, Linux) sur le site de son créateur:  http://pandoc.org/installing.html 
Il faut bien sûr l'installer sur sa machine.

Voici le code de mon fichier test.tex:
 
```ruby
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
 
\documentclass{article}
 
% Gestion de la langue, des polices, ligatures, etc
\usepackage[utf8x]{inputenc}
\usepackage[english,francais]{babel}
\usepackage[babel]{microtype}
 
% Marges, interlignes, graphiques et colonnes multiples
\usepackage[top=2.5cm,bottom=2.5cm,left=2.5cm,right=3.5cm,twoside]{geometry}
\usepackage{setspace}`
\usepackage{multicol}
\setlength\columnsep{10pt}
\usepackage{graphicx}
\onehalfspacing % interligne 1.5
 
\begin{document}
 
Exemple minimal \LaTeX\ 
 
\section{Introduction}
 
\begin{itemize}
\item Un item
\item Un second item
\end{itemize}
 
\section{Test des images}
 
Une belle image 
 
\begin{center}
\includegraphics[scale=0.25]{DSC_0001.jpg} 
\end{center}

\end{document}
 
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%`
 ```

Je peux le compiler avec n'importe quel distributeur Tex:
 
![](http://image.noelshack.com/fichiers/2017/03/1484866746-1.png)
 
Je vais ensuite ouvrir mon invite de commande (cmd dans "recherche" sous Windows).
Il faut se placer dans son répertoire de travail. Vous allez avoir besoin pour cela d'écrire "cd" suivi de votre chemin d'accès de vos fichiers. cd est du code bash qui signifie "Change directory".
Ce qui donne dans l'invite de commande quelque chose comme:
 
C:\Users\plsenge cd C:\Users\plstenge\Documents\Test Pandoc

Taper sur Entrée, puis vous obtiendrez directement:
C:\Users\plstenge\Documents\Test Pandoc

À la suite de cette ligne, vous allez entrer une ligne de code pour appeler l’exécutable  Pandoc et lui demander de convertir votre fichier test.tex en fichier test.rtf. Voici la ligne de code: pandoc -s test.tex -o test.rtf, ce qui donnera dans l'invite de commande:
 
C:\Users\plstenge\Documents\Test Pandoc pandoc -s test.tex -o test.rtf
 
Appuyer sur Entrée et dans votre répertoire d'origine, de nouveaux fichiers sont apparus, dont le fameux test.rtf
 
Vous allez pouvoir l'ouvrir avec LibreOffice Writer:
 
![](http://image.noelshack.com/fichiers/2017/03/1484866746-2.png)
 
Pour ensuite pouvoir l'enregistrer en format Microsoft Word 2007-2013 XML (.docx) (aller dans "enregistrer sous) et paf ! Vous pourrez l'ouvrir avec OpenOffice ou Word.
 
![](http://image.noelshack.com/fichiers/2017/03/1484866746-3.png)

Et voilà, vous n'avez plus qu'à appliquer les polices et tailles de votre choix !


Il existe d'autres techniques, qui donnent de meilleurs résultats, notamment avec Tex4ht qui permet d'obtenir ce genre de résultat final avec Word:
 
![](http://image.noelshack.com/fichiers/2017/03/1484866696-4.png)

 Malheureusement il y encore quelques lignes de codes qui me bloquent, donc en attendant d'avoir le must, Pandoc est déjà très utile !

Enjoy !