# Examen Linux
MIMO 2015

Les programmes nécessaires, si non présentes sur le poste, peuvent être installées.

En général cela devrait marcher:

* Sur GNU / Linux via sudo apt-get install COMMANDE
* Sur OS X via sudo brew install COMMANDE
* Sur Windows, je crois que la méthode GNU / Linux marche

Si tu n'arrives pas à récupérer le fichier demandé, prend un fichier au hasard.

1. Combien de lignes possède le fichier passwd.ibm1 ?

Je te laisse trouver ce que doit aller à la place de `option`

```
$ cat passwd | wc option
```

Pourquoi `cat`?

Parce que `cat nomdufichier` concatène (dans l'affichage à l'écran). Quand tu concatène une chose avec rien d'autre, tu obtiens juste l'affichace de la cose.
En concaténant `passwd` on affiche donc le contenu du fichier.

Pourquoi `|`?

Ça s'appelle "pipe", à l'anglaise, et il fait de tuyau qui rélie la commande qui précède, à la suivante. Le résultat de la commande précédente devient l'objet de la commande suivante.

Pourquoi `wc`?

Parce que cette commande permet de compter les mots ("word count")
Regardons comment elle marche avec

```
$ man wc
```

Lis le manuel et trouve la bonne option (tape `q` pour quitter le manuel).

Il est intéressant de remarquer par contre que l'option n'est pas nécessaire: elle permet juste d'avoir plus de clarté dans le résultat. Qu'est-ce qui se passe avec simplement `$ cat passwd | wc` ?


2. Quel est le dernier login par ordre alphabétique croissant du fichier `passwd.ibm1` ?

Regarde ce que fait la commande `sort`.

3. Combien de logins commencent par la lettre `j` ?
4. Lors de la création des utilisateurs une erreur a eu lieu. Le homedir de certains users a été positionné à `/home/p6chiM` alors qu’il aurait dû l’être à `/home/p6chim`. Que proposez vous pour changer cela ?
5. Combien de changements devez vous faire ?
6. Je tape la commande suivante
```
[mimo1@srv-mimo ~]$ id
uid=501(mimo1) gid=501(mimo1) groupes=501(mimo1)
```

a) Lorsque j’ai tapé cette commande dans quel répertoire étais-je sachant que tout les
comptes mimo se situent dans `/home` ? **Justifiez**.

b) Que me renvoie la commande indiquée (précisez pour chaque élément fournit)?

c) Je tape la commande suivante
```
ls -ail /var/log/audit/
ls: impossible d'ouvrir le répertoire /var/log/audit/: Permission non accordée
```
En regardant les droits sur le répertoire j’ai ceci
```
393185 drwxr-x---. 2 root root 4096 12 mars 09:10 audit
```
Expliquez la raison du message renvoyée par la commande `ls`

d) Indiquez les étapes qu’il faudrait faire pour me permettre d’accéder au contenu de ce
répertoire.

7. Je tape la commande suivante
```
[mimo1@srv-mimo ~]$ df
Filesystem
1K-blocks Used
Available Use% Mounted on
/dev/mapper/vg_srvmimo-lv_root 27359100 5480684 20488644 22% /
```
a) Quelle est la taille en GigaOctets de la partition `/` ?
b) Combien reste-t-il d’espace ?

8. J’utilise la commande suivante `tree -L 3 -F /var/www | grep /`
Voici le résultat.
```
[root@srv-mimo ~]# tree -L 3 -F /var/www | grep /
/var/www
├── cgi-bin/
├── error/
│ ├── include/
├── html/
├── icons/
│ ├── samples/
│ ├── small/
├── manual/
│ ├── developer/
│ ├── faq/
│ ├── howto/
│ ├── images/
│ ├── misc/
│ ├── mod/
│ ├── platform/
│ ├── programs/
│ ├── rewrite/
│ ├── ssl/
│ ├── style/
│ │ ├── css/
│ │ ├── lang/
│ │ ├── latex/
│ │ └── xsl/
│ └── vhosts/
└── usage/
```
a) Que fait la commande tapée ?
b) Je suis maintenant positionné dans le répertoire `xsl`.
Indiquez 2 commandes différentes permettant de me déplacer pour aller dans le
répertoire `small`.
c) Donner 2 commandes pour retourner dans mon homedir

9. Dans le répertoire /var/www/icons/ en utilisant la commande ls -ail je trouve ce résultat

~~10. J’ai besoin d’exécuter un programme fait en langage C et compilé.
Je dois donner des droits d’administrateur (root) uniquement durant l’exécution.
a) Que proposeriez vous ?
b) Donnez un exemple au niveau du système linux d’un fonctionnement identique.~~

11. Je désire ajouter une ligne à la fin d’un fichier nommé `fichier_sensible` qui en comporte déjà 10.
On me dit de tapez la commande suivante : `echo "ligne que j’ajoute" > fichier_sensible`. Qu’en pensez vous ? **Justifiez votre réponse**.
12. Voici la commande que je tape après m’être connecté directement au serveur en tant que `root`
```
root@srv-mimo ~]# ps -ef | grep ssh
root
1743 1 0 11:03 ?
00:00:00 /usr/sbin/sshd
root
2068 1743 0 11:03 ?
00:00:00 sshd: mimo1 [priv]
mimo1 2072 2068 0 11:04 ?
00:00:00 sshd: mimo1@pts/0
root
2930 2243 0 13:41 pts/0 00:00:00 grep ssh
```
a) Donnez la commande permettant de supprimer le processus concernant le
programme `/usr/sbin/sshd`
b) Quelle sera la conséquence de cette commande ?
c) Si je détruis le processus concernant le programme `sshd: mimo1@pts/0` que se passe-t-il ?
d) Dans le cas où je me suis d’abord connecté en user `mimo1` puis depuis ce compte en `root` que se passe-t-il ?
13. Je réalise en tant qu’utilisateur mimo1 des pages web dans mon
homedirectory dans le répertoire `WWW`.
Voici les informations dont je dispose :
```
[root@srv-mimo ~]# ps -ef | grep httpd
root
3141 1 2 14:21 ?
00:00:00 /usr/sbin/httpd
apache 3143 3141 0 14:21 ?
00:00:00 /usr/sbin/httpd
apache 3144 3141 0 14:21 ?
00:00:00 /usr/sbin/httpd
[root@srv-mimo ~]# id mimo1
uid=501(mimo1) gid=501(mimo1) groupes=501(mimo1)
[root@srv-mimo ~]# id apache
uid=48(apache) gid=48(apache) groupes=48(apache)
[mimo1@srv-mimo ~]$ ls -ailt
total 40
1315985 drwx------. 6 mimo1 mimo1 4096 25 mars 14:49 . .....
1436162 drwxr-x---. 2 mimo1 mimo1 4096 25 mars 14:49 WWW
1315932 -rw-------. 1 mimo1 mimo1 506 25 mars 13:46 .bash_history
1447507 drwxrwxr-x. 2 mimo1 mimo1 4096 25 mars 11:06 Examens
1305602 drwxr-xr-x. 19 root root 4096 12 mars 13:13 .. ...
```
a) Que devez vous modifier pour que ces pages soient accessibles via le web, avec
quelle syntaxe de commande ? **Justifiez brièvement**.
14. d
15. 
