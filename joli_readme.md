# CONCEPTS DE BASE DE RAILS : la "Biblo'thèque"

<p align="center">![alt text](http://www.centreculturelirlandais.com/content/cache/content/images/old_library_slider_660_360_s_c1.jpg "Biblo'thèque")</p>

*Débuter sur Ruby on Rails n'est pas chose évidente à première vue. Il s'agit donc d'en comprendre les concepts pour mieux les appréhender. Ainsi, à travers ce readme (codé en .md, héhé) vous allez parcourir le chemin des différentes requêtes d'un utilisateur face à un site web développé sur ce langage, qui permet de créer des sites web dit "dynamiques"...*

PS : Pour que la lecture ne soit pas ennuyeuse, je vous ai concocté une petite histoire, pas celles des "boiboîtes" cette fois-ci, mais celle de la "Bibl'othèque"

-----------------------------------------------

Je vous invite à parcourir les 6 points qui suivent permettant d'assimiler les concepts de base de Ruby On rails (ça va le faire !) : 

En introduction de mon histoire vous êtes l'un des utilisateurs de mon site, mais vous n'êtes devant un 


## 1. La différence entre un site statique et un site dynamique

* Site web statique : site qui sera visible par l'utilisateur tel qu'il a été conçu. Les pages, hébergées sur un serveur, seront toujours présentées de la même façon. 

* Site web dynamique : un site Web dynamique est un site Web dont les pages sont générées dynamiquement à la demande. **Le code s'exécute sur un serveur**, tel que Heroku sur pour les développeurs avec des bases de données.

Quand le site web statique sera l'équivalent d'un musée avec des livres, toujours les mêmes, le site web dynamique sera celle d'une bibliothèque avec du mouvement !


## 2. Le MVC = Model View Controller 

![alt text](http://french.railstutorial.org/images/figures/mvc_detailed-full.png "Chemin MVC")

Je vous laisse observer le chemin d'une requête d'un utilisateur sur votre site dynamique par l'URL.

* But : montrer une application web


1. L'utilisateur demande la page sur son navigateur via l'URL.
2. Le routeur envoie la requête de l'utilisateur au controleur. 
3. Le controlleurs fait une demande au model. 
4. Le modele interroge la BDD
5. La BDD renvoi la réponse
6. Le controlleur va l'envoyer à la view
7. La view va renvoyer cela au contrôleur
8. Le controleur le renvoi  l'utilisateur

Et sous forme imagée cela donnerait :

1. Vous, l'utilisateur, vous êtes face à une bibliothèque, une base de donnée, et vous demandez un certain livre (requête) à la personne à l'accueil (le routeur).
2. Cette personne de l'accueil va transmettre le message au "controller" le livre que vous souhaitez et va aussi lui souffler le type de livre qu'il s'agit. Lui choisira de chercher ou non le livre en question. En attendant, vous restez devant la bibliothèque à vous fumer un clope car votre demande a été traitée et vous aurez rapidement un retour sur votre demande.
3. Le controlleur va ensuite demander le livre au gardien de la bibliothèque (le model) qui a, lui seul, accès à aux nombreux livres a méticuleusement rangé dans le coffre fort des livres (la base de donnée)
4. Le model va entrer les indications de l'utilisateur dans le boitier électronique du coffre fort.
5. Si le livre est trouvé, le coffre fort va donner ce livre au model qui va le donner au controlleur.
6. Le controlleur va ensuite envoyer le livre au service des coffrets pour que le livre soit bien présenté dans un beau coffret. Pour le coup, le controller va envoyer la donner à la view pour imbriquer les données dans la page user.html.erb.
7. Le service des coffrets le redonne au controlleur une fois le coffret terminé.
8. Le controlleur va donner le coffret à l'utilsateur.

Voilà l'histoire de la Biblo-thèque !  


*Du côté du code* : pour le nom d'un controller il faut la première lettre en majuscule et un "s" en dernière lettre.
Pour le nom d'un model il faut une majuscle à la première lettre.
Le controller va aller chercher la méthode de celui demandé.


## 3. Les routes

Les routes permettent d’interpréter les URL et d’orienter vers les bonnes actions des controlleurs. 

*Du côté du code* : la configuration se trouve dans le fichier config/routes.rb ;)



## 4. Les Bases de Données

Une base de donnée est comme un gros tableau Excel avec plusieurs tables. Les feuilles sont parfois liées en elles.

Pour imager mes propos nous pourrions dire qu'une base de données est une blibliothèque que l'on rempli de livres, 

Nous savons qu'il faut une base de donnée. 



## 5. GET / POST

> La méthode "POST" du controlleur permet de créer dans la BDD.
> La méthode "GET" du controlleur permet d'avoir des données de la BDD, sans pour autant la modifier. 

S'il y a bien une règle à retenir c'est celle-ci. 

Plus de précision : Avec la méthode "GET" on va *piocher* une information en corrélation avec la requête de l'utilisateur. 

Ainsi, imaginez que la méthode GET est l'équivalent d'un lecteur dans une bibliothèque. Il va chercher une information présente dans une base de données, la bibliothèque puis il repose le livre, la donnée.
Alors que la méthode POST va plus être l'équivalent d'un auteur de livre qui pourra ajouter, modifier voire supprimer ses livres de la bibliothèque. Vous comprenez la logique ? 

La sécurité ... 


## 6. Le concept de migration

La migration sert à dire à rails de modifier la BDD. 
On peut d'ailleurs créer une table via le fichier dans le dossier "migrate". 
Il faut migrer pour aller dans la BDD.



## 7. Les relations entre les models des BDD

Commande terminal "rails g model article". On  


## 8. Les fonctions du CRUD

Le CRUD est un acronyme pour désigner 4 opérations de base pour gérer une base de donnée : 
1. *C*reate
2. *R*ead
3. *U*pdate
4. *D*elete

Il s'agira pour l'utilisateur de faire l'une de ces opérations selon les droits accordés à celui-ci.

Ainsi, dans notre histoire de Biblo'thèque vous, l'utilisteur, pourra selon les cas créer, lire, modifier voir supprimer certains livre selon les droits accordé à un utilisateur.







