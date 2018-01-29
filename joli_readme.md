# Joli Readme




## 1. La différence entre un site statique et un site dynamique

Un site statique est un site web qui sera visible par l'utilisateur tel qu'il a été conçu. Elles seront toujours présentées de la même façon. 
Dynamique : le code s'exécute sur le serveur, tel que Heroku. 
Rdv sur http://localhost:3000. 



## 2. Le MVC = Model View Controller 

* But : montrer une application web


![alt text](http://french.railstutorial.org/images/figures/mvc_detailed-full.png "Logo Title Text 1")


1. L'utilisateur demande la page sur son navigateur
2. Le routeur envoie la requête de l'utilisateur au controleur. 
3. Le controleur fait une demande au model. 
4. Le modele interroge la BDD
5. La BDD renvoi la réponse
6. Le controleur va l'envoyer à la view
7. La view va renvoyer cela au contrôleur
8. Le controleur le renvoi  l'utilisateur

Pour le nom d'un controller il faut la première lettre en majuscule et un "s" en dernière lettre.
Pour le nom d'un model il faut une majuscle à la première lettre.
Le controller va aller chercher la méthode de celui demandé.


## 3. Les routes

## 4. Les Bases de Données

Une base de donnée est comme un gros tableau Excel avec plusieurs tables. Les feuilles sont parfois liées en elles.



## 5. GET / POST

> La méthode "POST" du controller permet de créer dans la BDD.
> La méthode "GET" du controller permet d'avoir des données de la BDD.


## 6. Le concept de migration

La migration sert à dire à rails de modifier la BDD. 
On peut d'ailleurs créer une table via le fichier dans le dossier "migrate". 
Il faut migrer pour aller dans la BDD.



## 7. Les relations entre les models des BDD

Commande terminal "rails g model article". On  


## 8. Les fonctions du CRUD