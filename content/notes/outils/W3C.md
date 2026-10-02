# Introduction
Le W3C (World Wide Web Consortium), c'est le truc qui dicte les standards du web, en très gros.
J'en parle pour une chose, c'est la validité au W3C de votre site web.

Le W3C dicte ses standards, et c'est généralement reconnu comme bonne pratique que d'avoir son site validé au W3C. Ce ne sont certes que des conventions, mais généralement, si vous avez une erreurs au W3C, il peut être utile de la résoudre, car une erreur, même si elle ne casse visiblement rien sur votre page, pourrait casser dans un futur plus ou moins proche, ou même maintenant, mais sur un autre navigateur.

Lorsque j'étais en cours, on nous forçait à être valide au W3C, sous peine de perdre obligatoirement des points, même si le site était parfait et répondait à toutes les consignes.
Dans le monde réel, ce n'est **PAS** une obligation, mais c'est fortement conseillé de faire de son mieux de ce côté.
# Comment vérifier ?
Il suffit d'aller sur [cette page](https://validator.w3.org/).
D'ici, vous avez 3 modes de validation :

| Mode de vérification | Description                                                                                                 |
| -------------------- | :---------------------------------------------------------------------------------------------------------- |
| URI                  | Vous devez fournir une adresse http/https **publiquement accessible** (donc pas de localhost ou 127.0.0.1). |
| File Upload          | Vous devez fournir le fichier HTML directement. Ou son rendu si c'est généré avec PHP.                      |
| Direct Input         | Vous devez copier et coller votre HTML dans le champ prévu à cet effet.                                     |
La première méthode ne marchera pas pour des sites non publiés.
Dans un contexte de développement donc, les deux dernières options seront sûrement celles qui vont vous intéresser. Sauf si votre version de développement est publiquement accessible, auquel cas, attention, car cela peut comporter des risques.