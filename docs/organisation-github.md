# Organisation GitHub Sallio

Le modèle reprend l’accueil, la navigation latérale, les pages d’analyse et le journal de votre ancien projet. Le [wiki préparé](wiki/Home.md) contient sept pages, avec une [navigation latérale](wiki/_Sidebar.md). Le [plan de travail](plan-travail-sallio.md) et le [backlog](backlog-sallio.md) restent les références détaillées.

## Configuration du Project Sallio

Créer ou réutiliser un Project privé nommé « Sallio », puis le relier au dépôt depuis l’onglet Projects. Donner accès aux membres et vérifier les droits de consultation du professeur selon les consignes.

| Vue | Configuration |
| --- | --- |
| Backlog urgent | Board par Status, filtré sur les priorités Must et les éléments ouverts. Découper par responsable si utile. |
| Sprint en cours | Board par Status, filtré sur `iteration:@current`. |
| Prochain sprint | Board par Status, filtré sur `iteration:@next`. |
| Mes éléments | Table filtrée sur `assignee:@me`. |
| En revue | Table filtrée sur `status:"En revue"`, avec les PR liées. |
| Feuille de route | Roadmap, basée sur les dates des itérations retenues. |

Configurer les statuts Backlog, Prêt, En cours, En revue et Terminé. Afficher sur les cartes les responsables, la priorité Must, Should ou Could, l’itération et un champ Epic pour les lots Sallio. Ajouter une estimation seulement si l’équipe s’en sert pour planifier sa capacité. Les [issues TECH-01 à TECH-07](https://github.com/equipe-mariage-app/application-mobile-mariage/issues) sont le premier lot à importer. Affecter les personnes et les dates une fois décidées en réunion.

Avant de créer le Project, vérifier les projets existants de l’organisation. Si aucun Project Sallio n’existe et que GitHub autorise la copie du tableau MASI4 vers `equipe-mariage-app`, utiliser « Make a copy », en laissant la copie des brouillons désactivée. La copie reprend les vues, les champs et une partie des workflows. Relier ensuite le dépôt Sallio, adapter les filtres, vérifier la visibilité privée et importer uniquement les issues Sallio. Si la copie est inaccessible, recréer les six vues à partir du tableau ci-dessus. [Copier un Project](https://docs.github.com/en/issues/planning-and-tracking-with-projects/creating-projects/copying-an-existing-project)

Vérifier les workflows avant activation. Ajouter les nouvelles issues du dépôt Sallio dans « Backlog ». Déplacer une issue clôturée vers « Terminé » selon la convention de l’équipe. Garder le passage à « En revue » explicite et vérifier le lien entre issue et PR avant de compter une story comme livrée. [Documentation GitHub Projects](https://docs.github.com/en/issues/planning-and-tracking-with-projects)

## Publication du wiki

Les fichiers de `docs/wiki/` peuvent être revus dans une PR. Une fois la documentation intégrée à `main`, un mainteneur peut activer le Wiki si le dépôt et son offre le permettent, créer la première page `Home` sur GitHub, puis publier les pages et `_Sidebar` dans le dépôt du Wiki. Les pages qui pointent vers le plan et le backlog supposent que ces fichiers sont visibles dans `main`. Sur un dépôt privé dont l’offre ne donne pas accès au Wiki, les pages restent utilisables depuis `docs/wiki/`. [Publication des pages Wiki](https://docs.github.com/en/communities/documenting-your-project-with-wikis/adding-or-editing-wiki-pages)
