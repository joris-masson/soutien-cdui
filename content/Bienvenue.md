Ceci est un coffre **Obsidian**, c'est notamment utilisé pour prendre des notes et les organiser, à la manière de **Notion**, mais sans dépendance à un service externe, car tout est stocké sur votre machine, et rien n'en sort !
# Sommaire
- [[Les langages du web]]
	- [[HTML]]
	- [[CSS]]
	- [[JavaScript]]
	- [[notes/les_langages_du_web/PHP|PHP]]
	- [[notes/les_langages_du_web/SQL|SQL]]
- [[Les serveurs]]
	- [[Serveur physique]]
	- [[Serveur web]]
	- [[Serveur de base de données]]
	- [[Serveur FTP]]
- [[Les outils]]
	- [[Frameworks]]
	- [[FTP]]
	- [[CMS]]
	- [[DevTools]]
	- [[W3C|Validation W3C]]
- Non catégorisé
	- [[Sécurité]]
	- [[Récapitulatif]]
- [[Glossaire.base|Glossaire]] (WIP)
# Quelques statistiques
```dataviewjs
const pages = dv.pages('""').where(p => p.file.ext === "md");
const lignes = [];
let totalMots = 0;
let totalCar = 0;

for (const p of pages) {
  const contenu = await dv.io.load(p.file.path);
  const car = contenu.length;
  const mots = (contenu.match(/\S+/g) || []).length;
  totalMots += mots;
  totalCar += car;
  lignes.push([p.file.link, mots, car]);
}

lignes.sort((a, b) => b[1] - a[1]);

dv.paragraph(
  `**Total : ${lignes.length} notes, ` +
  `${totalMots.toLocaleString("fr-FR")} mots, ` +
  `${totalCar.toLocaleString("fr-FR")} caractères**`
);

dv.table(["Note", "Mots", "Caractères"], lignes);
```
# Notice sur l'utilisation de l'IA
Les IA génératives (Claude, ChatGPT) ont été utilisées à des fins de relecture de l'ensemble de ce support.