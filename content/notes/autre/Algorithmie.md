>[!info] Cette note est pour un niveau plus avancé.
# Introduction
Loin de moi l'idée de faire un cours d'algo ici, comme les 3/4 de ma promo en licence, j'ai genre eu 3 ou 4 dans ce cours. 😶
Je peux juste donner quelques conseils pour apprendre l'algorithmie, car c'est un point extrêmement bloquant pour beaucoup.
# L'apprentissage
L'apprentissage de l'algorithmie est assez particulière, mais retenez bien une chose : comme pour beaucoup d'autres domaines, on ne devient pas à l'aise avec en 2 jours seulement, vous n'allez pas devenir peintre en agitant un pinceau pendant 4 heures. En d'autres termes, c'est à force de forger que l'on devient forgeron.
# La pratique
C'est bateau dit comme ça, mais il faut pratiquer pour pouvoir devenir meilleur, vous devez très certainement en être plus que conscient.

Et le meilleur moyen de pratiquer, ce sont de petits projets à la con.
Vous choisissez une idée, qui vous plaît, ça c'est très important. Et ça peut être n'importe quoi, vraiment.
Par exemple, vous aimez les jeux-vidéos ? Pourquoi pas tenter de faire un petit jeu ? J'parle pas d'un Zelda, mais peut-être juste d'un Memory, ou un Pierre-Feuille-Ciseau, ou encore un Snake, des jeux simples.
Vous pouvez aussi aimer l'écriture, auquel cas vous pouvez vous lancer dans un petit programme qui vient remplacer tous les mots d'un texte par... euh... "caca" ? Ou encore quelque chose qui génère des mots complètement aléatoirement !
Si vous aimez la photo, peut-être qu'un programme qui modifie vos images, y rajoute des filtres, ou qui les tries peut être amusant à faire pour vous.

Les idées, y en a une infinité, mais il faut réussir à trouver l'idée qui *vous* fait vibrer, car la motivation n'en sera que plus grande.
# Le langage
On a parlé de [[notes/les_langages_du_web/PHP|PHP]] et de [[JavaScript]], qui sont deux langages de scripting complètement valides, vous pourrez réaliser à peu près n'importe quoi avec, mais sachez qu'il en existe d'autres, potentiellement plus accessibles, comme [Python](https://www.python.org/), qui a l'immense avantage d'avoir des bibliothèques de code pour tout et n'importe quoi, pour l'exemple des images plus haut, il existe [Pillow](https://pypi.org/project/pillow/), qui est très répandu pour travailler avec les images.

Dans tous les cas, sachez que le langage n'a que peu d'importance dans votre apprentissage, car peu importe celui que vous choisissez, la logique restera globalement la même.

Vous savez comment on nous apprends l'algorithmie à la fac ? Avec du texte, on ne travaille pas directement avec du code de tel ou tel langage, on travaille avec du texte. Et quand on nous évalue, les profs ne recherchent pas si ce qu'on a écrit **va** marcher, mais si ça a du sens, que c'est logique. C'est assez obscure dit comme ça, alors voici un exemple d'algorithme pour savoir si il y a un 'a' dans un mot :

```
variable mot1 -> "bonjour"
variable mot2 -> "au revoir"

fonction y_a_un_a(mot):
	pour tout élément lettre dans mot faire:
		si lettre est 'a':
			renvoyer VRAI
	renvoyer FAUX

affiche(y_a_un_a(mot1)) // affiche FAUX
affiche(y_a_un_a(mot2)) // affiche VRAI
```

Tout bêtement, et même si la structure est proche du Python, ça reste juste du français, et l'important, c'est que vous pouvez traduire ce code dans autant de langages que vous voulez, voici des exemples :

>[!example]- JavaScript
>```js
>let mot1 = "bonjour";
>let mot2 = "au revoir";
>
>function y_a_un_a(mot) {
>	for (const lettre of mot) {
>		if (lettre === 'a') {
>			return true;
>		}
>	}
>	return false;
>}
>
>console.log(y_a_un_a(mot1));
>console.log(y_a_un_a(mot2));
>```

>[!example]- PHP
>```php
>$mot1 = "bonjour";
>$mot2 = "au revoir";
>
>function y_a_un_a(string $mot): bool {
>	foreach(str_split($mot) as $lettre) {
>		if ($lettre == 'a') {
>			return True;
>		}
>	}
>	return False;
>}
>
>echo y_a_un_a($mot1);
>echo y_a_un_a($mot2);
>```

>[!example]- Python
>```python
>mot1 = "bonjour"
>mot2 = "au revoir"
>
>def y_a_un_a(mot: str) -> bool:
>	for lettre in mot:
>		if lettre == 'a':
>			return True
>	return False
>
>print(y_a_un_a(mot1))
>print(y_a_un_a(mot2))
>```

>[!example]- Java
>Cet exemple est volontairement simplifié, Java étant un langage de programmation orienté objet, il aurait également fallu définir la classe et tout le bordel... 🤣
>```java
>String mot1 = "bonjour";
>String mot2 = "au revoir";
>
>public static boolean y_a_un_a(String mot) {
>	for (char lettre : mot.toCharArray()) {
>		if (lettre == 'a') {
>			return true;
>		}
>	}
>	return false;
>}
>
>System.out.println(y_a_un_a(mot1));
>System.out.println(y_a_un_a(mot2));
>```

À savoir que certains de ces langages intègrent directement une fonction native pour vérifier si tel caractère est dans tel chaîne de caractère. Mais le but de cet exemple était de montrer qu'un algorithme peut être traduit dans tous les langages que vous voulez.