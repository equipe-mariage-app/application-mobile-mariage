# Organisation GitHub Sallio

Le modèle reprend l’accueil, la navigation latérale, les pages d’analyse et le journal de votre ancien projet. Le [wiki préparé](wiki/Home.md) contient sept pages, avec une [navigation latérale](wiki/_Sidebar.md). Le [plan de travail](plan-travail-sallio.md) et le [backlog](backlog-sallio.md) restent les références détaillées.

## Configuration du Project Sallio

Créer ou réutiliser un Project privé nommé « Sallio », puis le relier au dépôt depuis l’onglet Projects. Donner accès aux membres et vérifier les droits de consultation du professeur selon les consignes.

| Vue | Configuration |
| --- | --- |
| Backlog | Table, groupée par Epic, avec Priorité, responsable et Itération |
| Sprint courant | Board, filtré sur `iteration:@current`, groupé par Status |
| Jalons | Roadmap, basée sur les dates d’itération retenues |

Configurer les statuts Backlog, Prêt, En cours, En revue et Terminé. Reprendre les priorités Must, Should et Could. Préparer les premières issues avec TECH-01 à TECH-07 et les stories choisies au démarrage. Affecter les personnes et les dates validées en réunion. [Documentation GitHub Projects](https://docs.github.com/en/issues/planning-and-tracking-with-projects)

## Publication du wiki

Les fichiers de `docs/wiki/` peuvent être revus dans une PR. Une fois la documentation intégrée à `main`, un mainteneur peut activer le Wiki si le dépôt et son offre le permettent, créer la première page `Home` sur GitHub, puis publier les pages et `_Sidebar` dans le dépôt du Wiki. Les pages qui pointent vers le plan et le backlog supposent que ces fichiers sont visibles dans `main`. Sur un dépôt privé dont l’offre ne donne pas accès au Wiki, les pages restent utilisables depuis `docs/wiki/`. [Publication des pages Wiki](https://docs.github.com/en/communities/documenting-your-project-with-wikis/adding-or-editing-wiki-pages)
