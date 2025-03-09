# Omny Player

Cette extension Chrome modifie les en-têtes HTTP pour améliorer la compatibilité avec animeovf.fr.

## Installation

1. Ouvrez Chrome et accédez à `chrome://extensions/`
2. Activez le "Mode développeur" en haut à droite
3. Cliquez sur "Charger l'extension non empaquetée"
4. Sélectionnez le dossier contenant les fichiers de l'extension

## Fonctionnalités

### Modification des En-têtes
#### Règle Générale
- Supprime les en-têtes `origin`, `referer` et `sec-fetch-user`
- Configure les en-têtes `sec-fetch-*` pour une meilleure compatibilité
- Modifie les en-têtes CORS pour permettre l'accès aux ressources
- Exclut certains domaines spécifiques (youtube-nocookie, tiktok, etc.)

#### Règles Spécifiques
L'extension gère des règles spéciales pour les lecteurs vidéo suivants :
- uqload.to
- Serveurs CDN spécifiques (ahcdn.com, xhcdn.com, cdn13.com)
- sibnet.ru
- myvi.ru
- mail.ru
- vidmoly et ses domaines associés (vmrange.lat, vmrest.space, etc.)
- filemoon et domaines associés (filemoon.sx, defienietlynotme.com, etc.)

### Injection de Script
L'extension injecte automatiquement la propriété `window.OmniPlayer` avec la version actuelle sur animeovf.fr.

## Permissions

L'extension nécessite l'accès aux domaines suivants pour fonctionner correctement :
- animeovf.fr et ses sous-domaines
- Tous les domaines des lecteurs vidéo mentionnés ci-dessus

Ces permissions sont nécessaires pour que l'extension puisse modifier les en-têtes des requêtes vers ces domaines.

## Sécurité
- Toutes les règles sont définies de manière statique dans le fichier `rules.json`
- Les modifications d'en-têtes sont limitées aux domaines spécifiés
- L'extension utilise l'API declarativeNetRequest de Chrome pour des performances optimales
- L'injection de script est limitée au domaine animeovf.fr
