# Base de Données
Ce repo contient un site web qui gère les demandes des citoyens aux communes de la région Auvergne Rhone Alpes . Fait en HTML, CSS et PHP (avec mysqli)

## Exécution  
 Pour exécuter le code et avoir un rendu, il faut obligatoirement avoir un serveur php qui prend en compte l'extension mysqli.  
 Pour le faire en local, vous pouvez installer le serveur `MAMP` qui fait serveur Apache et serveur SQL.  
## Installation , Configuration et Lancement de MAMP (Windows)
### Installation
Vous pouvez télécharger la version correspondante à votre OS [ici](https://www.mamp.info/en/downloads). 
L'installation crééra un dossier MAMP dans votre OS(C:). 
### Lancement et Configuration
Une fois installé, ouvrez l'éxécutable (en tappant dans votre barre de recherche mamp), en haut à gauche , cliquez sur MAMP > Préferences.  
Choisissez alors les numéros de ports pour l'utilisation de MAMP.  
Les ports recommandés sont : `80` pour les serveur web et Nginx et `3306` pour le serveur SQL.  
Vous pouvez aussi choisir votre version de PHP (pour ce projet , j'ai pris la version 7.3.7).  

### Important 
Choisissez bien une version de php qui supporte bien mysqli (les rêquetes sont transmises via mysqli).  
Quand vous voudrez importer les fichiers de création ou peuplement de la base de donnés, il se pourrait que vous rencontriez un problème sur la taille maximale autorisée par phpMyAdmin.  
Pour augmenter cette taille, localisez `C:\MAMP\conf\php\phpX.X.X\php.ini` (où x.x.x est la version de vore php) ,ouvrez le fichier avec un éditeur de texte et trouvez ces lignes :  

```bash
    upload_max_filesize = 2M
    post_max_size = 8M
```  
Modifiez les valeurs en fonctions de votre besion, par exemple : 
```bash
    upload_max_filesize = 50M
    post_max_size = 50M
```  
Un petit conseil : assurez-vous que post_max_size soit au moins aussi grand que upload_max_filesize.  

## Lancement de phpMyAdmin  
Ouvrez MAMP, activez les serveurs PHP et SQL (normalement dès que vous lancez mamp, ils s'activent par défaut)  
Une fois les serveurs actifs, ouvrez votre navigateur web et tappez dans la barre de recherche : localhost/phpMyAdmin.  
Si tous va bien, vous verrez l'interface de phpMyAdmin.  

## Création des bases 
Pour ce projet, vous devrez créez 2 bases de données.  
Sur phpMyAdmin en haut à gauche, vous verrez `Nouvelle base de données`.  
Si vous cliquez dessus, vous aurez à renseigner le nom de votre base et la créer.  
#### La base dataset
Cette base doit avoir le nom `dataset` pour permettre aux requêtes sql d'aboutir.
#### Votre base 
Créez une 2e base , vous pourrez lui donner le nom que vous voulez  

## Peuplement des bases
Dans le dossier Scripts SQL, vous trouverez 3 fichiers.  
Le fichier `dataset` sert à créer les tables et remplir la base du même nom.
Le fichier `scrip_creation_base` servira à créer votre les tables base de données (celle avce le nom que vous voulez).  
Le deriner fichier servira à remplir les tables de votre base.  
## Importer le fichier sql dans phpMyAdmin  
Vous devez lz faire pour les 3 fichiers séparement.  
Cliquez sur le nom de votre base.  
Sur la ligne horizontale du haut, cliquez sur `importer` , parcourez vos dossiers pour trouver le fichier et une fois chargé, en bas à droite, cliquez sur éxécuter.  
Normalement ça marchera.  
Faites cela pour le fichier dataset dans la base dataset et les 2 autres dans votre base en començant par la création de la base.

## Modifications dans le fichier 'config-bd.php' du dossier inc
Vous aurez à modifier la dernière ligne `define('BDD', "BDIbra");` en remplaçant "BDIbra" par le nom de votre base.  

## Affichage du site 
Copiez ce repo dans votre `C:\MAMP\htdocs` et ouvrez votre navigateur web et tappez : `https://localhost`.  
Trouvez le repos depuis le navigateur, cliquez dessus et vous aurez la page.  

## PS
Ce projet a été réalisé en binome avec [Elhadj Amadou Barry](https://github.com/barryelhadj23).  
Sur son repo, se trouve la version commune.  
J'ai retravaillé le projet après.
