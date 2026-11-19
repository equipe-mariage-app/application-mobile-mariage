# Plan de travail et guide de réunion Sallio

Le premier résultat à viser est un parcours complet sur Android. Un propriétaire inscrit publie une salle depuis son téléphone. Un visiteur ouvre Sallio sans compte, trouve la salle et consulte sa fiche. À partir de ce parcours, l’équipe ajoute la gestion des disponibilités et la reprise de la réservation après connexion. Chaque étape produit des preuves pour la note, dans les issues, les PR, la CI, le README et la démonstration.

## 1. Décisions à prendre en réunion

Proposition pour 60 minutes. Reporter les décisions dans une issue de coordination ou une note dans GitHub Projects et créer aussitôt les issues du premier sprint.

| Temps | Sujet | Résultat attendu |
| --- | --- | --- |
| 0–10 min | Contraintes et calendrier | Confirmer la date du rendu, la prochaine revue, le barème détaillé s’il existe et les disponibilités des quatre membres. Vérifier l’accès enseignant au dépôt privé et la validation du sujet. |
| 10–25 min | Périmètre démontrable | Valider le parcours public et propriétaire. Décider si la réservation est une demande à accepter ou une confirmation directe, comment traiter une date déjà prise et si un paiement fait partie du rendu. |
| 25–35 min | Choix techniques | Choisir l’appareil Android de référence, la méthode de connexion à livrer en premier, le backend de développement et de démo, la gestion d’état et les langues à montrer. |
| 35–50 min | Répartition | Nommer les quatre référents, leurs relecteurs et un suppléant par lot. Choisir un objectif de sprint et les tickets que l’équipe peut finir avec sa capacité réelle. |
| 50–60 min | Mise en route | Vérifier le dépôt, créer le Project, choisir le responsable de la synchronisation des branches, fixer la prochaine démo et attribuer une première issue à chacun. |

**Décisions à écrire explicitement.** Pour US-36, écrire une phrase que tout le monde peut tester, par exemple « le client envoie une demande et le propriétaire l’accepte depuis son mobile » si l’équipe retient ce fonctionnement. Pour les disponibilités, préciser le sens d’un jour non renseigné et décider si une date peut être demandée dans ce cas. Le backlog actuel traite une date non renseignée comme inconnue. Pour la démo, choisir une méthode d’authentification en premier, un jeu de données fictives et deux comptes de test distincts. Je propose FR et NL pour illustrer la localisation en Belgique, à valider avec l’équipe. Les supports fournis indiquent l’internationalisation comme exigence et ne fixent pas de langues précises.

**État du dépôt au moment de la revue.** Le dépôt GitHub a pour branche par défaut `main` (`8a6a8e2`). `develop` (`7c97fae`) est son ancêtre, à sept commits de retard. Le README propose un flux via `develop`, tandis que le Dev Container et Docker Compose sont déjà sur `main`. La branche consultée contient le squelette Flutter avec son test de compteur. Le backlog Sallio prépare les stories produit. Le plan ci-dessous détaille aussi les tâches techniques à suivre. [Backlog Sallio](backlog-sallio.md) · [Dépôt GitHub](https://github.com/Kemadjou-Cabrel/application-mobile-mariage)

## 2. Exigences du cours et preuves à préparer

Le support d’introduction cite la fonctionnalité, la qualité du code, la documentation, l’UI/UX et la démarche agile. Il mentionne aussi l’examen et un bonus de participation. Les supports fournis ne donnent pas de pondération détaillée pour chaque critère du projet. L’équipe de quatre a été validée par le professeur selon votre retour.

| Exigence ou attente | Ce que Sallio doit montrer | Preuve à garder |
| --- | --- | --- |
| Application Flutter originale, sujet validé, présentation et soutenance. PDF 01, p. 6 et 11–14, 19. | Un besoin clair, des utilisateurs identifiés, des user stories et un parcours réel. Relier les maquettes aux écrans livrés. | Validation du sujet, README, maquettes, captures et scénario de soutenance. |
| Code propre et architecture. PDF 01, p. 15 et PDF 02, p. 15–23, 38–41. | Séparer présentation, règles métier et accès aux données. Justifier les dépendances et les choix de simplicité. | Schéma, deux PR illustrant les frontières et test d’une règle métier avec une dépendance remplacée. |
| Gestion d’état adaptée. PDF 01, p. 15 et PDF 03, p. 23–25, 34–44, 46–48. | Choisir et justifier une approche telle que Riverpod ou BLoC. Traiter chargement, résultat, vide et erreur pour les parcours concernés. | Une story complète, test d’état ou de widget et exemple où l’UI reflète le résultat asynchrone. |
| Qualité, CI/CD et tests. PDF 01, p. 15, PDF 04, p. 9, 29 et 32 et PDF 05, p. 38–48. | Faire tourner les **tests unitaires en CI**, explicitement obligatoires. Le support de tests propose aussi d’essayer un test de widget et un test d’intégration. Le build APK en CI est facultatif dans le support. | Workflow versionné, PR avec résultat GitHub Actions, tests lisibles, résultat d’intégration Android et, si retenu, artefact installable. |
| Internationalisation. PDF 01, p. 15 et PDF 05, p. 49–61. | Mettre en place les ressources de traduction, utiliser la locale pour les dates et les prix et valider les écrans du parcours retenu. | Ressources ARB et test ou comparaison des mêmes écrans dans les locales retenues. |
| Accessibilité et qualité UI/UX. PDF 01, p. 14–15 et PDF 05, p. 63–75. | Proposer une navigation cohérente, des libellés, des messages d’erreur compréhensibles, du contraste, des cibles tactiles adaptées et un affichage lisible avec un texte agrandi. | Captures, test de widget selon les règles d’accessibilité et courte vérification TalkBack sur Android. |
| Sécurité de l’application et du code. PDF 01, p. 15 et PDF 05, p. 47. | Lecture publique limitée aux informations publiées. Réservation avec compte actif. Écriture et gestion d’annonce autorisées au propriétaire concerné. Garder les secrets hors Git. | Règles versionnées, tests positifs et négatifs, exemple de configuration et trace de revue. |
| Démarche agile et dépôt GitHub. PDF 01, p. 11 et 17–19. | Dépôt privé avec accès en lecture pour l’enseignant indiqué dans le support. Planifier par issues ou équivalent, ouvrir des branches de fonctionnalité, faire des PR revues, fermer les issues et contribuer régulièrement à quatre. GitHub Projects est facultatif selon le support et choisi par l’équipe. | Project, historique par membre, issues reliées à des PR, revues, décisions et démos de sprint. |
| README complet. PDF 01, p. 12–13. | Présenter le besoin, des stories et des captures, les solutions existantes et les différences de Sallio, les choix techniques, le démarrage/build, le journal, le bilan et les suites. | README vérifié depuis un clone neuf avec liens vers les preuves techniques. |
| Capacités mobiles et environnement. PDF 01, p. 16 et PDF 05, p. 23–47. | Le hors-ligne, le GPS, la caméra, les performances, les notifications, les tâches de fond, le natif et le déploiement intelligent sont souhaités. L’équipe retient Docker pour la reproductibilité. Une option mobile cohérente, par exemple la photo d’annonce sur Android, peut être démontrée si le parcours principal est stable. | Dev Container validé sur deux postes, commandes de démarrage, preuve sur Android pour la fonctionnalité choisie. |

**Références du cours.** Les numéros désignent les pages des fichiers fournis. PDF 01 `m2-dam-01-introduction.pdf`, PDF 02 `m2-dam-02-architecture.pdf`, PDF 03 `m2-dam-03-state.pdf`, PDF 04 `m2-dam-04-testing.pdf`, PDF 05 `m2-dam-05-cicd-i18n-a11y.pdf`.

## 3. Découpage en incréments démontrables

Les durées et les dates se décident en fonction du calendrier de cours et de la capacité du groupe. Chaque incrément peut servir d’objectif d’itération. Le socle doit démarrer dès la réunion. Les quatre référents peuvent ensuite travailler en parallèle avec des contrats de données communs et des données fictives.

| Étape | Travail à livrer | Critère pour passer à la suite |
| --- | --- | --- |
| 0 · Socle commun | Vérifier les accès, aligner `develop`, configurer le Project, figer le SDK, vérifier Docker, démarrer la CI, poser une navigation et une convention de tests, décider backend et modèle minimal. | Les quatre personnes peuvent démarrer le projet avec la procédure convenue. Une PR avec revue et CI verte démontre le premier flux. |
| 1 · Explorer et accéder à son compte | Catalogue, filtre et fiche sur données fictives (US-07, 08, 10, 27). Compte et session (US-01, 03–06, 23, 25, 32), au minimum la méthode d’authentification décidée. Poser le thème Sallio, les ressources de langue et les critères d’accessibilité dès le premier écran. | Démo mobile d’une fiche ouverte sans compte et d’un compte éligible qui s’inscrit, se reconnecte et revient à l’exploration après déconnexion. |
| 2 · Publier et retrouver une vraie annonce | Accès propriétaire, création, liste et édition (US-20, 21, 28, 29). Relier le catalogue et la fiche à la même source persistante. Tester l’isolation entre propriétaires. | Le propriétaire A publie et modifie une salle depuis Android. Un visiteur la trouve sans compte et voit le changement. Le propriétaire B ne peut pas modifier cette salle. |
| 3 · Disponibilités et réservation | Saisie facultative et lecture publique des dates (US-30, 31). Authentification à l’action « Réserver » et reprise pour la même salle (US-35). Implémenter US-36 selon la décision de réunion et sa priorité. Ajouter l’historique US-16 lorsque les réservations ont une source fiable et que l’issue entre dans le rendu. | Démo d’une publication avec calendrier vide, puis de l’ajout d’une date et de sa lecture publique. La réservation reprend sur la même salle après connexion et l’écran affiche le statut réel du parcours livré. |
| 4 · Validation et soutenance | Terminer le parcours de confidentialité US-26 selon le traitement convenu, vérifier les cas limites, reproduire les tests, faire la recette Android, consolider README, preuves et support de démo. Prévoir une marge pour corriger les défauts. | Un membre peut repartir d’un clone neuf et un autre peut dérouler la démo. Les liens vers les preuves sont accessibles et correspondent à la version présentée. |

Attribuer US-26 dès le lancement pour cadrer l’accès et la suppression des données. Garder un ticket distinct pour sa recette avant rendu. Les stories **Should** et **Could** du backlog, comme la messagerie ou la carte, restent disponibles pour une itération ultérieure selon la capacité. Mettre à jour dans GitHub Projects les dates et l’ordre approximatif du backlog après la réunion. Le tableau ci-dessus est le scénario de planification proposé.

**Dépendances à traiter tôt.** US-21 dépend du parcours propriétaire US-20. US-30 dépend de l’annonce publiée et de « Mes salles ». US-31 réunit la fiche US-27 et le calendrier US-30. US-35 dépend du compte et de la fiche. US-36 utilise ce parcours et l’historique US-16 dépend des réservations réellement enregistrées. Le catalogue peut démarrer avec un dépôt de données fictives, puis passer à la persistance quand le contrat est validé.

## 4. Répartition à quatre

| Référent à nommer | Ce qu’il pilote | Première issue proposée | Preuve qu’il prépare |
| --- | --- | --- | --- |
| A · Catalogue et expérience mobile | Exploration, cartes, filtres, fiche, charte graphique, cohérence des ressources de traduction de ces écrans. | US-10 et enchaîner avec US-27. Préparer un catalogue fictif et une fiche ouverte sans compte. | Capture du parcours, test de widget pour les états et contrôle d’accessibilité. |
| B · Comptes et règles d’accès | Inscription, session, charte, accès propriétaire, reprise après connexion et règles d’accès avec C. | TECH-03, convenir de la méthode d’authentification et du contrat de session. Enchaîner sur US-01 et US-32. | Tests âge/charte/session et preuve du refus backend sans compte actif. |
| C · Espace propriétaire et persistance | Publication, édition, liste des annonces, calendrier facultatif et contrat de données avec A et B. | TECH-04, définir le modèle d’annonce et le dépôt de données. Enchaîner sur US-21. | Données de démo reproductibles, validation de formulaire et test entre propriétaires A et B. |
| D · Intégration et livraison | Docker, CI, exécution du parcours Android, intégration des contributions, README et répertoire des preuves avec toute l’équipe. | TECH-01 ou TECH-02 selon les accès. Démarrer le conteneur et obtenir une première PR vérifiée. | Lien GitHub Actions, procédure testée sur deux postes et test d’intégration principal. |

Chaque membre prend une issue livrable, écrit les tests liés à son travail, ouvre une PR et en relit au moins une sur le sprint. D pilote la CI et centralise les liens, tandis que les auteurs gardent la responsabilité de leurs tests et de leurs preuves. Proposer A relu par B, B par C, C par D, D par A, puis adapter selon le contenu et les absences. Garder un seul ticket principal en cours par personne au démarrage.

## 5. Tickets techniques à ouvrir dans GitHub

Les identifiants TECH ci-dessous servent à préparer les issues. Conserver ensuite les vrais numéros GitHub dans les PR et le tableau.

| Ticket | Travail | Critère d’acceptation |
| --- | --- | --- |
| TECH-01 · Dépôt, branches et Project | Vérifier accès équipe et enseignant, aligner les branches, ouvrir le tableau, activer ou convenir de la revue. | Les issues du sprint ont responsable, relecteur, critères et dépendances. Une première PR suit la convention documentée. |
| TECH-02 · Dev Container et CI | Épingler Flutter et lancer la première CI PR. | Deux membres obtiennent le même SDK. Un échec de test fait échouer le contrôle, puis une correction le fait repasser au vert. |
| TECH-03 · App et session | Choisir la gestion d’état, la méthode de connexion et le contrôle du compte actif. Définir où conserver l’action en attente. | Un composant présente chargement, données et erreur. Un test couvre la session et un autre la reprise du parcours après login. |
| TECH-04 · Modèle, données et permissions | Définir l’annonce publique, les données propriétaires, le stockage des photos, les disponibilités, les fixtures et la séparation démo/développement. | Deux comptes distincts et un visiteur peuvent exécuter les scénarios d’accès positifs et négatifs de la matrice de tests. |
| TECH-05 · i18n, thème et a11y | Centraliser les couleurs, les chaînes d’interface et les formats de dates/prix. Créer les premiers tests de widget accessibles. | Le même écran rendu dans les locales retenues présente des textes et des formats attendus, avec les cibles tactiles et libellés vérifiés. |
| TECH-06 · Test Android et livraison | Écrire ou documenter l’exécution du scénario d’intégration et définir comment installer la version de démo. Préparer l’artefact si l’équipe retient le build CI. | Un autre membre reproduit la démo à partir du commit ou du tag désigné. |
| TECH-07 · README et preuve d’évaluation | Relier les exigences aux issues/PR/tests, tenir le journal et préparer la soutenance. | Chaque exigence obligatoire renvoie vers une preuve consultable ou une issue ouverte avec responsable. |

## 6. GitHub Projects, branches, commits et PR

**Project.** Ouvrir une issue de dépôt par résultat vérifiable, puis l’ajouter au Project Sallio. Utiliser `Assignees`, `Status` et des champs `Priorité` (Must, Should, Could), `Epic` et `Itération`. Statuts proposés. « Backlog », « Prêt », « En cours », « En revue », « Terminé ». Mettre un label `bloqué` avec une description de la cause et de la prochaine action si nécessaire. Une vue Table regroupe le backlog par epic, une vue Board montre le sprint courant par statut. Chaque issue inclut le résultat, des critères testables, les dépendances et la preuve attendue. [GitHub Projects](https://docs.github.com/en/issues/planning-and-tracking-with-projects) · [Champs d’itération](https://docs.github.com/en/issues/planning-and-tracking-with-projects/understanding-fields/about-iteration-fields)

**Dépôt et branches.** Conserver le flux du README comme point de départ. Vérifier l’écart par `git fetch origin` puis `git rev-list --left-right --count origin/develop...origin/main`. Faire réviser une synchronisation `main → develop` avant de créer les branches de travail. Pour cette synchronisation et les PR de livraison entre branches longues, utiliser une fusion qui conserve les commits et leur filiation. `develop` reçoit les fonctionnalités intégrées. `main` reste la branche de démo validée. Activer les PR, une approbation et les contrôles requis sur les branches concernées si l’offre et les droits du dépôt le permettent. Dans le cas contraire, faire appliquer ces contrôles par le responsable de fusion et conserver la preuve de revue. Vérifier le niveau d’accès enseignant, notamment si le dépôt est hébergé par un compte personnel. [Branches protégées](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-protected-branches/about-protected-branches) · [Droits d’accès d’un dépôt personnel](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/repository-access-and-collaboration/permission-levels-for-a-personal-account-repository)

**Exemple sur l’issue fictive #42.**

```bash
git fetch origin
git switch -c feature/42-us-27-fiche-salle origin/develop
git add <fichiers-concernes>
git commit -m "feat(catalogue): afficher la fiche de salle"
git push -u origin feature/42-us-27-fiche-salle
```

Ouvrir la PR vers `develop` avec l’issue référencée par `Refs #42`. Décrire le résultat, les tests exécutés et les points que le relecteur doit vérifier. Pour un écran, joindre une capture ou une courte vidéo avec le scénario. Le relecteur vérifie les critères, la CI et les points de sécurité, localisation ou accessibilité concernés. Après intégration et validation, fermer l’issue selon la convention décidée. Pour une fermeture automatique à la livraison, mettre `Closes #42` dans la PR vers `main`, car GitHub interprète le mot-clé dans la description quand la PR cible la branche par défaut. Distinguer dans le tableau une story validée sur `develop` d’une version effectivement livrée sur `main`. [Lier PR et issue](https://docs.github.com/en/issues/tracking-your-work-with-issues/using-issues/linking-a-pull-request-to-an-issue)

| À remplir dans l’issue | Exemple |
| --- | --- |
| Titre et résultat | US-27 Consulter la fiche d’une salle. Un visiteur peut vérifier qu’une salle convient à son événement. |
| Critères | La fiche publique s’ouvre depuis une carte et affiche photo, capacité et prix par jour. Si la salle a été retirée entre-temps, un message invite à revenir au catalogue. |
| Organisation | Assigné A, revue B, Must, itération Explorer, lié à US-10 pour l’ouverture depuis une carte. |
| Preuve attendue | Test de widget et courte capture du parcours catalogue → fiche sans compte. |

Dans la PR correspondante, reprendre `Refs #42`, expliquer brièvement le changement, donner la procédure de vérification et joindre le résultat des tests et la capture. Des commits distincts facilitent la revue, par exemple `feat(catalogue): afficher la fiche de salle` et `test(catalogue): couvrir la fiche indisponible`.

**Cadence.** En début d’itération, choisir un objectif de démo et des tickets prêts. Faire un point court régulier pour signaler les blocages. En fin d’itération, montrer le parcours sur Android, noter les écarts et retenir une action d’amélioration pour la suivante. Mettre à jour le Project au moment du changement de statut.

## 7. Architecture, données et interface

- Organiser `lib/` par grandes fonctionnalités, par exemple `catalogue`, `auth`, `owner` et `booking`. Pour une fonctionnalité qui en a besoin, isoler présentation et gestion d’état, domaine en Dart et implémentation de données. Les widgets affichent la vue, le domaine applique ses règles et le dépôt de données masque Firebase ou les données fictives.
- Décider ensemble entre Riverpod, BLoC ou une autre solution justifiée. Tester tôt une lecture asynchrone sur un écran. Injecter le dépôt de données et prévoir un remplacement de test. Écrire dans le README un exemple du flux « widget → état → dépôt → données », avec les règles métier concernées.
- Si Firebase est confirmé, versionner les règles, le modèle et un moyen de charger des données fictives. Laisser les clés privées et comptes de service hors Git. Utiliser des fakes dans les tests Flutter rapides et l’émulateur ou un environnement de test dédié pour les scénarios d’accès. La même autorisation doit s’appliquer à un appel backend qu’à l’interface. [Tests de règles Firebase](https://firebase.google.com/docs/firestore/security/test-rules-emulator)
- Se mettre d’accord sur les champs minimaux d’une fiche publique, les identifiants d’annonce/propriétaire et les jours déclarés. Séparer les données de compte et les annonces en préparation de la lecture publique. Pour US-36, définir les statuts et la règle de concurrence avant de promettre une confirmation lorsque deux clients demandent le même jour.
- Reprendre la maquette Draw.io comme référence visuelle. Centraliser le bleu nuit `#0F2942`, l’orange `#FF6B00`, les composants et la navigation. Vérifier les contrastes du texte sur fond orange et l’état des contrôles avec le texte agrandi. Prévoir des libellés accessibles pour les icônes, distinguer les jours par un libellé en plus de la couleur et vérifier les cibles tactiles sur Android. [Accessibilité Flutter](https://docs.flutter.dev/ui/accessibility/accessibility-testing)
- Préparer `l10n.yaml`, les ressources ARB et leur génération dès les premiers écrans. Traduire les intitulés, les erreurs, les états vides et les libellés accessibles. Vérifier les formats de dates, la devise et les textes plus longs dans les locales retenues. [Internationalisation Flutter](https://docs.flutter.dev/ui/internationalization)

## 8. Docker, CI et livraison Android

### Docker et Dev Container

Le dépôt configure le service `flutter-workspace` avec l’image `ghcr.io/cirruslabs/flutter:stable` et le port 8080. Valider une version précise de Flutter compatible avec la contrainte Dart du `pubspec.yaml`, puis l’utiliser dans le conteneur et la CI. Choisir une image versionnée ou un digest validé et documenter la version. Tester le démarrage sur deux postes et corriger le bloc `git clone` du README, qui contient actuellement un lien Markdown dans une commande shell. [Docker Compose config](https://docs.docker.com/reference/cli/docker/compose/config/)

```bash
docker compose config
docker compose up -d
docker compose exec flutter-workspace flutter --version
docker compose exec flutter-workspace flutter pub get
docker compose exec flutter-workspace flutter test
```

Le navigateur peut servir d’aperçu de développement via le port 8080. Pour le serveur web dans le conteneur, documenter l’écoute sur `0.0.0.0`. Décider séparément où lancer l’émulateur Android et comment installer l’application sur appareil. Tester cette méthode avant la fin du premier sprint, notamment pour TalkBack, les permissions et la caméra si elle est retenue.

### Pipeline GitHub Actions

| Étape | Quand | Contrôles à mettre en place |
| --- | --- | --- |
| CI de vérification | Sur PR vers `develop` ou `main`, et sur intégration selon la convention | Installer le SDK fixé, exécuter `flutter pub get`, vérifier avec `dart format --output=none --set-exit-if-changed lib test`, lancer `flutter analyze` puis `flutter test`. Ajouter `flutter gen-l10n` avant l’analyse et les tests dès la mise en place d’ARB. Les tests unitaires doivent faire partie des contrôles. |
| Intégration Android | Après stabilisation de la tranche principale, en job séparé ou sur appareil avec preuve | Exécuter un scénario intégrant UI et données contrôlées. Archiver le résultat avec commit, appareil et compte de test utilisé. Garder les tests rapides de PR indépendants des services externes. |
| Livraison de démo | Sur un commit approuvé de `main` ou un tag décidé | Choisir une procédure d’installation reproductible. Si vous retenez le build APK en CI, produire un APK de démo en artefact Actions et vérifier qu’un autre membre peut l’installer. Garder le lien du run et le commit. |

Dans `.github/workflows/`, donner un nom stable au contrôle de PR et limiter les permissions du workflow au nécessaire. Documenter un run vert dès le socle et faire évoluer les tests à chaque parcours livré. Une publication en store ne figure pas dans les exigences fournies.

### Tests à répartir

| Niveau | Cas prioritaires pour Sallio | Preuve |
| --- | --- | --- |
| Unitaire Dart | Limite des 18 ans selon la date saisie, validation d’annonce, filtres, états public/privé, jours non renseignés et règle de calendrier. | Tests rapides dans `test/` exécutés en CI. |
| Widget | Ouverture d’une fiche, chargement/vide/erreur, retour vers la même salle après connexion, grande taille de texte, libellés et rendu localisé. | `flutter test`, assertions de widget et règles d’accessibilité là où elles sont pertinentes. |
| Règles backend | Un visiteur lit une annonce publiée. Un visiteur ne crée pas de réservation. Le propriétaire A modifie son annonce. B ne modifie ni l’annonce ni le calendrier de A. Une annonce en préparation reste privée. | Tests des règles sur données fictives, avec cas autorisés et refusés. |
| Intégration Android | Publier une salle avec le compte A, retrouver l’annonce sans compte, consulter ses disponibilités et vérifier le retour sur la même salle après authentification. Étendre au résultat de réservation si US-36 est livré. | Test Flutter `integration_test/` et exécution sur émulateur ou appareil documentée. |
| Recette manuelle | Installer la démo, tester TalkBack et la taille du texte, contrôler FR/NL si retenus et vérifier un cas réseau ou chargement dégradé. | Courte liste de vérification datée avec version et résultat. |

[Types de tests Flutter](https://docs.flutter.dev/testing/overview) · [Contrôles de statut GitHub](https://docs.github.com/en/pull-requests/reference/status-checks)

## 9. Définition de terminé et préparation du rendu

Une issue de fonctionnalité peut passer à « Terminé » après vérification de ces points applicables.

- Les critères d’acceptation sont vérifiés dans le parcours habituel de l’application et les cas d’échec utiles sont traités.
- Les tests concernés ont été écrits ou actualisés et la CI est verte.
- Les textes sont localisables. Les écrans et contrôles modifiés passent les vérifications d’accessibilité pertinentes.
- Les permissions et les données publiques ou privées sont vérifiées lorsqu’une règle d’accès change.
- Un pair a relu la PR, l’issue et la PR sont reliées, la preuve est consultable et le Project est à jour.
- Le README ou la documentation pertinente a été mis à jour si le démarrage, l’architecture ou le comportement attendu a changé.

À la dernière revue, vérifier que le README sert de point d’entrée au correcteur. Il doit pointer vers le Project, le workflow, une ou deux PR représentatives et la procédure de lancement et de test. Pour la démo, préparer deux comptes fictifs et un accès visiteur. Présenter le besoin, montrer une annonce publiée depuis le mobile propriétaire, la retrouver sans compte, consulter son calendrier, puis déclencher la réservation et montrer son état réel. Montrer ensuite une preuve de sécurité, de localisation, d’accessibilité et de revue/CI. Préparer des données déjà chargées et une courte capture de secours.

**Premier résultat à viser après la réunion.** Un premier ticket attribué à chaque référent, un objectif de démo commun, le flux Git convenu et une date pour la prochaine revue. La première PR qui passe la CI est le jalon du lancement.
