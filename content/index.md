Ceci est un coffre [**Obsidian**](https://obsidian.md/), c'est notamment utilisé pour prendre des notes et les organiser, à la manière de **Notion**, mais sans dépendance à un service externe, car tout est stocké sur votre machine, et rien n'en sort !

Une version web est disponible ici : https://joris-masson.github.io/soutien-cdui/
Une version à ouvrir avec Obsidian est disponible au téléchargement ici : https://github.com/joris-masson/soutien-cdui/releases
# Sommaire
- [[Les langages du web]]
	- [[notes/les_langages_du_web/HTML|HTML]]
	- [[notes/les_langages_du_web/CSS|CSS]]
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
	- [[Algorithmie]] (Avancé)
- [[Récapitulatif]]
- [[Glossaire.base|Glossaire]]
# Quelques statistiques
Normalement un tableau avec des statistiques est dans cette section. Si vous n'êtes pas dans Obsidian, cela ne s'affichera pas.
```dataviewjs
const MOTS_PAR_MIN = 230;

const formatDuree = (min) => {
  const h = Math.floor(min / 60);
  const m = Math.round(min % 60);
  return h > 0 ? `${h} h ${String(m).padStart(2, "0")} min` : `${m} min`;
};

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
  lignes.push([p.file.link, mots, car, formatDuree(mots / MOTS_PAR_MIN)]);
}

lignes.sort((a, b) => b[1] - a[1]);

const totalMin = totalMots / MOTS_PAR_MIN;
const jours = (totalMin / 60 / 24).toFixed(1);

dv.paragraph(
  `**Total : ${lignes.length} notes, ` +
  `${totalMots.toLocaleString("fr-FR")} mots, ` +
  `${totalCar.toLocaleString("fr-FR")} caractères**\n\n` +
  `**Temps de lecture estimé : ${formatDuree(totalMin)}** `
);

dv.table(["Note", "Mots", "Caractères", "Lecture"], lignes);
```
# Notice sur l'utilisation de l'IA
Les IA génératives (Claude, ChatGPT) ont été utilisées à des fins de relecture de l'ensemble de ce support.