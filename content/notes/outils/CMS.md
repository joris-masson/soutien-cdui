# Introduction
BON, il est temps de passer au gros du sujet : les CMS.
Dans un souci de grosse flemme intersidérale, on ne va aborder en détail que WordPress, qui est, de toute façon, le [^1]CMS par défaut de 99% du web moderne. Et de toute façon c'est également celui que vous voyez. Mais sachez que ses principes s'appliquent évidemment à d'autres.

>[!info] Je n'utilise personnellement pas WordPress
>Mes seules expériences avec sont une création de forum tout con en 4ème et la gestion du WordPress d'Amalia Graphiste pendant un temps.
>Donc le contenu ne pourra malheureusement pas être aussi exhaustif que sur les autres notes.
# Qu'est-ce qu'un CMS
CMS, pour **C**ontent **M**anagement **S**ystem, c'est un logiciel plutôt sympathique qui permet de créer, modifier et publier du contenu d'un site web. Et le plus important, **sans code** (ou très peu), ce qui a ses avantages, mais aussi ses inconvénients, vous verrez.

En gros, vous avez tout simplement une interface graphique, dans laquelle vous pouvez naviguer, et vous pouvez absolument tout gérer depuis cette interface. Vous n'avez à toucher à aucun code, le CMS s'occupe lui-même de toute la partie technique
# Notions à avoir
## Thèmes et templates
Un thème est un ensemble de fichiers qui vient régler comment s'affiche votre site web, son apparence ainsi que sa mise en page.

Il y a aussi les templates, qui font partie intégrante de ces thèmes.
Ils permettent de définir l'apparence et la mise en page d'un élément en particulier, par exemple pour un Hero ou un CTA.
### Template / Thèmes enfant
Vous pouvez utiliser des templates pour vos thèmes, ce sont des thèmes enfant.
Un thème peut avoir un enfant oui (non, ça marche pas comme pour nous, désolé... Ou pas ?).
Un thème enfant d'un thème ne sera constitué que des changements par rapport à son thème parent.
Fonctionner avec des thèmes enfants, ou templates, peut vous permettre de mieux organiser votre travail et d'éviter de trop vous disperser avec les demandes d'un client.
# Inconvénients
Bien que très pratique, oui, un CMS a ses inconvénients.
## Sécurité
Il faut savoir que WordPress étant extrêmement répandu, c'est évidemment un festin pour les hackers.
Voici quelques stats avancées par un gars de Reddit, de [r/selfhosted](https://www.reddit.com/r/selfhosted) :

![[stats_wp.png|700]][^2]

Ces stats montrent 30 jours de requêtes sur le serveur de ce gars, et ce que ces requêtes cherchent à atteindre.
Ces requêtes sont automatisées par de mauvaises personnes généralement, et **chaque site internet y est exposé**, à moins de prendre des mesures contre cela.

Tout en haut de la liste, avec 874 517 requêtes, nous avons du scan générique de PHP, comme beaucoup de sites utilisent PHP, ce n'est pas très étonnant.
Et ensuite, avec 196 003 requêtes, nous avons WordPress, avec des points d'accès bien connus comme `/wp-admin` par exemple.

Je le répète, mais tous les sites sont exposés à ces scans automatisés, ce n'est pas une blague, en hébergeant le WordPress d'Amalia Graphiste, j'ai pu personnellement voir ces scans.
### Se protéger
Je ne vais pas détailler comment se protéger, car sinon on en a pour 2 heures de plus.
Mais globalement, les plus gros conseils que je peux vous donner sont :
- N'ayez **pas** `admin` ou dérivé en tant que nom d'utilisateur.
- Ayez un mot de passe fort, difficilement devinable (et activez la double authentification).
- Changez l'url de connexion `/wp-login`, ça peut se faire via un plugin (ça n'enlève pas le risque, mais ça réduit le bruit quand-même).

Également, mettez à jour régulièrement, le fait que WordPress soit autant répandu est un gros avantage également, car les vulnérabilités sont repérées assez rapidement.
À savoir que les mises à jour de sécurité importantes sont installées automatiquement pour WordPress en lui-même. En revanche, ce n'est pas vrai pour les plugins, attention à cela donc.
## Personnalisation
Les CMS étant du no-code, si vous n'êtes pas dév, vous êtes complètement dépendant des thèmes et plugins des autres.
Ce qui veut dire que le jour où vous voulez quelque chose de très très précis et qui n'existe pas, vous allez devoir le faire vous-même. Ce qui implique des connaissances en développement.

>[!info] Point sur l'intelligence artificielle (LLM).
>Aujourd'hui certains pourraient vous dire "Oui mais aujourd'hui avec l'IA on peut tout faire avec WordPress, même sans être dév, y a juste à demander à l'IA si ce qu'on veut n'existe pas".
>Alors oui, mais non, ou alors il faut quand même savoir ce que vous faites.
>
>Réfléchissez-y à deux fois avant de vous lancer avec de l'IA. Que ce soit pour du theming (il y a du PHP qui peut tourner avec le fichier `functions.php` notamment), ou les plugins.
>Comme vu dans la partie [[#Sécurité]], WordPress est constamment scanné pour des vulnérabilités par des personnes avec de très mauvaises intentions.
>Et pour développer avec de l'IA, il est nécessaire de savoir développer soi-même, certains ne seront pas d'accord avec ça, que ça fait élitiste, mais c'est la réalité.
>Si votre IA vous génère du mauvais code, et que vous ne savez pas ce que vous faites, vous n'aurez **AUCUN** moyen de savoir que c'est du mauvais code. Et ce mauvais code pourrait introduire une ou plusieurs vulnérabilités. Ce que vous voulez absolument éviter.
## Les mises à jour
Ce n'est pas tout le temps le cas, mais sachez que WordPress a un certain historique avec les mises à jour qui tournent mal et qui dérèglent certaines choses.

C'est bien d'avoir des mises à jour, mais n'hésitez pas à demander à votre hébergeur de faire des sauvegardes **avant toute mise à jour** au cas où ça tourne mal.
Et sachez que vous pouvez aussi, et il vaudrait mieux également, en faire de vous-même, c'est possible avec des plugins.

[^1]: Ce chiffre est tiré de mon cul et très exagéré, mais sachez que ça représente une énorme partie quand même, environ 40% selon https://w3techs.com/technologies/details/cm-wordpress, ce qui est GIGANTESQUE.

[^2]: https://www.reddit.com/r/selfhosted/comments/1v0mrjd
