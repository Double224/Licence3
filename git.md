git init: initialise un depôt
git add : ajoute le fichier à l'index. c-à-d indexé le fichier
git status: permet de voir les modifications apportées aux fichiers du repertoire git
git log: permet de voir les series de commit éffectués (l'historique des modifs)
git commit -a -m: permet rajouté tous les fichiers se trouvant déjà dans l'index s'ils ont des modifications
git checkout id_commit(sha): permet de se positionner sur un commit specifié(pour revenir à au commit le plus recent on utilise git checkout "master")
git commit --amend -m "Votre nouveau message": permet de modifier le message du dernier commit s'il n'est pas pushé 
git reset --hard‌:permet d'annuler une modification non commité
