# Introduction
PHP, qui veut dire **PHP**: **H**ypertext **P**reprocessor... oui, c'est récursif, cherchez pas. Est également un langage du web, un langage permettant de rendre une page web **dynamique**.

Un petit point sécurité est disponible [[Sécurité|ici]].
## Dynamique ?
Ouais ouais, avec HTML, CSS et JS, vous pouvez réaliser un site web **statique**. PHP lui par contre, peut vous aider à réaliser un site web **dynamique**.

Qu'est-ce que ça veut dire concrètement ? La différence se situe surtout au niveau du serveur.
Déjà il faut voir ce qu'est une page statique.
### Une page web statique
Si une page web est statique, ça veut tout simplement dire que, grosso merdo, tout est défini dedans, et n'est pas réellement amené à changer, la structure définie par le HTML est posée, stable.

Le serveur va servir votre page telle quelle, peut-être qu'elle sera modifiée par le JS, mais ça c'est après le chargement de votre page.
### Une page web dynamique
Eh bien c'est l'inverse, tout n'est pas défini de base. 
Une page web dynamique va être partiellement, ou même complètement générée par le serveur **avant** d'être servie.
### La différence donc ?
La grosse différence, elle est liée au moment et au lieu de l'exécution du code.
PHP s'exécute sur le serveur **AVANT** que la page soit servie au navigateur.
JS s'exécute dans le navigateur **APRÈS** que la page ait été servie par le serveur.
### Comment ça marche ?
Eh bien c'est une histoire relativement simple :
~~Papa~~ Le serveur web est parti acheter du lait, et laisse la charge de gérer la page web à PHP.

Oui, le serveur demande tout simplement à PHP d'exécuter le code, code qui génère la page, et il redonne la page au serveur ensuite. La page est ensuite envoyée à notre navigateur.
# En pratique
La théorie c'est cool, mais on blablate depuis tout à l'heure sans exemple concret en tête.
L'exemple typique d'utilisation de PHP c'est... Un compte utilisateur.

Imaginez, vous voulez afficher votre profil utilisateur (ou celui de quelqu'un d'autre, peu importe en réalité).
Le navigateur demande à voir la page de `lulu`.
La requête arrive au serveur et en voulant préparer la page, PHP va gentiment aller récupérer les informations de l'utilisateur `lulu`, image de profil, date de création, et possiblement d'autres trucs, et il va intégrer toutes ces données à la page web finale, en les plaçant à des endroits définis par avance.

Voici un exemple concret de comment peut "préparer la page" avec PHP.

```php
<section id="profil">
	<h2><?php echo recupere_nom_de_profil(); ?></h2>
	<img src="<?php echo recupere_image_de_profil(); ?>">
	...
```

(On suppose que les fonctions `recupere_nom_de_profil()` et `recupere_image_de_profil()` échappent correctement les données).

Et ensuite, la page sera envoyée à votre navigateur !
# En résumé
On parle de serveur... Bah moi j'vais parler de... Votre partenaire.
Vous êtes gentiment sur votre canapé à jouer aux Lego, et vous demandez à manger à votre partenaire.

Votre partenaire va recevoir votre demande, vous cuisiner votre plat parce que c'est un amour et vous le servir.
Et PHP c'est pareil, vous demandez une page, sur le serveur, va recevoir la demande et vous la préparer, pour ensuite la servir à votre navigateur.