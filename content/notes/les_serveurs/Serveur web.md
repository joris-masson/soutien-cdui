# Introduction
Celui que vous devriez forcément connaître. C'est lui qui vient servir votre site web.
# Utilité
Comme dit précédemment, il sert votre site web. C'est à ce serveur que vont s'adresser les utilisateurs pour y accéder. C'est un peu le cœur de toute notre opération.
# Communication
Un serveur web communique, ouais, il parle peut-être pas notre langue, mais il parle, et pour lui parler, il faut communiquer en HTTP ou en HTTPS avec lui, ce sont les fameux http:// et https:// au début de l'URL.
# HTTPS
Le HTTPS, c'est la version sécurisée du HTTP, ça veut dire que la communication entre vous et le serveur est sécurisée.

>[!danger] HTTPS ne veut pas dire que le site ne peut pas être malveillant !
>Ça veut juste dire que la **communication** est sécurisée.
>La communication peut être sécurisée avec un site malveillant.

HTTPS utilise un **certificat SSL/TLS** pour permettre de s'assurer que vous parlez avec le bon serveur, et **chiffrer** la connexion entre le navigateur et le serveur web.

Grâce à cela, personne ne pourra venir épier ce qui se dit entre vous et le serveur.
# Configuration
## Indexation
Le fameux `robots.txt`, c'est ce fichier qui va dicter si oui on non les robots (indexeur de google et autres, ou même LLM) peuvent lire le contenu de votre site web.

>[!warning] Ce fichier n'a pas à être suivi par les robots.
>C'est juste l'équivalent de dire "stp va pas là si tu t'appelles Bob".
> Bob pourrait juste :
>- Complètement ignorer la demande.
>- Dire qu'il s'appelle Jean-Claude.
>
>Les robots peuvent donc complètement ignorer ces indications.

C'est un simple fichier texte qui se présente comme ceci :

```txt
User-agent: *
Allow:
```

Ce `robots.txt` autorise explicitement tous les robots sur tout votre site.
L'autorisation d'accès est implicite sans cela.
Si vous avez un panel admin, ce qui est probable avec WordPress, vous pouvez explicitement l'interdire comme ceci :

```txt
User-agent: *
Disallow: /wp-admin/
Disallow: /wp-login.php
```

Vous pouvez également renseigner le sitemap de votre site dedans :

```txt
User-agent: *
Disallow: /wp-admin/
Disallow: /wp-login.php

Sitemap: https://example.com/sitemap.xml
```

À savoir que WordPress gère généralement ce fichier lui-même, mais c'est important de connaître son utilité.
## Se protéger des IA
Si vous êtes artiste, il y a de **TRÈS** fortes chances que vous vouliez éviter la venue d'IA sur votre site, pour venir en ingérer le contenu par exemple.

Il existe plusieurs méthodes, deux polies qui vont ensemble, et une autre un peu plus agressive.
### Demander poliment

>[!warning] Là, encore une fois, ce sont des demandes polies à leurs yeux, ils ne sont pas tenus de respecter ces demandes.

>[!example]- Un bon fichier `robots.txt` :
>```txt
>User-agent: GPTBot
>Disallow: /
>
>User-agent: ChatGPT-User
>Disallow: /
>
>User-agent: CCBot
>Disallow: /
>
>User-agent: anthropic-ai
>Disallow: /
>
>User-agent: ClaudeBot
>Disallow: /
>
>User-agent: Claude-Web
>Disallow: /
>
>User-agent: Google-Extended
>Disallow: /
>
>User-agent: PerplexityBot
>Disallow: /
>
>User-agent: Applebot-Extended
>Disallow: /
>
>User-agent: Bytespider
>Disallow: /
>
>User-agent: Amazonbot
>Disallow: /
>```

Et rajouter une balise `<meta>` :

```html
<meta name="robots" content="noai, noimageai">
```

### Altérer légèrement vos images
Comme les IA peuvent s'entraîner sur des images, vos images, il est possible "d'empoisonner" leur entraînement, ce serait un peu l'équivalent de dire à un enfant en bas-âge "oh le beau putois" tout en montrant ~~un électeur du RN~~ un chien.

Voici un logiciel qui fait cela : https://nightshade.cs.uchicago.edu/index.html. Il en existe grosso modo deux versions, celle-ci est la plus agressive, et peu affecter l'entraînement des IA.

Il altère très légèrement vos images sans pour autant trop en affecter la qualité et la lisibilité, du moins de loin, en regardant de près on y voit de légers artéfacts.

| Avant        | Après (paramètres de base) | Après (HIGH et Medium)         |
| ------------ | -------------------------- | ------------------------------ |
| ![[moi.jpg]] | ![[moi_moche.jpg]]         | ![[moi_encore_plus_moche.jpg]] |
