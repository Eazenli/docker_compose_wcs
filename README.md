### WordPress + MySQl en Docker (exercice)
Ce projet propose une application WordPress connectée à une base de données MySQL, déployée via **Docker Compose**.  
Les informations sensibles sont protégées à l’aide de **Docker Secrets**, et la configuration est externalisée dans un fichier `.env`.

#### Arborescence du projet 
docker_wordpress
├── compose.yml \
├── .env \
├── env.exemple.env \
├── .gitignore \
├── secrets/ \
│   ├── db_user_password.txt (non versionné) \
│   └── db_root_password.txt (non versionné)
├── README.md

#### Variables d'environnement (.env)
MYSQL_DATABASE > Nom de la base MySQL à créer (ex. wordpress_db) \
MYSQL_USER > Nom de l'utilisateur MySQL utilisé par WordPress \
WORDPRESS_DB_NAME > Nom de la base utilisée par WordPress (doit être identique à MYSQL_DATABASE) \
WORDPRESS_DB_USER > Utilisateur utilisé par WordPress (identique à MYSQL_USER) \
WORDPRESS_DB_HOST > Nom du service MySQL dans le réseau Docker (ex. wordpress_db:3306) \
WORDPRESS_DB_PASSWORD > Variable utilisée uniquement pour compatibilité ; la vraie valeur est lue via un secret 

#### Secrets 
dans le fichier secrets : \
'votre_mot_de_passe_root' > secrets/db_root_password.txt \
'votre_mot_de_passe_utilisateur' > secrets/db_user_password.txt 





