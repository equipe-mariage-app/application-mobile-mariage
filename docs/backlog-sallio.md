# Backlog Sallio

Sallio aide les personnes à trouver une salle pour un événement en Belgique. Dès l’ouverture de l’application, un visiteur peut parcourir le catalogue public, utiliser les filtres, ouvrir une fiche et consulter les disponibilités renseignées. Le compte devient obligatoire lorsque le visiteur choisit de réserver. Un propriétaire doit disposer d’un compte actif et être connecté pour publier et gérer ses annonces depuis l’application mobile. Il peut renseigner les disponibilités de chaque salle à sa convenance. La prise de contact est un complément au parcours principal.

L’inspiration Airbnb se traduit dans le parcours Sallio par des cartes photo, des filtres faciles d’accès, une fiche détaillée et une action « Réserver » depuis cette fiche. L’interface reprend l’identité visuelle de Sallio et présente les informations nécessaires à un événement, notamment la capacité et les types d’événements acceptés.

## Revue des besoins et du MVP

- Les fiches individuelles du Word classent la déconnexion (US-23), les conditions générales et la politique de confidentialité (US-25) et les demandes liées aux données (US-26) en **Must**, et la FAQ (US-24) en **Could**. Le tableau récapitulatif inverse ces priorités. Le backlog reprend celles des fiches individuelles, cohérentes avec le contenu décrit dans le tableau.
- La connexion au moment de réserver est définie dans US-35. Le traitement et la confirmation d’une réservation (US-36), puis son historique (US-16 et BF-12), restent **à cadrer**. Les jours renseignés dans le calendrier indiquent une disponibilité déclarée par le propriétaire.
- Dans le diagramme, associer au visiteur la recherche, la consultation d’une fiche et de ses disponibilités, puis le passage à la connexion lorsqu’il souhaite réserver. Côté propriétaire, faire apparaître l’accès à « Mes salles », la modification d’une annonce et la gestion des disponibilités. La modération des annonces et de la charte par un administrateur reste une décision produit distincte.
- Les priorités proposées placent la fiche de salle (US-27) et la gestion propriétaire (US-28 à US-31) dans le **Must**. Pour US-30 et US-31, le support du calendrier fait partie du MVP et le propriétaire garde le choix de le renseigner. Le contact par messagerie (US-17 à US-19) passe en **Could**.
- La première version du calendrier proposée ici fonctionne par journée, en cohérence avec le prix par jour du Word. Les langues supplémentaires, la modération et l’origine des avis sur les salles restent à définir par l’équipe. Le français est la langue de référence du backlog.
- Avant le sprint Compte, préciser les méthodes de connexion par e-mail et par téléphone, ainsi que le rôle de l’adresse e-mail demandée lors d’une inscription commencée par téléphone.

## Compte et inscription

### US-01 Commencer l’inscription

**Must · BF-01**

En tant que visiteur, je veux saisir mon adresse e-mail ou mon numéro de téléphone pour commencer mon inscription.

- [ ] Un e-mail ou un numéro de téléphone au format accepté permet de passer à l’étape suivante.
- [ ] Une valeur vide ou au format invalide affiche une erreur explicite près du champ.

### US-02 Utiliser un compte Google ou Apple

**Should · BF-01**

En tant que visiteur, je veux utiliser un compte Google ou Apple pour accéder à Sallio avec un compte que je possède déjà.

- [ ] Le bouton de chaque fournisseur retenu ouvre son parcours d’authentification.
- [ ] Une authentification réussie ouvre la session d’un utilisateur existant ou lance les étapes d’inscription restantes, y compris la date de naissance et la charte si elles sont requises.
- [ ] Une annulation ou un échec ramène à l’écran de connexion avec un message adapté.

### US-03 Renseigner mes informations d’inscription

**Must · BF-02**

En tant que nouvel utilisateur, je veux fournir mon prénom, mon nom et mon adresse e-mail pour créer mon profil Sallio.

- [ ] Les champs requis et l’adresse e-mail sont contrôlés avant de poursuivre.
- [ ] Lorsqu’un compte existe déjà avec cette adresse, l’application indique comment accéder au parcours de connexion.

### US-04 Saisir ma date de naissance

**Must · BF-02**

En tant que nouvel utilisateur, je veux choisir ma date de naissance pour compléter mon inscription.

- [ ] Une date confirmée s’affiche dans le format de la langue courante.
- [ ] Une date future est refusée. L’annulation conserve la dernière valeur confirmée.

### US-05 Vérifier mon admissibilité à l’inscription

**Must · BF-03**

En tant que nouvel utilisateur, je veux savoir si ma date de naissance me permet de m’inscrire pour comprendre la suite du parcours.

- [ ] L’inscription est bloquée avec une explication si la date saisie correspond à un âge inférieur à 18 ans.
- [ ] Le parcours peut continuer le jour du 18ᵉ anniversaire et au-delà, sous réserve des autres conditions d’inscription.

### US-06 Lire et accepter la charte

**Must · BF-04**

En tant que nouvel utilisateur, je veux lire la charte et choisir si je l’accepte pour décider de rejoindre Sallio.

- [ ] La charte est consultable avant l’activation du compte Sallio et présente les actions « Accepter et continuer » et « Refuser ».
- [ ] Après acceptation et validation des étapes précédentes, le profil Sallio est actif. L’utilisateur reprend l’action qui a déclenché l’inscription ou arrive sur l’accueil du catalogue.
- [ ] Un refus termine le parcours avec un profil Sallio inactif et l’accès aux fonctionnalités réservées bloqué. Le catalogue public reste accessible.

### US-32 Me connecter à mon compte existant

**Must · BF-01**

En tant que client ou propriétaire déjà inscrit, je veux me connecter pour retrouver mon profil et mes données.

- [ ] L’utilisateur peut se reconnecter avec la méthode d’authentification associée à son compte.
- [ ] Après connexion, il reprend l’action qui a demandé l’authentification, si une action est en cours. Il retrouve aussi son profil et, le cas échéant, ses annonces.
- [ ] Un échec d’authentification affiche une erreur et permet de réessayer.

## Recherche et fiche de salle

### US-07 Rechercher une salle par mot-clé

**Must · BF-05**

En tant que visiteur ou client connecté, je veux rechercher une salle par mot-clé pour trouver les annonces qui m’intéressent.

- [ ] La barre de recherche est utilisable depuis le catalogue sans compte.
- [ ] Les résultats reflètent le mot-clé saisi et s’actualisent lorsque la recherche change.
- [ ] Une recherche vide réaffiche le catalogue selon les filtres actifs. Une recherche sans résultat affiche un état dédié.

### US-08 Filtrer par type d’événement

**Must · BF-06**

En tant que visiteur ou client connecté, je veux filtrer les salles par type d’événement pour repérer celles qui conviennent à mon projet.

- [ ] Le filtre est disponible depuis le catalogue sans compte.
- [ ] La sélection d’un type affiche les annonces qui déclarent ce type, en tenant compte de la recherche en cours.
- [ ] « Tout » retire le filtre de type et conserve le mot-clé saisi.

### US-09 Explorer par ville

**Should · BF-07**

En tant que visiteur ou client connecté, je veux ouvrir la liste des salles d’une ville pour chercher près de mon événement.

- [ ] La sélection d’une ville affiche ses annonces publiées, y compris pour un visiteur sans compte.
- [ ] Le nom de la ville active est visible et le filtre peut être retiré.

### US-10 Comparer les salles dans le catalogue

**Must · BF-07**

En tant que visiteur ou client connecté, je veux voir les renseignements essentiels sur chaque carte pour repérer rapidement les salles à consulter.

- [ ] Au premier lancement, le visiteur arrive sur le catalogue et voit les annonces publiées sans compte.
- [ ] Une carte affiche la photo principale, le nom, la ville et le prix par jour.
- [ ] Une note apparaît lorsqu’une donnée d’avis est disponible.
- [ ] Une pression sur la carte ouvre la fiche de la salle correspondante (US-27).

### US-27 Consulter la fiche d’une salle

**Must · Nouveau besoin associé à BF-05 et BF-07**

En tant que visiteur ou client connecté, je veux consulter les photos, la description, la capacité, le prix par jour et la ville d’une salle pour décider si elle convient à mon événement.

- [ ] La fiche d’une annonce publiée s’ouvre pour un visiteur sans compte.
- [ ] La fiche correspond à l’annonce sélectionnée et affiche les informations publiées par le propriétaire, dont les types d’événements acceptés.
- [ ] Une annonce devenue indisponible à la consultation affiche un message explicite et permet de revenir au catalogue.
- [ ] La fiche donne accès aux disponibilités déclarées lorsque la fonctionnalité US-31 est livrée.

### US-11 Repérer les salles sur une carte

**Could · BF-08**

En tant que visiteur ou client connecté, je veux consulter les salles sur une carte pour comparer leur emplacement.

- [ ] La carte des salles est accessible sans compte.
- [ ] Une pression sur un repère ouvre l’aperçu ou la fiche de la salle correspondante.
- [ ] Si le client autorise la géolocalisation, il peut centrer la carte sur sa zone. Si elle est refusée ou indisponible, il peut parcourir la carte manuellement.

### US-31 Consulter les disponibilités d’une salle

**Must · Nouveau besoin · Dépend de US-27 et US-30**

En tant que visiteur ou client connecté, je veux voir les jours déclarés disponibles par le propriétaire pour savoir si la salle peut convenir à la date de mon événement.

- [ ] La fiche affiche les jours déclarés disponibles pour cette salle et distingue les dates dont la disponibilité est inconnue.
- [ ] Quand aucune date n’est indiquée, la fiche affiche « Disponibilités non renseignées ».
- [ ] Le calendrier est consultable sans compte et présente les informations comme déclarées par le propriétaire.
- [ ] Les états sont compréhensibles avec un libellé accessible, y compris sans distinction de couleur.

## Gestion des salles sur mobile

### US-20 Accéder à l’espace propriétaire

**Must · BF-15**

En tant que personne qui souhaite mettre une salle en location, je veux accéder à l’espace propriétaire avec mon compte Sallio pour gérer mes annonces.

- [ ] Un visiteur qui choisit de proposer une salle est invité à se connecter ou à créer un compte. Une fois son compte actif et sa session ouverte, il reprend le parcours propriétaire.
- [ ] Un utilisateur connecté peut choisir « Devenir propriétaire » depuis son profil. Après confirmation du changement de rôle, le statut propriétaire est visible.
- [ ] Un utilisateur déjà propriétaire accède à « Mes salles » depuis le profil et peut lancer une nouvelle publication.

### US-21 Publier une salle

**Must · BF-15 · Dépend de US-20**

En tant que propriétaire connecté, je veux publier une annonce depuis mon téléphone pour présenter ma salle aux visiteurs et aux clients.

- [ ] Le backend accepte la publication uniquement pour un propriétaire connecté dont le compte Sallio est actif.
- [ ] Le formulaire demande un nom, des photos, une description, une capacité, un prix par jour, une ville et les types d’événements acceptés. Les champs obligatoires et valeurs invalides sont signalés.
- [ ] Une publication réussie apparaît dans « Mes salles » et dans le catalogue avec ses données renseignées.
- [ ] Le propriétaire peut publier avec un calendrier vide et renseigner ses disponibilités ultérieurement.

### US-28 Voir mes salles dans l’application mobile

**Must · Nouveau besoin associé à BF-15 · Dépend de US-20**

En tant que propriétaire, je veux voir mes annonces au même endroit pour retrouver une salle et accéder à ses réglages.

- [ ] « Mes salles » affiche uniquement mes annonces, avec une photo, le nom, la ville, la capacité et le prix par jour visibles sur mobile.
- [ ] Depuis une annonce, je peux retrouver ses informations et accéder aux actions de modification et de gestion des disponibilités lorsqu’elles sont livrées.
- [ ] Si je n’ai publié aucune salle, un état vide propose d’en publier une.

### US-29 Modifier une annonce existante

**Must · Nouveau besoin associé à BF-15 · Dépend de US-21 et US-28**

En tant que propriétaire, je veux modifier les informations d’une salle déjà publiée pour garder mon annonce à jour.

- [ ] Le formulaire est prérempli avec les valeurs enregistrées et applique les mêmes validations que la publication.
- [ ] Après enregistrement, les valeurs actualisées apparaissent dans « Mes salles » et sur la fiche client.
- [ ] Une modification par un autre compte est refusée par le backend.

### US-30 Renseigner les disponibilités d’une salle

**Must · Nouveau besoin · Dépend de US-21 et US-28**

En tant que propriétaire, je veux ajouter, modifier ou retirer les jours disponibles de chaque salle depuis mon téléphone pour indiquer les dates auxquelles je peux la louer.

- [ ] À partir de « Mes salles », je peux ouvrir le calendrier de la salle sélectionnée, ajouter des jours disponibles, déplacer une disponibilité ou retirer des jours déjà enregistrés.
- [ ] Les jours sont enregistrés sans doublon, dans le calendrier de cette salle, et restent visibles après réouverture. Un jour passé ne peut pas être ajouté.
- [ ] Je peux laisser le calendrier vide, y compris après avoir retiré le dernier jour renseigné. L’annonce reste publiée.
- [ ] Toute modification du calendrier de cette salle par un autre compte est refusée par le backend.

## Favoris et dossiers

### US-12 Ajouter ou retirer une salle de mes favoris

**Should · BF-09**

En tant que client, je veux enregistrer les salles qui m’intéressent pour les retrouver facilement.

- [ ] Le bouton Favori reflète l’état actuel et permet d’ajouter ou de retirer la salle.
- [ ] La liste des favoris reflète le changement et retrouve les valeurs enregistrées à la réouverture.

### US-13 Créer un dossier d’événement

**Could · BF-10 · Dépend de US-12**

En tant que client, je veux créer un dossier par événement pour regrouper les salles que j’envisage.

- [ ] Un nom valide permet de créer un dossier visible avec son nombre de salles et sa date de dernière mise à jour.
- [ ] Le client peut ajouter une salle favorite au dossier. Le nombre de salles s’actualise.

### US-14 Mettre à jour un dossier d’événement

**Could · BF-10 · Dépend de US-13**

En tant que client, je veux renommer ou supprimer un dossier et retirer des salles du dossier pour organiser mes sélections.

- [ ] Le renommage ou le retrait d’une salle met le dossier à jour.
- [ ] La suppression d’un dossier exige une confirmation et conserve les annonces dans le catalogue ainsi que les favoris associés au compte.

### US-15 Retrouver les salles récemment consultées hors ligne

**Could · BF-11 et BNF-03 · Dépend de US-27**

En tant que client, je veux retrouver les salles récemment consultées sans connexion pour poursuivre ma comparaison en déplacement.

- [ ] Les fiches déjà consultées et disponibles sur l’appareil s’ouvrent sans réseau.
- [ ] L’écran signale le mode hors ligne et précise quand les données sont issues du cache, notamment les disponibilités.
- [ ] Un état vide explique qu’aucune salle récente n’est disponible sur l’appareil.

## Prise de contact

### US-17 Contacter le propriétaire depuis une fiche

**Could · BF-13 · Dépend de US-27**

En tant que client, je veux poser une question au propriétaire d’une salle pour obtenir les renseignements utiles à mon événement.

- [ ] Depuis une fiche, le client connecté peut ouvrir la conversation associée à cette salle et envoyer un message au propriétaire correspondant.
- [ ] Un message vide est refusé. Un échec d’envoi est visible et permet de réessayer.
- [ ] Seuls les participants à la conversation peuvent consulter son contenu.

### US-18 Répondre depuis l’application

**Could · BF-13 · Dépend de US-17**

En tant que propriétaire, je veux répondre aux messages reçus pour échanger avec les clients intéressés.

- [ ] Le propriétaire retrouve ses conversations avec la salle concernée et peut répondre depuis le mobile.
- [ ] La réponse apparaît dans la même conversation pour les deux participants.

### US-19 Repérer les messages non lus

**Could · BF-14 · Dépend de US-17 et US-18**

En tant que client ou propriétaire, je veux repérer les nouveaux messages pour retrouver les conversations à lire.

- [ ] Un badge dans l’application signale les messages non lus et s’actualise après la lecture de la conversation concernée.
- [ ] Le badge reste présent si d’autres conversations contiennent des messages non lus.

## Réservations

### US-35 Me connecter au moment de réserver

**Must · Nouveau besoin · Dépend de US-01, US-06, US-27 et US-32**

En tant que visiteur qui a choisi une salle, je veux pouvoir me connecter ou créer un compte au moment de réserver pour poursuivre depuis la même annonce.

- [ ] Depuis la fiche, l’action « Réserver » propose la connexion et la création de compte à un visiteur.
- [ ] Après connexion ou inscription terminée, l’utilisateur reprend la réservation de la même salle. Un utilisateur déjà connecté avec un compte actif poursuit directement.
- [ ] Si le visiteur annule la connexion ou l’inscription, il retrouve la fiche publique.
- [ ] Le backend refuse toute création de réservation sans session valide et compte Sallio actif.

### US-36 Réserver une salle

**À cadrer · Nouveau besoin · Dépend de US-35**

En tant que client connecté, je veux réserver une salle pour une date afin de savoir si je peux y organiser mon événement.

- [ ] Avant planification, l’équipe précise si le client envoie une demande à valider par le propriétaire ou reçoit une confirmation directe. Elle définit aussi la gestion d’une date déjà prise et le rôle éventuel du paiement.
- [ ] Lorsque le parcours est défini, le client peut sélectionner une date et voir le résultat de son action avec un libellé correspondant au statut réel.

### US-16 Consulter l’historique de mes réservations

**À cadrer · BF-12 · Dépend de US-36**

En tant que client, je veux retrouver mes réservations pour suivre mes événements passés et à venir.

- [ ] Une fois la source des réservations définie, seules les réservations du client connecté sont affichées, triées par date avec leur statut.
- [ ] Un état vide est prévu pour un compte sans réservation.
- [ ] L’historique s’appuie sur les réservations enregistrées selon le parcours défini dans US-36.

## Profil et paramètres

### US-22 Consulter et modifier mon profil

**Should · BF-16**

En tant que client ou propriétaire, je veux consulter et mettre à jour les informations et coordonnées de mon profil pour les garder exactes.

- [ ] Le profil affiche les informations modifiables de l’utilisateur connecté.
- [ ] Les changements valides sont enregistrés et visibles à la réouverture. Une valeur invalide affiche une erreur près du champ.

### US-23 Me déconnecter

**Must · BF-17**

En tant que client ou propriétaire, je veux fermer ma session pour protéger l’accès à mon compte.

- [ ] La déconnexion ferme la session et ramène à l’accueil public de l’application.
- [ ] Après déconnexion, l’accès à un écran réservé demande une nouvelle authentification.

### US-24 Trouver une réponse dans la FAQ

**Could · BF-18**

En tant que client ou propriétaire, je veux consulter la FAQ dans l’application pour répondre aux questions courantes sur Sallio.

- [ ] La FAQ est accessible depuis les paramètres et permet de lire une question et sa réponse.

### US-25 Lire les conditions et la politique de confidentialité

**Must · BF-20**

En tant qu’utilisateur, je veux consulter les conditions générales et la politique de confidentialité pour comprendre le fonctionnement de Sallio et l’usage de mes données.

- [ ] Les deux documents sont accessibles depuis des entrées distinctes et identifiables, y compris depuis le parcours d’inscription lorsqu’ils y sont mentionnés.

### US-26 Demander l’accès à mes données ou la suppression de mon compte

**Must · BF-21 et BNF-01**

En tant que client ou propriétaire, je veux pouvoir demander l’accès à mes données ou la suppression de mon compte depuis les paramètres pour exercer mes droits sur mes données.

- [ ] Les deux demandes sont accessibles depuis les paramètres de confidentialité et demandent la vérification du compte concerné.
- [ ] Le parcours de suppression demande une confirmation explicite. L’application accuse réception avec les étapes de traitement.
- [ ] Le traitement d’une demande d’accès permet de remettre les données au titulaire par un canal sécurisé. Le traitement d’une demande de suppression ferme l’accès au compte et applique les règles définies pour les données associées.
- [ ] Avant mise en œuvre, l’équipe définit le traitement des données liées au compte, notamment les annonces, les photos et les conversations.

### US-33 Voir mon profil public

**Could · À cadrer · BF-16**

En tant qu’utilisateur, je veux prévisualiser mon profil public pour savoir quelles informations sont visibles par les autres.

- [ ] Avant planification, l’équipe définit les acteurs qui peuvent consulter le profil public et les champs affichés.
- [ ] L’aperçu présenté au titulaire correspond aux informations destinées aux autres utilisateurs.

### US-34 Parrainer un propriétaire

**Could · À cadrer · BF-19**

En tant qu’utilisateur, je veux inviter un propriétaire à rejoindre Sallio pour qu’il puisse publier sa salle.

- [ ] Avant planification, l’équipe définit qui peut inviter, comment l’invitation est transmise et si un suivi ou une récompense sont prévus.

## Mise en place dans GitHub Projects

Pour la réunion et la planification d’équipe, utiliser le [plan de travail Sallio](plan-travail-sallio.md). Il inclut le socle technique, les responsabilités et les preuves d’évaluation. Le tableau ci-dessous reste un regroupement indicatif des stories produit.

Créer une issue du dépôt par story en reprenant le titre, le récit et les critères d’acceptation. Garder l’identifiant US dans le titre pour retrouver le lien avec le Word. Ajouter les issues au projet Sallio. Utiliser un champ de sélection « Priorité » avec les valeurs Must, Should et Could, et un champ de type « Itération » pour les sprints. Une vue Tableau peut servir au backlog par priorité et une vue Board au sprint en cours par statut. [Présentation de GitHub Projects](https://docs.github.com/en/issues/planning-and-tracking-with-projects) · [Champs d’itération](https://docs.github.com/en/issues/planning-and-tracking-with-projects/understanding-fields/about-iteration-fields)

| Sprint proposé | Objectif de démo | Stories candidates |
| --- | --- | --- |
| 1 | Créer un compte admissible, accepter la charte, puis se reconnecter | US-01, US-03 à US-06, US-23, US-25, US-32 |
| 2 | Publier une salle depuis un compte propriétaire, puis la trouver et ouvrir sa fiche sans compte | US-07, US-08, US-10, US-20, US-21, US-27, US-28 |
| 3 | Gérer les disponibilités, les consulter sans compte, puis se connecter pour commencer à réserver la même salle | US-26, US-29 à US-31, US-35 |

Les dates, la charge et les responsables se décident selon les disponibilités de l’équipe. Les stories qui demandent encore une décision prennent le statut « À cadrer ». Pour le suivi d’une story planifiée, les statuts proposés sont « À faire », « En cours », « En revue » et « Terminé ». Chaque story du sprint peut être reliée à la PR qui la livre et être clôturée après revue et validation de ses critères.

À suivre dès le premier sprint avec des issues techniques dédiées. Poser l’architecture Flutter et la gestion d’état, lancer les tests unitaires en CI, préparer la localisation des textes et définir les règles d’accès. Le catalogue public expose les informations des annonces publiées et leurs disponibilités déclarées. Les données de compte, les réservations et la gestion des annonces gardent leurs permissions propres. Ajouter aux premières revues la vérification des libellés, du contraste et du grossissement du texte sur mobile. Le mode sombre mentionné dans le Word reste à estimer avec le reste du travail d’interface.
