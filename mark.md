# Connexion au serveur distant
ssh utilisateur@adresse_ip

# Mise à jour du système
sudo apt update && sudo apt upgrade -y

# Installation des outils nécessaires
sudo apt install unzip curl git composer mysql-server nginx -y

# Vérification de Composer
composer -v

# Sécurisation de MySQL
sudo mysql_secure_installation

# Configuration de MySQL
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'nouveaumotdepasse';
FLUSH PRIVILEGES;
CREATE DATABASE nombdd CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
CREATE USER 'nom_user'@'localhost' IDENTIFIED BY 'motdepassefort';
GRANT ALL PRIVILEGES ON nombdd.* TO 'nom_user'@'localhost';
FLUSH PRIVILEGES;

# Installation de Symfony CLI
wget https://get.symfony.com/cli/installer -O - | bash
sudo mv /home/ubuntu/.symfony/bin/symfony /usr/local/bin/symfony

# Démarrage du serveur Symfony (test local)
symfony server:start

# Configuration des droits pour le serveur web
sudo chown -R ubuntu:www-data /var/www
sudo chmod -R 775 var/

# Clonage du projet depuis GitHub
cd /var/www
git clone git@github.com:utilisateur/mon-projet.git production

# Configuration des variables d'environnement
cp .env .env.local
nano .env.local
# Modifier APP_ENV=prod et les informations de base de données

# Installation des dépendances pour la production
composer install --no-dev --optimize-autoloader

# Migration de la base de données
php bin/console doctrine:migrations:migrate --no-interaction --env=prod

# Gestion du cache
php bin/console cache:clear --env=prod
php bin/console cache:warmup --env=prod

# Compilation des assets
php bin/console asset-map:compile

# Configuration de Nginx
sudo nano /etc/nginx/sites-available/mon_projet
sudo ln -s /etc/nginx/sites-available/production /etc/nginx/sites-enabled/
sudo rm /etc/nginx/sites-enabled/default
sudo nginx -t
sudo systemctl reload nginx
sudo systemctl status nginx
