# ELEPHANT

[EN]
This Jquery plugin allows to store, to sort by interest, and to display the navigation of a user on particular pages of a site. It's a kind of "auto smart selection" of favorite user's page on a site.
At begining, this plugin is developed to a real estate website, but it could be used on a lot of various case.

It allows to display a list of pages that represent the interest of the user of the site, to facilitate the search for products, and to easily find the products for which it has a real interest.

The order of classification of the various recorded pages takes into account certain measurable parameters such as:
- the time spent on the page
- the fact of more or less scroll in the page
- the number of times or the user has visited the page
- trigger elements (eg. opening a list of information, opening photos, clicking a button, etc.)
- a "favorites" button, that user can manually notify his interest

[FR]
Ce plugin Jquery permet de stocker, classer par intérêt, et restituer la navigation d'un internaute sur des pages données d'un site. C'est une sorte de 'sélection automatique et intelligente' des pages favorites d'un utilisateur sur un site.
A la base, ce plugin est développé pour un site d'agence immobilière, mais il peut etre utilisé dans de nombreux autres cas.

Il permet d'afficher une liste de pages sensés intéresser l'utilisateur du site, lui faciliter la recherche de produits, et retrouver facilement les produits pour lesquels il éprouve un réel intérêt.

L'ordre de classement des différentes pages enregistrées prends en compte certains paramètres mesurables tels que :
- le temps passé sur la page
- le fait de plus ou moins scroller dans la page
- le nombre de fois ou l'utilisateur à visité la page
- des éléments "déclencheurs" (ex: ouvrir une liste d'informations, ouvrir des photos, cliquer sur un bouton, etc...)
- un bouton "favoris", pour que l'utilisateur puisse notifié manuellement son intérêt



# Installation
1 - Copier le dossier elephant dans votre répertoire javascript

2 - appeler les fichier JS et CSS correspondant dans vos balise head
~~~~
<link rel="stylesheet" href="/path/to/elephant.min.css">
<script type="text/javascript" src="/path/to/elephant.min.js"></script>
~~~~

3 - Positionner la div déclencheuse du comptage des stats dans les pages désirées (id='elephant')
~~~~
<div id="elephant" data-text="Le texte qui s'affichera<br />dans le rendu visuel" data-image="/path/to/image.jpg"></div>
~~~~


4 - Positionner la div de rendu dans les pages désirées (id='elephanto')
~~~~
<div id="elephanto"></div>
~~~~

5 - Positionner la div dédiée aux favoris (id='elephant_favorite')
~~~~
<div id="elephant_favorite"></div>
~~~~


6 - Puis exécuter le plugin JS
~~~~
$(document).ready(function () {
  $.fn.elephant();
});
~~~~

# Options
Le plugin Elephant prends en compte certaines options personnalisable.

**Important :** pour l'instant, l'option 'path' doit être obligatoirement renseignée.

Options par défaut :
~~~~
{
triggers: new Array(),
activeDuration: 30,
refreshRender: 1,
maxDisplayedResult: 5,
title: 'My selection',
entryName: {
  'one': '',
  'several': ''
},
favoriteTrigger: '#elephant_favorite',
favoriteOffText: "Cette page m'intéresse",
favoriteOnText: "Cette page ne m'intéresse plus"
path: "",
theme: "default",
displayModeText:{
  'normal': 'View all',
  'see_other': 'Reduce view'
},
clear: "Clear",
clearText: "Would you really reset your selection ?",
pluginInformation: "Selection made based on your browsing on the site."
}
~~~~
triggers (tableau) : définie les éléments qui incrémentent la stat 'trigger' (type selecteur JQuery (tag, id, class,...)).

activeDuration (secondes) : définit la durée à partir de laquelle l'utilisateur est considéré comme inactif sur une page. Pris en compte pour l'incrémentation de la stat 'time'.

refreshRender (secondes) : définit le temps de rafraichissmeent du rendu visuel.

maxDisplayedResult (entier) : définit le nombre maximal de positions à afficher dans le rendu visuel.

title (chaîne) : définit le texte à afficher en haut du rendu visuel.

entryName (objet): défini le nom 'humain' des entrées de la sélection (ex: produit, bien immobilier, annonce, etc...)

favoriteTrigger (chaîne) : id de la div du bouton favoris.

favoriteOffText (chaîne) : texte pour ajouter une page dans les favoris.

favoriteOnText (chaîne) : texte pour enlever une page des favoris.

path (chaîne): chemin du dossier du plugin (nécéssaire pour la gestion des thèmes).

theme (chaîne): nom du dossier contenant le thème désiré

displayModeText (objet): texte à afficher à coté du bouton qui permet d'afficher toutes les entrées enregistrées

clear (chaîne):  texte à afficher à coté du bouton qui permet de vider la sélection

clearText (chaîne): texte de confirmation lors du vidage de la sélection

pluginInformation (chaîne): Phrase informative sur le fonctionnement du plugin. Dédié à l'utilisateur.


# Themes

Afin de personnaliser le plugin sur votre site, il est très facile de faire votre propre thème. Il vous suffit juste de copier le répertoire du thème par défaut,
de personnaliser les différents fichiers (css, images), puis de l'appeler dans les options du plugin grâce à la variable 'theme'


# Screenshot

**Thème par défaut :**
![theme par defaut](https://github.com/fyzalis/elephant/blob/master/demo/elephant-screenshot-default.png)


**Thème premiumimmoneuf :**
![theme premium](https://github.com/fyzalis/elephant/blob/master/demo/elephant-screenshot-premium.png)


# Auteur
*Plugin réalisé par [Julien Buabent](http://julienbuabent.fr), pour le groupe [immo9 - Immobilier neuf à Toulouse](http://toulouseimmo9.com)*
