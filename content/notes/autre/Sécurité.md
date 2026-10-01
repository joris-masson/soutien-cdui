# Introduction
Le serveur web a aussi un rôle important à jouer dans la sécurité de votre site.

Une bonne règle à avoir, c'est qu'il ne faut **JAMAIS** faire confiance aux données venant de l'utilisateur 
# Exemple
Prenons l'exemple d'un formulaire. Votre utilisateur va rentrer des informations dedans, sous forme de texte par exemple.
Ce ne sera peut-être pas votre rôle, mais il est important de savoir que vous ne devez, sous aucun prétexte, faire confiance aux données transmises par l'utilisateur.
## Côté front-end
Là, c'est votre boulot, lorsque vous réalisez un formulaire, il y a quelques attributs HTML à utiliser au niveau des champs du formulaire pour définir des limites à l'utilisateur.
## Côté back-end
Les limites imposées à l'utilisateur par le front-end restent relativement limitées malheureusement. Un utilisateur mal intentionné peut lui-même éditer le HTML pour modifier les champs du formulaire à volonté. 
C'est pour ça que, au niveau du serveur par le biais de PHP, nous sommes **OBLIGÉS** de revérifier la conformité des données derrière.

>[!info]- Pour aller un peu plus loin.
>Bien sûr, une donnée valide (du texte dans un champ de texte par exemple), peut toujours être dangereuse.
>Pour cela, les requêtes faites via SQL sont **préparées**, c'est à dire que le développeur note à l'avance un modèle de requête SQL, avec des paramètres à la place des données réelles. Comme un texte à trou un peu : "Voici \_\_\_\_, né le \_\_\_\_ et il se décrit comme "\_\_\_\_"".
>Ensuite lors de la réelle exécution de la requête, le serveur est prêt à recevoir les données, et on lui donne : "Voici lulu, né le 01/10/1999 et il se décrit comme "J'aime les chats !"".
>De cette manière, les données envoyées par l'utilisateur ne sont **jamais** traitées autrement que comme des données.
>C'est une protection contre les **injections SQL**.
>
>Il est également nécessaire d'échapper les données utilisateur.
>Exemple simple, une description de profil : imaginez, `lulu` a comme description de profil ceci : `<h1>J'aime les chats !</h1>`. Que pensez-vous qu'il va se passer ?
>Eh bien c'est simple, dans le cas où la description n'est pas échappée, un réel `<h1>` va se glisser dans le HTML de votre page, et ce, peu importe qui consulte votre page, du moment qu'il est sur la page de profil de `lulu` qui affiche sa description.
>En revanche, dans le cas où le contenu serait échappé, alors sa description ne sera que "\<h1>J'aime les chats !\</h1>", sous forme de texte comme montré ici.
>L'échappement doit se faire à l'affichage des données, pas au stockage.
>C'est une protection contre les **failles XSS**.
>
>>[!info]- Anecdote amusante
>>Je dois aussi échapper le HTML dans ces notes comme ceci :
>>```md
>>\<h1>J'aime les chats\</h1>
>>```
>>(Notez les `\` avant les balises ouvrante et fermante.)
>>Sinon il se passe ça :
>><h1>J'aime les chats</h1>
>>Le HTML est **interprété** par Obsidian.
>
>Le cas d'un simple `<h1>` n'est clairement pas très grave, mais imaginez si c'était du script, car on pourrait rajouter des balises `<script>`, et donc le code du script serait exécuté sur tous les navigateurs affichant le profil de `lulu`.
## Conséquences d'une mauvaise sécurité
Dans le meilleur des cas, ce sera juste un petit malin qui va jouer sans trop faire de mal, mais dans d'autres cas :
- Suppression des bases de données
- Altération de votre site web
- Vol des données utilisateur
- Etc...
En gros, ne jouez jamais avec la sécurité.

# Exemple concret
J'adore le sortir celui-ci.
Nous étions en cours de développement web, à voir PHP et les requêtes aux bases de données.
Le professeur nous a donné un code via son support de cours, et ce code était **dangereux**. La requête SQL qui allait être envoyée à la base de données était littéralement dans le champ d'un formulaire, ça donnait, en gros, ceci :

```html
<form method="post" action="/confirmer"> 
	<p>Confirmer l'enregistrement ?</p> 
	<input type="hidden" name="requete" value="INSERT INTO Utilisateur (nom, email) VALUES ('lulu', 'lulu@example.com');">
	<button type="submit">Confirmer</button>
</form>
```

Un petit malin peut (et va, à ce niveau c'est vraiment demander à se faire pirater), modifier la requête SQL avant de l'envoyer au serveur, et là, c'est open bar vu comme ça.
Notre professeur nous avait dit de faire ça pour faire une sorte de confirmation après un formulaire.

Et il faut savoir que notre prof avait mis en ligne une version de test qui était terminée.
Naïvement je me suis dit que c'était pas possible et que ce serait corrigé dans un prochain TP, et donc que sa version finale mise en ligne devait forcément être sécurisée.

>[!warning] C'est illégal de faire ça si vous n'avez pas les droits. 🤓

Donc j'ai testé de changer la requête SQL par :

```sql
DROP TABLE Utilisateur;
```

Ce que fait cette requête est simple : elle supprime la table `Utilisateur`, qui contient TOUTES les données des utilisateurs.
Et le site était devenu inutilisable pour tout le monde, j'étais fier, mais en même temps pas trop. 🤣