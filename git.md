git init: initialise un depôt
git add : ajoute le fichier à l'index. c-à-d indexé le fichier
git status: permet de voir les modifications apportées aux fichiers du repertoire git
git log: permet de voir les series de commit éffectués (l'historique des modifs)
git commit -a -m: permet rajouté tous les fichiers se trouvant déjà dans l'index s'ils ont des modifications
git checkout id_commit(sha): permet de se positionner sur un commit specifié(pour revenir au commit le plus recent on utilise git checkout "master")
git commit --amend -m "Votre nouveau message": permet de modifier le message du dernier commit s'il n'est pas pushé 
git reset --hard‌:permet d'annuler une modification non commité
git pull: permet de récupérer une modification faite depuis un autre ordinateur ou un remote
git branch "nom de la branche" : permet de créer une branchhe
git merge "nom de la branche" : permet de fusionner la branche courante à celle indiqué sur la ligne de commande;
git blame : permet de voir plus rapidement qui a fait un commit et à quel niveau et pourquoi
git show "SHA(id_commit)": permet de voir exactement le contenu d'un commit
.gitignore : permet d'ignorer des fichiers 
