# Introduction
Nous avons un peu parlé d'FTP dans la note concernant le [[Serveur FTP|serveur FTP]], logique.
Maintenant il vous faut un outil pour utiliser ce serveur et vous y connecter, il y en a plusieurs. Voici les deux principaux :
- [FileZilla](https://filezilla-project.org/)
- [WinSCP](https://winscp.net/eng/download.php)

Notez cependant que FileZilla a l'air d'être plutôt mal vu aujourd'hui, bien que fonctionnel, préférez WinSCP si vous devez choisir entre les deux.
Personnellement je suis avec WinSCP, donc je ne montrerais que ce logiciel, mais sachez que le fonctionnement et l'interface restent très similaires dans tous les cas.
# Interface
![[win_scp_base.png]]

Généralement, vous devriez avec deux sections sur votre écran, une correspondant à votre ordinateur, et l'autre au serveur.
Ici, à gauche vous avez le contenu de mon bureau, et à droite le contenu du dossier racine du serveur d'Amalia Graphiste (y a rien de sensible, c'est juste les dossiers de base d'un Linux).

Vous pouvez tout simplement cliquer sur le contenu à gauche que vous voulez mettre sur le serveur, et le déposer à droite sur le serveur. C'est très simple.
# Ajout d'un serveur / site
![[ajout_site.png]]

Vous aurez cette interface, qui peut être assez déstabilisante les premières fois. Comme abordé dans la partie [[Serveur FTP#Utilisation|Utilisation]] de la note sur le [[Serveur FTP|serveur FTP]], plusieurs informations sont demandées :
- Le protocole
- Le nom d'hôte
- Le numéro de port
- Le nom d'utilisateur
- Le mot de passe
Ces informations vous sont normalement transmises par votre hébergeur, je ne rentrerais donc pas dans les détails.
## Exemple d'un site
Voici la fenêtre de connexion du site d'Amalia Graphiste
![[exemple_site.png]]

À titre personnel, j'utilise le protocole SCP, je trouve personnellement ça plus simple à mettre en place, mais ça peu importe.
Le nom d'hôte est une adresse IP, celle du serveur.
Le numéro de port est 22, car le protocole SCP se base sur le protocole SSH (comme SFTP), qui utilise le port 22.
Le nom d'utilisateur est un nom d'utilisateur tout à fait classique que je masque ici pour des raisons de sécurité.
Et il n'y a pas de mot de passe car je me sers d'une clé pour me connecter (j'ai un guide entier sur SSH si ça intéresse quelqu'un 🤓).