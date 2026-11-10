# Maintenance — POC simplifié

Application PWA statique pour GitHub Pages. Deux menus : Machines / QR et Planning.

## Publication
1. Créez un dépôt GitHub.
2. Envoyez **le contenu de ce dossier** à la racine du dépôt.
3. Settings > Pages > Deploy from a branch > main > /(root).
4. Ouvrez l’URL Pages dans Safari sur iPhone et choisissez Partager > Ajouter à l’écran d’accueil.

## Fonctionnement
- Ajoutez vos machines, puis ouvrez leur fiche pour afficher et imprimer un QR code.
- Le QR code contient un lien vers cette application avec l’identifiant de la machine.
- Depuis le calendrier, ajoutez une tâche liée à une machine. Une fois terminée, elle apparaît dans l’historique de cette machine.
- Une intervention non planifiée peut être ajoutée depuis la fiche machine.
- Les interventions et machines peuvent être modifiées ou supprimées (confirmation avant suppression).
- Exportez régulièrement les données JSON ; l’import **remplace** les données existantes.

## Limites importantes
- Données uniquement dans le stockage local du navigateur : pas de partage ni de synchronisation entre téléphones.
- Scanner un QR avec un autre téléphone ouvre le lien mais ne transfère pas l’historique ; importez la sauvegarde sur cet appareil pour y retrouver les machines.
- Le générateur QR utilise une bibliothèque chargée par CDN : connexion Internet nécessaire au premier chargement du générateur.
- Les suppressions sont définitives ; exportez vos données avant les tests importants.
- Le POC n’est pas une GMAO de production et n’a pas de système de comptes.
