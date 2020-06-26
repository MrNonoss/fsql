Voici un template tout fait pour importer facilement et rapidement des dumps MySQL. \

Attention, ici, rien n'est sécurisé, ce n'est pas destiné à une utilisation en production, mais juste pour pouvoir remonter un dump MySQL facilement lors d'une analyse et le visualiser avec PHPMyadmin.
Ici, il n'y a aucun mot de passe, alors protégez votre instance qui ne doit pas être accéssible depuis le net. \
 \
On utilise les images officielles mysql:latest et phpmyadmin:latest \
 \
##USAGE: \
 \
Consignes: \
1 - cloner le dépot, \
2 - Copier les dumps dans le répertoire "share", \
3 - exécuter le docker-compose, \
4 - exécuter un bash dans le container, \
5 - créer une base de données vierge, \
6 - sortir de la console mysql, \
7 - lancer l'import de la base, \
8 - la visualiser dans PHPMyadmin. \
 \
Prenons l'exemple d'une base de données exemple.sql: \
```
git clone https://github.com/MrNonoss/fsql.git
mv exemple.sql fsql/share/ && cd fsql
docker-compose up -d
sudo docker exec -ti mysql /bin/bash
mysql
CREATE DATABASE exemple;
exit
mysql -u root exemple < /home/share/exemple.sql
```
Plus qu'à ouvrir son navigateur à l'adresse http://localhost et se connecter avec l'user root, sans mot de passe
