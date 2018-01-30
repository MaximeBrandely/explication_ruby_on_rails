# CONCEPTS DE BASE DE RAILS : la "Biblo'thèque"

![alt text](http://www.centreculturelirlandais.com/content/cache/content/images/old_library_slider_660_360_s_c1.jpg "Biblo'thèque")

*Débuter sur Ruby on Rails n'est pas chose évidente à première vue. Il s'agit donc d'en comprendre les concepts pour mieux les appréhender. Ainsi, à travers ce readme (codé en markdown) vous allez parcourir le chemin des différentes requêtes d'un utilisateur face à un site web développé sur ce langage, qui permet de créer des sites web dit "dynamiques"...*

PS : Pour que la lecture ne soit pas ennuyeuse, je vous ai concocté une petite histoire, pas celles des "boiboîtes" cette fois-ci, mais celle de la "Bibl'othèque"

-----------------------------------------------

En introduction de mon histoire mettez vous dans la peau d'une personne qui souhaite avoir un livre dans une bibliothèque.

Je vous invite à parcourir les 6 points qui suivent permettant d'assimiler les concepts de base de Ruby On rails (ça va le faire !) : 


## 1. La différence entre un site statique et un site dynamique

* **Site web statique** : site qui sera visible par l'utilisateur tel qu'il a été conçu. Les pages, hébergées sur un serveur, seront toujours présentées de la même façon. 

* **Site web dynamique** : un site Web dynamique est un site Web dont les pages sont générées dynamiquement à la demande. **Le code s'exécute sur un serveur**, tel que Heroku pour les développeurs.

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
6. Le controlleur va l'envoyer à la view. Pour le coup, le controller va envoyer la donnée à la view pour imbriquer les données dans la page user.html.erb.
7. La view va renvoyer cela au contrôleur.
8. Le controlleur le renvoi  l'utilisateur

Et sous forme imagée cela donnerait :

1. Vous, l'utilisateur, vous êtes face à une bibliothèque, une base de donnée, et vous demandez un certain livre (requête) à la personne à l'accueil (le routeur).
2. Cette personne de l'accueil va transmettre le message au "controller" le livre que vous souhaitez et va aussi lui souffler le type de livre qu'il s'agit. Lui choisira de chercher ou non le livre en question. En attendant, vous restez devant la bibliothèque à vous fumer un clope car votre demande a été traitée et vous aurez rapidement un retour sur votre demande.
3. Le controlleur va ensuite demander le livre l'un des gardiens (les models) d'une partie bibliothèque qui ont, eux seuls, accès aux nombreux livres méticuleusement rangés dans le coffre fort des livres (la base de donnée). Attention, tous ont accès au coffre fort mais une fois à l'intérieur chacun a sa partie !
4. L'un des model va entrer les indications de l'utilisateur dans le moteur de recherche du coffre fort, "Biblo'ogle".
5. Si le livre est trouvé, le coffre fort va donner ce livre au model en question, qui va le donner au controlleur.
6. Le controlleur va ensuite envoyer le livre au service des coffrets pour que le livre soit bien présenté dans un beau coffret.
7. Le service des coffrets le redonne au controlleur une fois le coffret terminé.
8. Le controlleur va donner le coffret à l'utilsateur.

Voilà l'histoire de la Biblo-thèque !  


*Du côté du code* : pour le nom d'un controller il faut la première lettre en majuscule et un "s" en dernière lettre.
Pour le nom d'un model il faut une majuscle à la première lettre.
Le controller va aller chercher la méthode de celui demandé.


## 3. Les routes

Les routes permettent d’**interpréter les URL** et d’**orienter les controlleurs vers les bonnes actions à mener**. 

*Du côté du code* : la configuration se trouve dans le fichier config/routes.rb.



## 4. Les Bases de Données

Une base de donnée est comme un **gros tableau Excel avec plusieurs tables**. Les feuilles sont parfois liées en elles.

Pour imager mes propos nous pourrions dire qu'une base de données est le coffre fort qui renferme des livres de notre bibl'othèque 

Nous savons qu'il faut une base de donnée. 



## 5. GET / POST

> La méthode "POST" du controlleur permet de **créer dans la BDD.**
> La méthode "GET" du controlleur permet d'avoir des données de la BDD, **sans pour autant les modifier**. 


Plus de précision : Avec la méthode "GET" on va *piocher* une information en corrélation avec la requête de l'utilisateur. 

Ainsi, imaginez que la méthode GET est l'équivalent d'un lecteur dans une bibliothèque. Il va chercher une information présente dans une base de données, la bibliothèque puis il repose le livre, la donnée.
Alors que la méthode POST va plus être l'équivalent d'un auteur de livre qui pourra ajouter, modifier voire supprimer ses livres de la bibliothèque. Vous comprenez la logique ? 


## 6. Le concept de migration

La migration sert à dire à rails de modifier la BDD. On dit que **ce fichier ruby est une migration**. Il permet de changer la structure de votre base de données. 
Changer la structure d’une base de données, **c’est ajouter, supprimer ou modifier une table ou une colonne**. C’est comme remplir la première ligne d’un tableur avec le nom des colonnes. Si ces noms changent, il faut faire une migration pour changer sa structure. On peut d'ailleurs créer une table via le fichier dans le dossier "migrate". 

Dans notre histoire de "Biblo'thèque" c'est le model qui sait et peut modifier l'organisation des livres du coffre fort.

*Remarque :* Il faut migrer pour aller dans la BDD.



## 7. Les relations entre les models des BDD

Dans une application on aura très rapidement besoin de **"croiser" des informations** afin de relier certaines données (les articles auront des catégories par exemple). Pour cela, Rails permet de gérer des associations directement au niveau des modèles.

Il y a donc plusieurs modèles dans la Biblo'thèque ayant chacun leur propre petit coffre fort. 

A noter que c'est la commande "rails g model article" du terminal qui permettra d'en créer.   


## 8. Les fonctions du CRUD

Le CRUD est un acronyme pour désigner 4 opérations de base pour gérer une base de donnée : 
1. **C**reate
2. **R**ead
3. **U**pdate
4. **D**elete

Il s'agira pour l'utilisateur de faire l'une de ces opérations selon les droits accordés à celui-ci.

==> **Ainsi, dans notre histoire de Biblo'thèque vous, l'utilisateur, pourra selon les cas créer, lire, modifier voir supprimer certains livres selon les droits accordés à un utilisateur.**

----------------------------------------

### Plus d'informations :

Retrouvez l'excellent tutoriel créé par Félix, [ici](https://www.youtube.com/watch?v=deNytSPvAxA&feature=youtu.be) qui vous fait une traduction en vidéo du tutoriel officiel de Ruby On Rails, [ici](http://guides.rubyonrails.org/getting_started.html) !

### Merci de m'avoir lu jusqu'au bout chers correcteurs !

Koyote








