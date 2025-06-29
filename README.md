# Projet Gestion Portfolio 


## Présentation du projet
Ce projet est une application web développée en PHP & MySQL permettant aux utilisateurs de gérer leur portfolio en ligne.  
Chaque utilisateur peut :
- S’inscrire, se connecter et mettre à jour son profil.
- Sélectionner ses compétences parmi celles proposées par un administrateur.
- Ajouter, modifier et supprimer ses projets (titre, description, image, lien).

Un administrateur peut quant à lui gérer la liste des compétences disponibles.



## Fonctionnalités implémentées
### 1. Authentification & gestion des comptes
- Inscription avec validation serveur des champs  
- Connexion sécurisée (sessions PHP) et option « Se souvenir de moi »  
- Gestion des rôles (admin / utilisateur)  
- Mise à jour des informations personnelles  
- Réinitialisation du mot de passe par lien sécurisé  
- Déconnexion et destruction sécurisée de la session  

### 2. Gestion des compétences
- CRUD des compétences (Admin)  
- Sélection des compétences par l’utilisateur  
- Niveau de compétence sur une échelle 1 (débutant) → 5 (expert)  

### 3. Gestion des projets
- Création, modification et suppression de projets  
- Chaque projet contient un titre, une description, une image et un lien externe  
- Upload d’images sécurisé (format & taille)  
- Affichage structuré en grille responsive  

### 4. Sécurité
- Protection contre les injections SQL (PDO + requêtes préparées)  
- Protection contre le XSS et la conservation des données saisies  
- Hachage des mots de passe avec `password_hash()`  
- Expiration automatique des sessions après inactivité  
- Sécurisation des accès (interdiction de l’interface admin aux non-admins)  

## Installation et utilisation

### Prérequis
- Serveur local (XAMPP, WAMP, MAMP, LAMP…)  
- PHP 8.x  
- MySQL / MariaDB  
- Un navigateur web moderne  
- Visual Studio Code (ou tout autre éditeur)  
- phpMyAdmin (ou équivalent GUI pour MySQL)  



### Étapes d’installation
1. **Cloner le dépôt**  
   git clone <url_de_votre_repo>
   cd projetb2

2. **Générer les hashes de mots de passe**
Dans un terminal :
    php -r "echo password_hash('password' PASSWORD_DEFAULT) . PHP_EOL;"

3. **Importer la base de données**
Avec phpMyAdmin :

    1.Créez la base projetb2 (utf8mb4_unicode_ci).

    2.Sélectionnez-la, allez dans l’onglet Importer, choisissez config/database.sql et exécutez.

4. **Configurer la connexion**
Modifiez config/database.php si nécessaire pour vos identifiants MySQL :
    define('DB_HOST', 'localhost');
    define('DB_PORT', 3306);
    define('DB_NAME', 'projetb2');
    define('DB_USER', 'projetb2');
    define('DB_PASS', 'password');

5. **Lancer le serveur PHP**
    php -S localhost:8000 -t public
Puis ouvrez : http://localhost:8000



## COMPTES DE TEST
Administrateur
    Email : alice@example.com
    Mot de passe : password

Utilisateurs
    Email : bob@example.com
    Mot de passe : password

    Email : charlie@example.com
    Mot de passe : password



## TECHNOLOGIES UTILISEES
    Langage : PHP 8.x (PDO)
    Base de données : MySQL / MariaDB
    Frontend : HTML5, CSS3
    Outils : Visual Studio Code, phpMyAdmin
    PHP/HTML/CSS
