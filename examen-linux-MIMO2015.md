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
