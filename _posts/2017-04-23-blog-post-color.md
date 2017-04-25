---
title: 'Pourquoi abolir la subjectivité de la couleur dans notre étude ?'
date: 2017-04-24
permalink: /posts/2017/04/color/
tags:
  - Subjectivité
  - Couleur
  - huître perlière
---

Brake *et al.,* (2004) considèrent la pigmentation des huîtres *Crassostrea gigas* comme un trait continu. 
La segmentation du caractère pigmentaire en valeurs équivalentes serait pourtant pertinent pour les études portant sur des comparaisons chromatiques. 
Néanmoins, l'attribution et la qualification des couleurs restent subjectif, voir unique pour un individu donné ou même pour une culture par rapport à une autre (Kuriki *et al.,* 2017). 
Comparer des teintes, et les variations de ces teintes sur une simple intuition est impertinent. De plus, il existe un besoin de confirmer ou non les phénotypes. 
C'est pourquoi un phénotypage des coquilles par analyses photographiques sera réalisé. 
Les deux valves de chaque huître seront photographiées de façon standard grâce au Sysnext Packshot Creator 3D® présent au Centre Ifremer du Pacifique. 
Pour photographier la face interne des huîtres perlières vivantes (e.g. expérience Yo-yo), un prototype est en cours de réalisation pour obtenir un "échantillon-image" aléatoire de la zone colorée en question.

<br/><img src='/images/machine.png'>

La zone correspondant à l'expression de la couleur chez l'huître sera découpée à l'aide de logiciels comme Gimp® ou Paint. L'image sera ensuite intégrée dans le logiciel `R` à l'aide des packages `Imager`, `jpeg` et `png`. Chaque pixel est composé d'une couleur, elle-même composée d'un triplet de couleurs primaires (R - Rouge, V - Vert et B - Bleu ; RGB en anglais), et "décrite" par un code de valeurs chiffrées et lettrées hexadécimales. Une fonction créée sous R permettra d'extraire les valeurs des chenaux R, G et B. Chaque chenal d'une couleur possède une valeur allant de 0 à 255, 0 se rapprochant du noir, et 255 du blanc. 
Ces chenaux seront donc tous divisés par 255 afin d'obtenir des valeurs comprises entre 0 et 1. 
Il sera alors possible d'attribuer des valeurs aux couleurs, et donc de pouvoir les hiérarchiser, dans l'ordre conventionnel du système RGB. 
Néanmoins, ce système ne peut être qu'utile pour comparer des teintes, et non leurs nuances. 
C'est pourquoi, le code du système RGB sera converti en système HSV 
(H : Hue, teinte en anglais, S : Saturation et V : Value, correspondant ici à la "brillance" en français). 
Le triplet de code RGB sera réduit à une seule valeur en degré correspondant à la position de la teinte sur le cercle des couleurs de Goethe (issue de son traité des couleurs de 1810). 
Ce cercle sera positionné à la base d'un cône. La valeur de teinte (H) est répartie sur la circonférence de la base du cône. La saturation (S) correspond à la pureté de la couleur. 
Si celle-ci se grise, s'approche du blanc, on parle de dégradation de sa pureté. Dans ce cas, la valeur de S tendra vers 0. 
Le vecteur de la saturation part d'une valeur de teinte et se rapproche vers le centre du disque du cône. 
La brillance (V) d'une couleur est un vecteur qui part du centre du disque vers la pointe du cône. 
Plus une couleur sera sombre, plus elle tendra vers le noir, et donc vers 0. 
Grâce à ce système, les différentes teintes induites par la génétique pourront être comparées grâce au système RGB, et les variations chromatiques induites par l'épigénétique (e.g. brillance (V) et/ou pureté (S)) seront comparées par le système HSV.

<br/><img src='/images/syst.png'>

Bibliographie:      
 - Brake, John, Ford Evans, and Chris Langdon. 2004. “Evidence for Genetic Control of Pigmentation of Shell and Mantle Edge in Selected Families of Pacific Oysters, Crassostrea Gigas.” Aquaculture 229 (1–4): 89–98. doi:10.1016/S0044-8486(03)00325-9.           
 - Kuriki, Ichiro, Ryan Lange, Angela M Brown, and Delwin T Lindsey. 2017. “The Modern Japanese Color Lexicon” 17: 1–18. doi:10.1167/17.3.1.doi.          



------