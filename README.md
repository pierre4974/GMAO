# GMAO Maintenance — Prototype V3

Application web installable (PWA) pour iPhone (Safari) et Android (Chrome). Déployable telle quelle sur GitHub Pages, sans build ni serveur.

## Installation sur GitHub Pages

1. Décompresser l'archive et téléverser **index.html, app.js, styles.css, sw.js, manifest.webmanifest et icon.svg** à la racine d'un dépôt GitHub.
2. GitHub > Settings > Pages > Deploy from a branch > main / (root).
3. Ouvrir le lien HTTPS du site depuis Safari sur iPhone ; bouton Partager > Sur l'écran d'accueil. Sur Android, Chrome > Installer l'application.
4. Après une mise à jour, recharger l'application ; si l'ancien écran reste affiché, fermer et rouvrir le site, éventuellement vider son cache (après avoir exporté une sauvegarde).

## Fonctionnalités

- **Scan QR en premier** : caméra arrière ou photo de QR code, accès à la fiche machine ; QR code généré pour chaque machine.
- **Machines** : création, modification, historique des interventions terminées et tâches en attente.
- **Planning** : calendrier mensuel, consultation des tâches prévues et interventions terminées en sélectionnant une date ; toutes les tâches sont liées à une machine.
- **Équipe** : création, modification, suppression des membres ; attribution de chaque tâche.
- **Chronométrage** : début, pause, reprise, fin et compte rendu obligatoire ; sessions horodatées. Un technicien ne peut pas avoir deux interventions en cours simultanément sur cet appareil.
- **Temps** : suivi de chaque technicien sur les cinq derniers jours *calendaires* (aujourd'hui inclus), base indicative de 9 h par jour. Pause exclue.
- **Corrections** : modifier les machines, équipes et tâches ; corbeille restaurable pour les suppressions autorisées.
- **Sauvegardes** : export/import JSON.

## Important : limites du POC

**Aucune synchronisation entre appareils** : le stockage est dans le navigateur de chaque téléphone (localStorage). Un QR code ne permet d'ouvrir la fiche que si les données de cette machine existent localement sur l'appareil qui le scanne. Pour plusieurs techniciens partageant les données, il faudra ultérieurement un serveur et une base commune.

Le lecteur et le générateur QR utilisent des bibliothèques hébergées sur Internet, qui nécessitent une connexion lors de leur chargement. Le scan caméra nécessite HTTPS et l'autorisation caméra. La PWA peut conserver des ressources en cache, mais son fonctionnement hors connexion complète n'est pas garanti.

Le pourcentage affiché mesure l'occupation par des sessions de maintenance chronométrées, **pas la productivité globale** : 9 heures par jour sont prises comme référence même les jours non travaillés. Les sessions des tâches supprimées ne sont plus comptées tant que la tâche n'est pas restaurée. Les modifications d'un compte rendu restent possibles dans ce POC ; un système multi-utilisateur devra enregistrer un journal d'audit.

Les données ne sont pas protégées par un système d'authentification. Ne pas utiliser de données sensibles, personnelles ou opérationnelles critiques dans le POC.

## Réutilisation de la V2

Cette version conserve la clé de stockage `gmao_simple_v1`, utilisée par le prototype précédent. **Faire un export JSON depuis la V2 avant de mettre à jour** par précaution. Les anciens champs `machines`, `tasks` et `team` sont repris, et le nouveau champ `trash` est ajouté automatiquement.

## Fichiers

- `index.html` : interface principale et navigation
- `styles.css` : styles iPhone/Android
- `app.js` : logique métiers et stockage
- `manifest.webmanifest` et `icon.svg` : installation comme application
- `sw.js` : cache de l'interface, versionné
