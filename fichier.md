## R6 : Architectures matérielles et systèmes d’exploitation

### R6C3 : Systèmes d’exploitation

Gérer les droits et permissions d’accès aux fichiers.

- Connaître les droits sur les fichiers

L'option `-l` utilisée avec la commande `ls` en ligne de commande Linux précise dans sa sortie les informations suivantes pour chaque fichier ou répertoire :
- Les permissions : qui indiquent les droits d'accès du fichier ou du répertoire pour différents types d'utilisateurs (propriétaire, groupe, et autres).
- Le type : qui spécifie si l'élément est un fichier ordinaire, un répertoire, un lien symbolique, etc.
- Le nom de l'utilisateur propriétaire : qui est le nom de l'utilisateur ayant les droits de propriétaire sur le fichier ou le répertoire.
- Le nom du groupe propriétaire : qui est le nom du groupe ayant les droits de groupe sur le fichier ou le répertoire.
- La taille : qui indique la taille du fichier en octets.
- La date : qui montre la date de la dernière modification du fichier ou du répertoire.
- Le nom : qui est le nom du fichier ou du répertoire.

Exemple : 
```bash
localhost:~$ ls -l /home/ada/flask-csv-master
total 20
-rw-r--r--    1 root     root          1064 Mar 12 15:43 LICENSE
-rw-r--r--    1 root     root          1456 Mar 12 15:43 README.md
-rw-r--r--    1 root     root            89 Mar 12 15:43 data.csv
-rw-r--r--    1 root     root          2227 Mar 12 15:43 flask-csv.py
drwxrwxrwx    2 root     root           183 Mar 12 15:43 pages
