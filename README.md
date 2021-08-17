# Exercice Symfony

Dans cet exercice, nous allons mettre en place une application web Symfony qui va permmettre de présenter la promotion avec les profils de chacun. 

L'administration de l'application web se fera via un backoffice d'admin sécurisé avec login développé via Symfony.

Vous pouvez retrouvez le site d'exemple à reproduire en <a href="https://formation.pierre-bertrand-marketing.com/" target="_blank">cliquant ici</a>

Le travail à fournir est à rendre directement sur Github avec une branch (PR) aux conventions de nommage suivante : 

- `Votre Prénom & Nom-Votre promotion` 

_(exemple : `Pierre-Bertrand-MasterII`)_

Vous serez notez sur le développement complet de l'application, en respectant les bonnes pratiques et en utilisant toutes les fonctionnalités vu en cours.

## Téléchargez le repos :

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

## Ouvrir votre branch de développement :

Une fois que le repos est sur votre poste (en local), vous allez devoir créer votre branch de travail __ATENTION, ne pas commencer le développement sur la branch master__.

Pour créer une nouvelle branch à votre nom, vous devez : 

- Ouvrir VsCode
- Ouvrir un nouveau terminal et entrer la commande : 
  ```shell
  git checkout -b le-nom-de-votre-branch
  ```
Vous êtes maintenant sur votre branch et vous pouvez commencer votre développement.

## Process de commit :

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






