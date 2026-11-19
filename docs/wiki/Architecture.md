# Architecture et choix techniques

Le plan propose des fonctionnalités Flutter séparées en présentation et état, domaine, et accès aux données. Firebase reste le backend envisagé. Le choix de gestion d’état, la méthode d’authentification initiale et l’environnement de démo sont à consigner après validation.

| Donnée ou action | Accès prévu |
| --- | --- |
| Annonce publiée et disponibilités déclarées | Lecture publique |
| Publier une salle | Propriétaire connecté avec compte actif |
| Modifier une salle ou ses disponibilités | Propriétaire concerné |
| Démarrer une réservation | Compte actif |

Chaque décision technique importante indique son contexte, les options, la décision et le lien vers l’issue ou la PR.
