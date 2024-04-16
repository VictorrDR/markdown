**<span style='color: red;'>## R6 : Architectures matérielles et systèmes d’exploitation</span>**

**### R6C3 : Systèmes d’exploitation**

*Gérer les droits et permissions d’accès aux fichiers.*

**<p style="text-align: center;color: red"> I. Connaître les droits sur les fichiers </p>**

L'option `-l` utilisée avec la commande `ls` en ligne de commande Linux précise dans sa sortie les informations suivantes pour chaque fichier ou répertoire :
- **Les permissions :** qui indiquent les droits d'accès du fichier ou du répertoire pour différents types d'utilisateurs (propriétaire, groupe, et autres).
- **Le type :** qui spécifie si l'élément est un fichier ordinaire, un répertoire, un lien symbolique, etc.
- **Le nom de l'utilisateur propriétaire :** qui est le nom de l'utilisateur ayant les droits de propriétaire sur le fichier ou le répertoire.
- **Le nom du groupe propriétaire :** qui est le nom du groupe ayant les droits de groupe sur le fichier ou le répertoire.
- **La taille :** qui indique la taille du fichier en octets.
- **La date :** qui montre la date de la dernière modification du fichier ou du répertoire.
- **Le nom :** qui est le nom du fichier ou du répertoire.

**Exemple :**
```bash
localhost:~$ ls -l /home/ada/flask-csv-master
total 20
-rw-r--r--    1 root     root          1064 Mar 12 15:43 LICENSE
-rw-r--r--    1 root     root          1456 Mar 12 15:43 README.md
-rw-r--r--    1 root     root            89 Mar 12 15:43 data.csv
-rw-r--r--    1 root     root          2227 Mar 12 15:43 flask-csv.py
drwxrwxrwx    2 root     root           183 Mar 12 15:43 pages
```

**total 20** : nombre total de blocs utilisés par les fichiers répertoriés dans le répertoire. 
*Les lignes suivantes représentent les fichiers et les répertoires dans le répertoire avec les informations suivantes :*
- **Les permissions** : `-rw-r--r--` pour les fichiers et `drwxrwxrwx` pour les répertoires. 
- **Le nombre de liens** : 1 pour les fichiers réguliers et le nombre de fichiers contenus dans le répertoire 
- **Le nom de l'utilisateur propriétaire** : root dans cet exemple.
- **Le nom du groupe propriétaire** : également root dans cet exemple.
- **La taille du fichier en octets** : par exemple, 1064, 1456, 89, 2227.
- **La date de dernière modification** : dans cet exemple, Mar 12 15:43.
- **Le nom du fichier ou du répertoire** : LICENSE, README.md, data.csv, flask-csv.py, ou pages.

**<p style="text-align: center; color: red"> II. Gérer les droits avec chmod</p>**

Un utilisateur a le droit de faire un `chmod` sur un fichier seulement si :

- **il est root**
- **il est propriétaire du fichier en question** 

`chmod` permet de modifier les permissions (ou droits d'accès) sur les fichiers et répertoires dans un système de fichiers.

Les options passées à la commande `chmod` sont indiquées comme cela:
`chmod options modes fichiers`
Pour un fichier, la syntaxe est la suivante :
`chmod [u g o a] [+ - =] [r w x] nom_du_fichier`
- **[u g o a]** : désigne les types de propriétaires concernés : **u** pour le propriétaire (user), **g** pour le groupe (group), **o** pour les autres (others), **a** pour tous (all).
- **[+ - =]** : désigne les changements d'état : **+** et **-** pour ajouter ou retirer un type de droit aux droits courants, et l'opérateur **=** pour les écraser.
- **[r w x]** : désigne les permissions : **r** pour read (lecture), **w** pour write (écriture), **x** pour execute (exécution). 

**Exemple :**
`chmod u+r,g-w,o= example.txt`
Dans ce cas :
- **u+r** : Ajoute la permission de lecture (**r**) pour le propriétaire (**u**).
- **g-w** : Retire la permission d'écriture (**w**) pour le groupe (**g**).
- **o=** : Écrase toutes les permissions existantes pour les autres (**o**), en ne leur accordant aucune permission.

**<p style="text-align: center;color: red"> III. Gérer les propriétaires avec chown</p>**
La commande `chown` permet de changer le propriétaire d'un fichier ou d'un dossier
La syntaxe générale de la commande `chown` est la suivante : `chown [utilisateur][:groupe] cible1 [cible2 ..]`.


Pour changer le propriétaire d'un fichier ou d'un dossier, vous pouvez utiliser la commande `chown` suivie du nom de l'utilisateur ou de l'utilisateur et du groupe séparés par **:** et enfin du nom de la cible.


Par exemple, pour rendre l'utilisateur python propriétaire du fichier nsi.txt, vous pouvez utiliser la commande : `chown python /home/lesson/nsi.txt`.

Si vous souhaitez modifier le propriétaire de tout le contenu d'un dossier de manière récursive, vous pouvez ajouter l'option **-R** : `chown -Rf utilisateur1 /home/dossier1`.

Il est également possible de modifier à la fois l'utilisateur et le groupe en spécifiant **utilisateur:groupe** dans la commande, par exemple : `chown john:eleve /home/lesson/nsi.txt`.

