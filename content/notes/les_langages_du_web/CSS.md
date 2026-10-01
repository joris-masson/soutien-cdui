# Introduction
Le CSS, **C**ascading **S**tyle **S**heets ou Feuilles de Style en Cascade en bon français, eh ben si le HTML c'est le squelette, le CSS c'est la peau d'une page web.
Le CSS est là pour styliser (non non vraiment, j'vous jure !) votre page, dire que tel truc est de telle couleur par exemple.

>[!info] Je suis pas dév front-end.
>Ainsi, je ne peux pas garantir que les exemples que je montre ici sont réalisés en se basant sur de bonnes pratiques.
>Je ne fais que montrer des exemples afin d'expliquer un principe.
# Les sélecteurs CSS
Lorsque l'on travaille avec du CSS, on utilise des sélecteurs pour... sélectionner les éléments de votre page.
Reprenons l'exemple du titre dans la section [[notes/les_langages_du_web/HTML#Les attributs|Les attributs]] de la note sur le [[notes/les_langages_du_web/HTML]]:

```html
<h1 id="titre-principal" class="titre">Ceci est un titre</h1>
```

Ici, trois choses peuvent servir à identifier et sélectionner ce `<h1>` :
- La balise `<h1>` en elle-même
- Son ID `titre-principal`
- Sa classe `titre`

Pour sélectionner cela, il existe différentes façon, selon ce que vous voulez sélectionner, avec les [sélecteurs CSS](https://developer.mozilla.org/fr/docs/Web/CSS/Guides/Selectors).

N'oubliez pas les [[notes/les_langages_du_web/HTML#Différence entre id et class|différences entre un ID et une classe]].
# Propriétés CSS
Le but du CSS, c'est principalement de changer le style de vos éléments HTML, de votre page. Pour cela, après avoir sélectionné ce que vous voulez changer, il faut commencer à modifier les propriétés CSS, par exemple :

```css
.titre {
	color: green;
	font-size: 177013px;
}
```

Là, on change les propriétés `color` et `font-size`, la couleur du texte et la taille de la police. Il existe **PLEIN** de propriétés CSS, impossible de tous les lister ici, mais c'est amusant de les tester !
# En résumé
CSS est là pour donner une bonne gueule à votre page web.