# Introduction
Probablement le langage le plus simple de tous, ce n'est pas un langage de programmation à proprement parler, mais un langage de **balisage**.
Il sert à définir la **structure** de votre page web.

>[!info] Je suis pas dév front-end.
>Ainsi, je ne peux pas garantir que les exemples que je montre ici sont réalisés en se basant sur de bonnes pratiques.
>Je ne fais que montrer des exemples afin d'expliquer un principe.
# Les balises
Déjà parce que ce qui est utilisé lorsque l'on fait du [[HTML (Glossaire)|HTML]], ce sont des balises. 🤓
Mais surtout parce que HTML va servir à dire "là y a un article", "là y a le titre de cet article", etc...
## Qu'est-ce qu'une balise ?
C'est simple, c'est un truc qui est entouré de `<>` : `<img>`, `<br>` `<h3>`, etc...
Certaines balises **entourent** du contenu, comme pour `<p>`, dans ce cas, il existe également des balises **fermantes**, avec un `/` devant le nom de la balise : `</p>`, exemple concret :

```html
<p>Le HTML c'est cool !</p>
```

Ici, nous avons un paragraphe `<p>`. Le contenu de ce paragraphe est **entouré** de ces balises, une ouvrante (`<p>`) et une fermante (`</p>`).

Certaines balises n'ont pas de balises fermantes, c'est le cas de `<img>` et `<br>` par exemple.

Il existe une multitude de balises, toutes avec une utilité bien définie. L'usage des bonnes balises [[HTML (Glossaire)|HTML]] est préférable pour le SEO.
Par "bonne", j'entends utiliser la balise qui fait le plus sens sémantiquement, par exemple pour le titre principal d'une page, utiliser `<h1>` plutôt que `<div id='mon-super-titre'>`.
# Les attributs
Les balises [[HTML (Glossaire)|HTML]] peuvent contenir des **attributs**, les plus courants étant `id` et `class`.
Les attributs sont à définir dans la balise **ouvrante**, par exemple :

```html
<h1 id="titre-principal" class="titre">Ceci est un titre</h1>
```

Il y a aussi les `href` des `<a>` :

```html
<a href="https://www.youtube.com/watch?v=dQw4w9WgXcQ">Ceci n'est pas un rickroll</a>
```

Et bien d'autres !
### Différence entre id et class
Ces deux attributs sont extrêmement importants en [[HTML (Glossaire)|HTML]] et [[CSS (Glossaire)|CSS]].

La plupart des gens vont résumer ça à "id, c'est unique, et class, c'est plusieurs".
Techniquement, c'est vrai, cependant, ça manque cruellement de détails et de nuances.
#### Un ID
Un ID, c'est un identifiant, et c'est fait pour être unique, ce n'est pas une recommandation, ça **DOIT** être unique sur une page.

L'ID est là pour... Identifier (lol), un élément précis de votre page. Par exemple le titre principal.

```html
<h1 id="titre-principal">Ceci est un titre</h1>
```
#### Une classe
Une classe, c'est un **groupe** d'éléments qui **partagent** des propriétés communes.
Là, vous pouvez avoir autant d'éléments que vous voulez dans votre page qui partagent une même classe, et il est même possible de combiner des classes.

```html
<h1 class="titre">Ceci est un titre</h1>
<h2 class="titre">Ceci est un sous-titre</h2>
<h3 class="titre sous-sous-titre">Ceci est un sous-sous-titre</h3>
...
```
# Structure
Un bon [[HTML (Glossaire)|HTML]] est un HTML bien structuré, et pour ça, il faut voir la structure de base d'une page web :

```html
<!DOCTYPE html>
<html lang="fr">
	<head>
		<!-- Ici nous avons principalement les métadonnées de la page -->
		<meta charset="utf-8">
	</head>
	<body>
		<!-- Ici nous avons le contenu de la page -->
	</body>
</html>
```

C'est la structure de base d'une page en HTML.
D'abord le `<!DOCTYPE html>`, qui sert à indiquer au navigateur comment il est censé rendre la page, c'est nécessaire pour s'assurer que le navigateur interprète la page correctement.
Ensuite le `<html lang='fr'>`, qui contient toute votre page, et indique via un attribut, la langue du contenu de la page.
Nous avons ensuite le `<head>`, qui est là pour contenir les diverses métadonnées de votre page, par exemple :
- Son titre
- Son icône (favicon)
- Les feuilles de style ([[CSS (Glossaire)|CSS]])
- Diverses autres choses...
Ici, même si ça sort un peu du cadre de la structure en elle-même, j'ai rajouté `<meta charset="utf-8">`, qui devrait normalement toujours être là, afin de s'assurer que les accents par exemple, soient affichés correctement.
Et enfin le `<body>`, qui représente le contenu de la page en lui-même, les paragraphes, les titres de sections, tout ça, ça va là-dedans.
# En résumé
Le [[HTML (Glossaire)|HTML]], c'est le **squelette** d'une page web.