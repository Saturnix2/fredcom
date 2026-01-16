################################################################################
README_DEV_LOCAL.md
FICHIER PERSONNEL — NON VERSIONNÉ (gitignore)
################################################################################

OBJECTIF
--------
Reprendre rapidement le projet fredcom sans réfléchir,
sans hésiter et sans oublier une étape.

Ce document est un rituel de démarrage personnel.
Il n’a pas vocation à être partagé.


RÈGLE FONDAMENTALE
-----------------
Toutes les commandes sont exécutées depuis la racine du projet :
fredcom/


SÉQUENCE DE DÉMARRAGE — À RESPECTER STRICTEMENT DANS CET ORDRE
------------------------------------------------------------

1) MISE À JOUR DU CODE
---------------------
git pull
# Synchronisation avec GitHub avant toute modification locale


2) VÉRIFIER MA POSITION GIT
---------------------------
git status
# Vérifier :
# - la branche courante
# - l’absence de fichiers modifiés involontairement
#
# Rappel mental :
# HEAD = ma position actuelle dans l’arbre Git


3) DÉMARRER LA BASE DE DONNÉES (DOCKER)
--------------------------------------
docker compose up -d
# Démarre MySQL et phpMyAdmin

docker ps
# Vérifier la présence des conteneurs :
# - fredcom_db
# - fredcom_phpmyadmin


4) VÉRIFIER LA CONNEXION SYMFONY ↔ MYSQL
----------------------------------------
php bin/console doctrine:query:sql "SELECT 1"
# Résultat attendu : 1
# Si échec → NE PAS CODER


5) LANCER LE SERVEUR SYMFONY
----------------------------
symfony serve --no-tls --port=8002
# Application locale :
# http://127.0.0.1:8002


POINTS D’ACCÈS & RÉFÉRENCES (TABLEAU DE BORD)
--------------------------------------------

APPLICATION (SYMFONY)
- URL locale        : http://127.0.0.1:8002
- Contrôleurs       : src/Controller/
- Routes            : config/routes.yaml ou annotations PHP

BASE DE DONNÉES (MYSQL DOCKER)
- Host              : localhost
- Port              : 3307
- Database          : fredcom
- User              : fredcom

PHPMYADMIN
- URL               : http://127.0.0.1:8081
- User              : fredcom
- Password          : fredcom
- Usage             : inspection / debug / vérification

CONFIGURATION
- ENV local         : .env.local (non versionné)
- ENV par défaut    : .env
- Docker            : docker-compose.yml

GIT
- Branche principale: master
- Repo GitHub       : https://github.com/<user-ou-orga>/fredcom


RAPPELS CONCEPTUELS
------------------
Git        = gestion du temps
Commit     = photo d’un état
Push       = publication
Pull       = synchronisation
Docker     = environnement figé
SymfonyCLI = confort local
Doctrine   = base pilotée par le code
HEAD       = position réelle de travail


ARRÊT PROPRE DU PROJET
---------------------
symfony server:stop
# Arrêt du serveur Symfony

docker compose down
# Arrêt des conteneurs Docker

docker compose down -v
# ATTENTION : supprime aussi les données MySQL locales


RÈGLE FINALE
-----------
SI QUELQUE CHOSE NE FONCTIONNE PAS :
→ REVENIR À CE FICHIER
→ SUIVRE LA SÉQUENCE
→ NE PAS IMPROVISER


NOTES PERSONNELLES
-----------------
Pages créées :
Routes importantes :
Entités existantes :
Problèmes rencontrés :
Pièges à éviter :


FIN DU DOCUMENT
################################################################################

