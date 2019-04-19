# graphxconv

Graphx Converter v0.5
Est un outil pour convertir des images BMP d'une taille de 256 x 192 pixels vers une palette fixe de 16 couleurs, comme le mode écran 2 du MSX, à l'aide de  l'algorithme de conversion CIEDE2000.

L'outil converti l'image source et sauvegarde la nouvelle image au format MSX pour le Mode 2. La conversion peut prendre quelques dizaines de secondes, suivant la puissance de votre ordinateur.

graphxconv : se lance en ligne de commande. Une interface graphique est alors disponible permettant de visualiser la conversion, puis de comparer cette conversion avec de nouveaux paramètres de conversion ou de nouvelles palettes de couleurs.

Plusieurs palettes de couleurs sont disponibles.
- 2 versions de la palette MSX de base
- 1 version tronquée de la palette MSX permettant une conversion en Noir et Blanc.
- Une palette simulant l'affichage sur un C64
- Une palette simulant l'affichage sur un Spectrum
- Une palette simulant l'affichage sur une Game Boy
- Une palette deux couleurs simulant l'affichage en noir et blanc.

Bien que des palettes de micro-ordinateurs autres que le MSX soient proposées, l'exportation de l'image convertie ne se fait pour l'instant que dans le format binaire pour MSX (Chargement avec BLOAD). D'autre modèles de sauvegarde pourront être ajoutés plus tard.

 La ligne de commande pour lancer une conversion est la suivante :
graphxconv <Input file> <output file> [-i<n> -p<n> -t<n> -d<n> -c -h]

Les deux premiers paramètres sont obligatoires.
<Input file> : correspond au chemin et au nom du fichier BMP à convertir
<Output file> : Correspond au chemin et au nom du fichier converti au format MSX

Les autres paramètres sont facultatifs. Si ils ne sont pas précisés, les paramètres par défaut sont utilisés.
-i<n> : si n=0, cela indique que vous ne désirez pas utiliser l'interface graphique. Une fois la conversion et l'image sauvegardée, l'interface graphique est close. Toute autre valeur, active l'interface graphique. Par défaut la valeur est 1 (Ex : -i0)

-p<n> : n, indique la palette à utiliser pour la conversion. 
	Par défaut la palette 0 est utilisée. (Ex: -p1)
	n, ne peut pas être supérieur au nombre de palettes inclues dans le programme.

-t<n> : n, indique la tolérance sur les couleurs, lors du processus de conversion. 
	Par défaut la tolérance est réglée sur 100. 
	La valeur de tolérance doit être comprise entre 0 et 100. (Ex: -t80)

-d<n> : n, indique le niveau de détails qui sera utilisé lors de la conversion. 
	Par défaut le niveau de détails est réglé sur 32. 
	Le niveau de détails doit être compris entre 0 et 255. (Ex: d100)

-c : Affiche les informations de copyright.
-h : affiche l'aide.

La liste des palettes inclues dans le logiciel.
0 : MSX Palette 0
1 : MSX Palette 1
2 : C64 Palette
3 : SPECTRUM Palette
4 : GAME BOY Palette
5 : B & W Palette
6 : MSX SC2 B & W (Compatible MSX1, Screen 2)

L'interface graphique
Une fois que 'graphxconv' est lancé une fenêtre de 808 x 616 Pixels est ouverte.

La première image affichée en haut à gauche est l'image originale.
Une fois la conversion réalisée, à sa droite sera affiché l'image convertie avec la palette choisie.

Si vous n'êtes pas satisfait du résultat, vous pouvez tenter une nouvelle conversion en changeant des paramètres, sans avoir à relancer le programme.
Utilisez les touches suivante :

Touche '1' : Décrémente le paramètre de tolérance couleur de 20 unités
Touche '2' : Incrémente le paramètre de tolérance couleur de 20 unités 
Touche '8' : Décrémente le paramètre de Niveau de détails de 20 unités
Touche '9' : Incrémente le paramètre de Niveau de détails de 20 unités
Touche 'P' : Utilise la palette suivante (0 -> 6 -> 0 ->)
Touche 'S' : Insert un nouveau Slot d'image
Touche 'ESC' : Quitte le programme

Chaque appuis sur une touche de contrôle, (sauf ESC et S) relance une nouvelle conversion de l'image originale, affiche le résultat, et sauvegarde le résultat sous le nom que vous avez indiqué.
Chaque nouvelle conversion s'affiche au dessus de la précédente.
Si vous désirez comparer plusieurs versions de l'image convertie, insérez un nouveaux Slot image en appuyant sur la touche 'S'. Une nouvelle portion de la fenêtre se dégagera, et la prochaine conversion s'affichera dans ce nouveau Slot. Vous pouvez ouvrir au total 8 slots supplémentaires, et ainsi comparer 8 versions de l'image convertie.




Graphx Converter  0.5  April 2019 
Original conversion routine by Leandro Correia
 This tool was coded in C, with SDL2 Graphic Library
 by Eric Boez 2019 - BZ Prod Game Studio
This tool is provided as is, with no guaranty
 Under the Creative Commons CC BY_SA 4.0 license
