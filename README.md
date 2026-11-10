# GMAO Atelier — Proof of Concept

PWA statique pour GitHub Pages, compatible Safari iPhone et Chrome Android.

## Installation sur GitHub Pages

1. Créez un dépôt GitHub (par exemple `gmao-poc`).
2. Déposez à la racine les fichiers `index.html`, `app.js`, `manifest.webmanifest`, `icon.svg` et `sw.js`.
3. Dans **Settings → Pages**, choisissez **Deploy from a branch**, puis `main` et `/ (root)`.
4. Ouvrez l'URL GitHub Pages. Sur iPhone : Safari → Partager → Ajouter à l'écran d'accueil.

## Limites importantes

- Les données sont conservées dans le `localStorage` de **chaque appareil**, sans synchronisation ni compte utilisateur. Ne pas utiliser pour une production multi-techniciens.
- Exportez souvent les sauvegardes JSON. Le stockage local peut être effacé par le navigateur.
- Le QR code est généré via `api.qrserver.com`, qui reçoit l'URL de la fiche. Ne pas utiliser de données confidentielles.
- Le scan utilise l'appareil photo natif du téléphone pour ouvrir le lien. Un lecteur intégré n'est pas inclus.
- Les interventions et leur chronométrage sont des fonctions de test. Les modifications/suppressions sont permises, avec corbeille pour les suppressions, mais sans audit immuable.
- L'accès au QR code sur un autre téléphone nécessite une base de données partagée à ajouter ultérieurement.
- Pas de gestion des photos, d'authentification, ni de récurrence automatique des tâches dans ce POC.

## Migration future

Prévoir une API et une base PostgreSQL sur le serveur de l'usine. Les données JSON exportées pourront servir de point de départ à une migration contrôlée.
