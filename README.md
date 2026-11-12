# GMAO Maintenance V5 — GitHub Pages

## Nouveautés
- Quatre onglets dans cet ordre : **Scanner → Planning → Équipe → Machines**.
- À la clôture d’une tâche : compte rendu et **photos avant et après obligatoires** (photos complémentaires facultatives).
- Les photos sont visibles dans les détails de la tâche, y compris depuis l’historique des machines et le planning.
- Les photos peuvent être ajoutées, remplacées ou supprimées depuis une intervention terminée.
- Les photos sont compressées et stockées dans **IndexedDB**, à part des informations stockées dans **localStorage**.
- Export/import JSON englobe maintenant les photos, y compris celles associées à des tâches dans la corbeille.

## Installation
1. Exporter les données de la V4 avant la mise à jour.
2. Décompresser l’archive, copier tous les fichiers dans la racine de votre dépôt GitHub Pages et remplacer les anciens.
3. Ouvrir ou recharger la page sur iPhone (Safari), puis autoriser l’accès aux photos / à l’appareil photo selon le choix proposé par iOS.
4. Tester une tâche avec début → fin → compte rendu → photo avant et après → consulter l’historique.

## Limites importantes
- **POC local uniquement** : aucune synchronisation entre téléphones ; les QR codes ne partagent pas la base de données.
- Les photos ne sont pas téléchargées sur GitHub ni sur un serveur ; elles occupent l’espace local du navigateur. Safari peut purger les données du site : **exportez des sauvegardes JSON régulièrement** et conservez-les ailleurs.
- Les photos obligatoires sont contrôlées à la clôture, pas au moment du démarrage ; le technicien peut choisir une photo de sa photothèque. Pour documenter réellement l’état avant intervention, prenez la photo avant de commencer.
- L'export avec beaucoup de photos peut produire un JSON volumineux ; le stockage d'images sur un serveur sera nécessaire pour un usage partagé/production.
- La galerie et les photos dépendent du support IndexedDB du navigateur.
- Taux d’activité = temps chronométré / 9 h par jour, non une mesure directe de performance.
- Le POC n’a pas été validé sur un iPhone réel.

## Fichiers
`index.html`, `app.js`, `styles.css`, `sw.js`, `manifest.webmanifest`, `icon.svg`, `README.md`.
