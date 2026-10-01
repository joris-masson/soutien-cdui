# Introduction
Le serveur FTP est ce qui vous permet de venir modifier les sources de votre site web situé sur [[Serveur web|le serveur web]].

FTP signifie **F**ile **T**ransfer **P**rotocol, ou en français : Protocole de Transfert de Fichiers.

Ça décrit bien l'utilisation, ça sert pour... Transférer des fichiers !
# SFTP
FTP en tant que tel n'est **pas** sécurisé, une personne mal intentionnée pourrait écouter et voir tous les transferts que vous faites avec votre serveur.
C'est pour ça qu'il existe le protocole SFTP, le S étant le S de **S**SH, qui est un protocole de communication sécurisé utilisant un autre serveur (le serveur SSH), que nous n'aborderons pas.
Il existe également FTPS, qui vient rajouter un chiffrement SSL/TLS pour sécuriser la connexion entre vous et le serveur, à la manière du serveur web avec [[Serveur web#HTTPS|HTTPS]].
# Utilisation
FTP, SFTP et FTPS s'utilisent globalement de la même manière, il vous faudra plusieurs informations :
- Un nom d'hôte
- Un nom d'utilisateur
- Un mot de passe
- (Un numéro de port)
Le nom d'hôte représente le serveur en lui-même, et comment il s'identifie, c'est son adresse (nom de domaine / IP).
Le nom d'utilisateur et le mot de passe, je pense que c'est assez explicite, mais oui, il est nécessaire de s'authentifier.
Le numéro de port est souvent optionnel dans le sens où ces protocoles ont tous un numéro de port par défaut, et qu'il est rarement changé. Dans la plupart des cas ce champ est prérempli par votre logiciel.

Toutes ces informations vous sont normalement transmises par votre hébergeur.