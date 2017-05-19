# elephant
Affichage historique navigation personnalisé et basé sur un scoring de page intéressantes pour l'utilisateur.


Ce module permettra d'afficher une liste de pages qui sont sensés être plus intéerssantes que les autres pour l'utilisateur d'un site web.

Ca se présentera comme un mini historique de navigation.

Les liens affichés à l'intérieur seront les pages "produits" d'un site d'annonces immobilières.
L'ordre de classement des différentes pages enregistrées doit se faire par un petit algo, en js (pas de backend pour l'instant), qui prendra en compte certains paramètres mesurables tels que :
- le temps passé sur la page
- le fait de plus ou moins scroller dans la page
- le nombre de fois ou l'utilisateur à visité la page
- des éléments "déclencheurs" (du type ouvrir une liste d'information, ouvrir des photos, etc...)
- un possible bouton "favoris", pour que l'utilisateur puisse notifié son interet

liste non-exhaustive

Pourquoi elephant ? Parcequ'ils ont une bonne mémoire, surtout pour retrouver leur point d'eau ! :)

Bon allez, let's code !


# Installation
1 - Copier le dossier elephant dans votre répertoire javascript

2 - appeler les fichier JS et CSS correspondant dans vos balise head
~~~~
<link rel="stylesheet" href="/path/to/elephant.min.css">
<script type="text/javascript" src="/path/to/elephant.min.js"></script>
~~~~

3 - Positionner la div déclencheuse du comptage des stats dans les pages désirées (id='elephant')
~~~~
<div id="elephant" data-text="Le texte qui s'affichera dans le rendu visuel" data-image="/path/to/image.jpg"></div>
~~~~


4 - Positionner la div de rendu dans les pages désirées (id='elephanto')
~~~~
<div id="elephanto"></div>
~~~~

5 - Puis exécuter le plugin JS
~~~~
$(document).ready(function () {
  $.fn.elephant();
});
~~~~

# Options
Le plugin Elephant prends en compte certaines options de personnalisation.

Options par défaut :
~~~~
{
triggers: new Array(),
activeDuration: 30,
refreshRender: 1,
maxDisplayedResult: 5,
moreText: 'Vos pages favorites'
}
~~~~
triggers : définie les éléments qui incrémentent la stat 'trigger' (type selecteur JQuery (tag, id, class,...)).

activeDuration (secondes) : définit la durée à partir de laquelle l'utilisateur est considéré comme inactif sur une page. Pris en compte pour l'incrémentation de la stat 'time'.

refreshRender (secondes) : définit le temps de rafraichissmeent du rendu visuel.

maxDisplayedResult : définit le nombre maximal de positions à afficher dans le rendu visuel.

moreText: définit le texte à afficher en haut du rendu visuel pour switcher l'ouverture de la div.

