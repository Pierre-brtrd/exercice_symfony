# Exercice Symfony

Dans cet exercice, nous allons mettre en place une application web Symfony qui va permmettre de présenter la promotion avec les profils de chacun. 

L'administration de l'application web se fera via un backoffice d'admin sécurisé avec login développé via Symfony.

Vous pouvez retrouvez le site d'exemple à reproduire en <a href="https://formation.pierre-bertrand-marketing.com/" target="_blank">cliquant ici</a>

Le travail à fournir est à rendre directement sur Github avec une branch (PR) aux conventions de nommage suivante : 

- `Votre Prénom & Nom-Votre promotion` 

_(exemple : `Pierre-Bertrand-MasterII`)_

Vous serez notez sur le développement complet de l'application, en respectant les bonnes pratiques et en utilisant toutes les fonctionnalités vu en cours.

### Téléchargez le repos :

Afin de pouvoir travailler de mannière collaborative, nous allons utiliser Gihtub, qui est un outil de versioning de code, il va vous permettre de créer vos propre branch, faire des commits réguliers pour voir l'avancée de votre développement et de poussée toutes vos modifications en ligne sur ce repos Github afin que je puisse récupérer votre travail et vous évaluer.

Voici les étapes à suivre :

- Allez sur le repos dans l'onglet `code`
- cliquez sur le bouton vert `code` et sélectionnez l'onglet `https`
- Copiez le lien du repos
- Ouvrer un terminal de commande
- Allez dans le dossier où vous voulez télécharger le repos.
  - Pour rappel `cd NomDossier` -> changement de dossier en ligne de commande
  - `cd ..` -> revenir dans le dossier précédent
  - `ls` -> montrer les fichiers dans le dossier actuel
- Entrez la commande

  ```shell
  git clone https://github.com/Pierre-brtrd/cours_symfony_pierre_brtrd.git
  ```

### Ouvrir votre branch de développement :

Une fois que le repos est sur votre poste (en local), vous allez devoir créer votre branch de travail __ATENTION, ne pas commencer le développement sur la branch master__.

Pour créer une nouvelle branch à votre nom, vous devez : 

- Ouvrir le dossier du repos que vous venez de télécharger avec VsCode
- Ouvrir un nouveau terminal et entrer la commande : 
  ```shell
  git checkout -b le-nom-de-votre-branch
  ```
Vous êtes maintenant sur votre branch et vous pouvez commencer votre développement.

### Process de commit :

À chaque étapes de l'exercice, vous allez devoir faire un commit, pour enregistrer vos modification et passer à l'étape de développement suivante.

Pour faire un commit, il faut : 

- Entrer la commande dans le terminal : 
  ```shell
  git status
  ```
  Cette commande va vous montrer les fichiers qui vont être modifiés par rapport à l'origine, vérifiez que tous les fichiers que vous avez modifiés sont dans la liste.

- Ensuite, entrer la commande : 
  ```shell
  git add .
  ```
  Cette commande va ajouter la liste des fichiers modifiés à la file d'attente du commit.
  
- Entrer la commande en mettant le sujet de votre commit (étape de développement) : 
  ```shell
  git commit -m "Le sujet de votre commit"
  ```
  Cette commande va faire le commit avec les fichiers insérant en file d'attente et va ajouter un nom au commit.

- Enfin, entrez la commande avec le nom de la branch que vous avez créé : 
  ```shell
  git push origin votre-branch
  ```
  Cette commande envoie le commit que vous venez de faire en local sur le repos distant (Github)
  
## Les étapes de développement :

__1. Configuration de l'environnement de développement :__

Pour faciliter les choses, nous allons utiliser docker pour préparer un environnement de développement stable pour syfmony.
Vous pouvez voir dans le dossier du repos que vous avez télécharger qu'il existe déjà des fichiers et des dossiers, c'est la configuration Docker que j'ai déjà préparé, vous n'avez plus qu'à lancer la construction de l'environnement :

- Entrez la commande
  ```shell
  docker-compose build
  ```
- Ensuite, entrez la commande
  ```shell
  docker-compose up -d
  ```
- Enfin, entrez la commande
  ```shell
  docker exec -it -u dev sf5_php bash
  ```
  **PUIS**
  ```shell
  cd sf5
  ```
- Vous êtes maintenant sur le terminal de l'environnement Docker et vous allez pouvoir débuter l'installation du projet Symfony.
  C'est également sur ce terminal que vous allez lancer les commandes pendant le développement du projet.
  
Maintenant, quand vous voulez effectuer des commandes sur la console de Symfony, vous devez avant tout vous connecter au terminal Docker avec la commande
```shell
docker exec -it -u dev sf5_php bash
```
La commande `exit` vous fera sortir du terminal Docker pour revenir au terminal local VsCode.

__2. Création de votre application Symfony :__

Vous devez créer votre projet symfony avec l'aide de __composer__ depuis le terminal Docker :
- ```shell
  composer create-project symfony/skeleton my_project_directory
  cd my_project_directory
  composer require webapp
  ```

__Faire votre commit avec le message "Init Symfony project"__

__3. Préparation de la base de donnée :__

Configurez la connection entre Symfony et votre base de donnée.

Les informations utiles : 
- db_user = `sf5`
- db_password = `sf5`
- URL = `@sf5_mysql`
- db_name = `sf5`

__Faire votre commit avec le message "Init database URL"__

__4. Création de votre première Entity :__

Créez une entity du nom de __Etudiants__ qui vous permettra de gérer toutes les informations sur les étudiants que vous allez afficher sur l'application symfony.

Vous devrez disposer des informations suivantes dans votre table :

- Nom
- Prénom
- Age
- Sexe
- Image
- Description

__Faire votre commit avec le message "Create Entity for Etudiants"__

__5. Création de Fixtures pour tester l'affichage en front :__

Une fois votre table créé, vous devez dans un premier temp créer des données fictive pour faire un test d'affichage sur le front de votre application avant de remplir entièrement votre table.

Vous devez donc : 
- Utiliser de bundle Fixtures -> <a href="https://symfony.com/doc/current/bundles/DoctrineFixturesBundle/index.html" target="_blank">lien de la doc</a>
- Configurer un profil d'étudiant via les Fixtures pour faire ensuite le test d'affichage
- Migrer les fixtures en base de donnée.

__Faire votre commit avec le message "Add Fixtures Etudiants"__

__6. Création de la première page :__

Vous devez dans un premier temps créer un Controller du nom de __FrontController__ qui vous permettra de configurer les routes (pages) ainsi que les requêtes à effectuer sur les pages.

Dans ce Controller, vous allez définir : 

- La route "/" qui sera la route pour votre homepage, 
- Définir les requpetes à effectuer pour récupérer tous les étudiants ainsi que toutes les informations utiles.
- Rendre le template TWIG correspondant à la homepage

Ensuite, vous devez créer le template TWIG qui devra être affiché pour la homepage. Vous n'avez pas d'obligation sur le design de la page, il faut simplement que la homepage affiche les informations suivantes : 

- Profil étudiant -> rapide présentation des étudiant, mais sans la description longue. (pas d'obligation d'afficher la photo, vous ferez la configuration d'upload photo plus tard dans le développement)

__Faire votre commit avec le message "Add HomePage & Controller config"__

__7. Création de la partie admin de l'application :__

Vous devez maintenant développer la partie admin de l'application afin de pouvoir ajouter, modifier ou supprimer des profils sur le site.

Créer un Controller du nom de __AdminController__ qui devra gérer toutes les routes et requêtes à effectuer pour gérer l'administration du site.

Créer un formulaire du nom de __EtudiantsFormType__ qui vous permettra d'envoyer toutes les informations à la base de donnée depuis votre page d'admin.

Créer le template TWIG qui sera affiché sur la homepage d'admin.

Configurez le Controller pour qu'il rende le template TWIG de la page d'admin.


__Faire votre commit avec le message "Add admin homepage"__



