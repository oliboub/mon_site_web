#<span style="color:orange">Formation skilleos git et github: les fondamentaux par Arnaud Mercier</span> 

***
#<span style="color:purple">git</span>

## <span style="color:blue">Préparer git</span>
Configurer git avec le username et le email.
  - **git config --global user.name** "aaaaa xxxxxxx"
  - **git config --global user.email** "xxxxxx@gmail.m"

## <span style="color:blue">Préparer l'environnement de formation</span>
  - Créer un dossier dans le répertoire à synchroniser<br>
  - mkdir /media/olivier/Donnees/Documents/Formations/skilleos git/cours_git/mon_site_web<br>
  - cd /media/olivier/Donnees/Documents/Formations/skilleos git/cours_git/mon_site_web<br>
  - ouvrir un terminal dans le répertoire en cours<br>
  - mettre les fichiers style.css et hello.html dans le répertoire
  - dans le terminal:
Note: *pour copier/coller une information de l'écran vers l'emplacement du curseur, il suffit de cliquer sur la molette de la souris*

## <span style="color:blue">git: initialisation d'un dépot</span>
  - Pour initialiser un dépot dans le répertoire en cours faire **git init**<br>
  - **git status** donne les infos courrante de notre dépot

## <span style="color:blue">git: ajouter des fichiers dans le dépot
- **git add** sert à indexer les nouveaux fichiers dans le dépot
  - **git add** hello.html style.css
  - **git status**
- Pour sortir un fichier du dépot, faire: **git reset** *nom du fichier*
  - **git reset** hello.html
  - **git status**
  - **git add** hello.html
- Pour enregistrer les modifications dans le dépot il faut faire **git commit -m "message"**<br>
  - **git commit -m "Mon premier commit"**

## <span style="color:blue">git: supprimer des fichiers dans le dépot
- **git rm** *fichier*

## <span style="color:blue">git: afficher les modifications</span>
- Modifier hello.html pour voir une version modifiée<br>
- Lancer git status pour voir si il détecte qu ele fichier a changé<br>
  - **git status**<br>
- Vérifier les modifications par **git diff**<br>
  - **git diff**<br>
- Ajouter les modifications dans la zone d'indexage<br>
  - **git add** hello.html<br>
- **git diff** ne montre plus rien<br>
- Une fois ajouté dans l'index , on peut voir les difference avec **git diff --cached**<br>
  - **git diff --cached**<br>
- Maintenant on enregistre les modifs dans le dépot<br>
  - **git commit -m "Modification de l'entete"**<br>

## <span style="color:blue">git: voir l'historique des commits</span>

- **git log** permet de voir l'historique avec les SHA-1 ainsi que les auteurs, les tags master et HEAD<br>
  - **git log**<br>
- Pour voir les modifications il faut lancer **git show** *SHA-1* du commit cherché<br>
  - **git show** *05ae748297c4db31e2e2e46a0ca686ab09e68238*<br>
- on peut aussi afficher les tags : **git show master**<br>
  - **git show master**<br>

## <span style="color:blue">git: naviguer dans l'historique des commits</span>

Pour revenir sur une version précédente, on doit déplacer le tag HEAD sur le commit voulu.<br>
  - git log<br>
- Pour revenir sur une version il faut utiliser **git checkout** *SHA-1*<br>
  - **git checkout** *SHA-1*<br>
Pour vérifier recharger la page web et on voit que la description n'y est plus.<br>
  - **git log** n'affiche plus que les 2 commits<br>
Pour revenir sur la branche master il faut faire: **git checkout** *master*<br>
  - **git checkout master**<br>
Pour vérifier recharger la page web et on voit à nouveau la description.<br>
  - **git log** affiche les 3 commits<br>
<br>
## <span style="color:blue">git: Utiliser des tags</span>
Les tags que l'on va créer resteront sur le commit qui a reçu le tag.<br>
- Pour attacher un tag a un commit, il faut se déplacer sur le commit.<br>
   - **git checkout** *SHA-1*<br>
   - **git tag** *nom du tag* **-m"ceci est un commentaire"**<br>
 - Pour supprimer un tag il faut faire:
   - **git tag --delete** *tag*<br>
   - **git tag** *MON_SITE_V1* **-m"Première version de mon site"**<br>
 - Ensuite il faut retourner sur la branche master<br>
   - **git checkout master**<br>
- En faisant **git log**, on voit le tag MON_SITE_V1 sur le commit 2<br>
  - **git log**<br>
- on peut se déplacer sur le commit 2 en faisant **git checkout** *MON_SITE_V1*<br>
- Pour voir la liste des tags il faut exécuter **git tag**<br>
  - **git tag**<br>
<br>
# <span style="color:purple">github</span>
*Note personnelle: synology a un serveur github installé acessible par ssh et nfs (dossier partage github).*

Un gist permet de partager un morceau de code , par exemple pour échanger un problème.
Dans un gist on met du code et on peut récupérer ce gist comme un addon .js dans une page web en copiant/collant le mode embeded de github<br>

## <span style="color:blue">Créer et configurer un dépot git sous github</span>

Aller su github et faire **+** new repository
Voir la video

## <span style="color:blue">Explorer un depot git sous github</span>
Voir la video

## <span style="color:blue">Utiliser les issues</span>
Voir la video

##  <span style="color:blue">Découvrir les pull requests</span>
Voir la video
Pour faire un pull request, il faut dabord faire un fork du projet qui se retrouve copier dans notre github.

## <span style="color:blue">Cloner un dépot git</span>
- Pour cloner il faut utiliser la commande **git clone** *[remote] [folder name]*
- Aller sur la page d'accueil de notre github et se positionner sur le dépot à cloner
- soit on utilise les lignes de commandes, soit le mode boutton
  - Copier le lien https du site
- en ssh on va créé une clé publique et privé pour échanger sans mot de passe
- Sur le PC se positionner sur le dossier git. (pas le site web)
  - **cd '/media/olivier/Donnees/Documents/Formations/skilleos git/cours_git'**
  - **git clone** *lien https* *clone_mon_site_web*
  - **cd '/media/olivier/Donnees/Documents/Formations/skilleos git/cours_git/clone_mon_site_web'**
  - **git status**

On va créer une config locale pour dissocier les deux users
  - **git config user.name "clone"** 
- Ce nouveau user *clone* se situe uniquement dans le répertoire *clone_mon_site_web* alors que le global reste actif dans le répertoire mon_site_web
  - **git config --local --list**

## <span style="color:blue">Gérer les remotes</span>
pour voir le site distant, sur le PC faire **git remote -v**
  - **git remote -v**
  - **git remote show origin**

- Se repositionner sur le cours local
  - **cd '/media/olivier/Donnees/Documents/Formations/skilleos git/cours_git/mon_site_web**
  - **git remote -v** ne donne pas de résultats puisqu'il n'est que local
  - **git remote add origin** *https://github.com/oliboub/mon_site_web.git*
  - **git remote -v**
- A ce stade, on a deux répertoires locaux qui pointent sur le même dépot github, mais avec deux users différents.

## <span style="color:blue">Pousser ses commits sur le dépot distant</span>
- Pour pousser des fichiers il faut un token. Il convient de créer un token sur son profile github. ce token est à conserver et servira de mot de passe lors du transfert<br>
  - **cd '/media/olivier/Donnees/Documents/Formations/skilleos git/cours_git/mon_site_web'**<br>
  - **git push -u origin master** (origin étant le site remote, et master le local)<br>
  - Pour vérifier aller sur github et regarder le contenu<br>

- Avec cette commande les tags ne sont pas poussés. pour pousser les tags, il convient de faire:<br>
### <span style="color:blue">Pousser ses tags sur le dépot distant</span>
  - **git push origin** *tag*<br>
  - **git tag**<br>
  - **git push origin MON_SITE_V1**, pour pousser un seul tag<br>
  - **git push --tags**, pousse tous les tags<br>

## <span style="color:blue">Récupérer les modifications du dépôt distant</span>
la récupération des modifications se fait par
  - **git fetch remote** puis
  - **git pull** pour récupérer le master.
  - **git pull** intègre le **git fetch**
- Aller dans le répertoire clone
  - **cd '/media/olivier/Donnees/Documents/Formations/skilleos git/cours_git/clone_mon_site_web'**
  - **git pull**
  - **git log**

### <span style="color:blue">Corriger l'issue</span>

  - **cd '/media/olivier/Donnees/Documents/Formations/skilleos git/cours_git/clone_mon_site_web'**
  - **echo "# Mon site web: le cours git" >> README.md**
  - **git add README.md**
- Insérer le numéro d'issue dans le commentaire avec un #
  - **git commit -m"#1: Ajout du README.md"**
  - **git log** pour voir que l'auteur est bien "clone"
  - **git push**
  - Aller sur le site github et voir que vous avez un readme.
  - Cliquer sur le **#1** pour aller sur l'issue associée. Le commentaire a été ajouté automatiquement, donc on peut cloturer l'issue.
  - Cliquer sur **close  issue**
- mettre à jour le site mon_site_web
  - **cd '/media/olivier/Donnees/Documents/Formations/skilleos git/cours_git/mon_site_web'**
  - **git pull**
  - **git log**

***
# <span style="color:purple">Travailler en équipe</span>

## <span style="color:blue">Différents modèles d'organisation d'équipes
- Gestion centralisée 
- Gestion intégration
- Gestion dictateur
- Gestion dictateur avec lieutenants
  - Pour équipes de grandes tailles ou les lieutenants sont référents sur une partie du projet

## <span style="color:blue">Maitriser les modifications</span>
On utilise **git blame** *nom du fichier*<br>
- **git blame xxxxx.py**<br>
  - format de fichier:<br>
  SHA-1 - owner du commit - date et heure du commit - + ajout/- retrait - information<br>
  Si un petit chapeau se trouve devant le SHA-1, c'est que c'est ce commit qui a créé le fichier.<br>
- **git blame -L 10,20 fichier** permet d'afficher de la ligne 10 à la ligne 20<br>
- **git blame -L 10,+4 fichier** permet d'afficher à partir de la ligne 10 le nombre de ligne après le +<br>

## <span style="color:blue">Filtrer et ignorer les modifications</span>

La manière d'ignorer des fichiers ou des répertoires est basé sur un fichier local à la racine du projet.<br>
- le fichier est **.gitignore**<br>
  - **touch.gitignore**<br>
  Il convient de mettre dedans tous les fichiers ou répertorie à éviter.br>
  Ils n'aparaitront plus dans les propositions de **git status**<br>
  On peut mettre des fichiers avec *. ex *.txt<br>

## <span style="color:blue">Mettre de coté des fichiers et des modifications</span>
Par exemple si on a fait un checkout et qu'on ne veut pas perdre les nouveaux fichiers <br>
on utilise **git stash** après avoir fait des modifs locale.<br>
Ca permet de stocker les fichiers modifiés par rapport à la branche  dans un index caché <br>
- **git status** on voit les fichiers modifiés<br>
- **git stash save "message "**<br>
- **git status** on revient à la visio du pull<br>
on revient en version précédente:<br>
- **git checkout MON_SUITE_V3**<br>
on revient sur la branche master:<br>
- **git checkout master**<br>
on réapplique les modifs:<br>
- **git stash pop 0**<br>
- **git status**<br>

On peut faire plusieurs stash si on fait des modifs suivant le premier stash.<br>

pour récupérer:<br>
- **git stash pop 0**<br>
Pour voir les stash faire:<br>
- **git stash list**<br>
Pour voir le contenu, il faut faire:<br>
- **git stash show** *index*<br>

## <span style="color:blue">Faire un merge de fichier</span>

Pour faire un merge quand les fichiers ont des modificaiton sdes 2 cotés, il faut:<br>
- faire un **git pull**, le git pull dira qu'il y a conflit<br>
- Faire un **git stash** pour sauvegarder nos modificaitons locales<br>
- faire un **git pull**, qui récupérera les modifcations distantes en local et metra notre arbre à niveau<br>
- faire un **git statsh pop** qui va tenter de fair eun merge et qui mettra les différences dans les fichiers en conflit<br>
- modifier le(s) fichier(s) qui contient(nnent) les conflits afin de les résoudre<br>
Ensuite on reprend le processus normal<br>
  - **gitt add** *fichier(s)*<br>
  - **git commit** *-m"message"*<br>
  - **git push**<br>

## <span style="color:blue">Faire un merge de commit</span>

Marche pas correctement. mais méthide pas très pertinente, car trop de comit de merge et pas de valeur ajoutée pour le projet.<br>
Pour annuler un merge, il faut faire **git merge --abort**<br>

## <span style="color:blue">Faire un rebase de commit</span>

 - **git pull --rebase** permet de récupérer le dépot main/master et intégrer nos modifications commités en un seul coup. pas besoin de dissocier le merge.<br>

# <span style="color:purple">Le système de branches</span>

## <span style="color:blue">Comprendre le système de branche et créer une branche</span>

- **git branch** *BRANCH_A_MERGE* créé la branche mais reste sur le master
- **git branch** pour vérifier que la branche a bien été créée
- **git log** pour voir que la BRANCH_A_MERGE pointe sur la meme branche que le master
- **git checkout** *BRANCH_A_MERGE* pour basculer sur la nouvelle branche<br>
Faire ses modifications. Au premier git push, un message nous informe que la branche n'est que locale:<br>
  > fatal: The current branch BRANCH_A_MERGE has no upstream branch.<br>
To push the current branch and set the remote as upstream, use<br>

  >>    git push --set-upstream origin BRANCH_A_MERGE<br>

  >To have this happen automatically for branches without a tracking<br>
upstream, see 'push.autoSetupRemote' in 'git help config'.<br>
- **git push --set-upstream origin** *BRANCH_A_MERGE* lancer la commande proposée<br>
ensuite tous les commits seront standard<br>
- **git push**<br>

## <span style="color:blue">Récupérer une branche</span>
- **git branch** pour voir sur quelle branche on est
- **git pull** montre qu'il y  a une nouvelle branche sur le serveur distant
- **git branch** montre qu'on est toujours sur master
- **git branch -a** pour voir les branches du serveur
- **git checkout** *BRANCH_A_MERGE* pour se déplacer sur la branche BRANCH_A_MERGE
Faire les modifs , commit et ensuite
- **git push**

## <span style="color:blue">Copier un commit</span>
Permet par exemple de récupérer un commit qui corrige un bug dans le master et le copier dans la branche en cours.<br>
on va appliquer le premier commit de la branch_a_merge dans le master<br>
- **git checkout** *master*<br>
- **git log** *BRANCH_A_MERGE* pour voir les logs de cette branche<br>
- **git cherry-pick** *SHA1 du commit à récupérer*<br>

## <span style="color:blue">Faire un merge de branche</span>
Il faut se positionner sur la branche dans laquelle on veut faire le merge, donc le master dans notre cas.<br>
- **git branch** pour vérifier sur quelel branch on est.<br>
Si besoin faire un **git checkout** *master* pour se positionner sur la branche master<br>
- **git merge** *BRANCH_A_MERGE*<br>
Il peut y avoir des conflits:<br>
  >Fusion automatique de hello.html<br>
CONFLIT (contenu) : Conflit de fusion dans hello.html<br>
La fusion automatique a échoué ; réglez les conflits et validez le résultat.<br>
- Donc il faut éditer le fichier et corriger les conflits<br>
- **git add** *hello.html*
- **git commit -m"alignement des branches"**

## <span style="color:blue">Faire un rebase de branches</span>
le git rebase va déplacer le pointeur master sur le dernier comit de la nouvelle branche. et les deux pointeurs branche et master seront sur le cernier commit<br>
- **git pull**<br>
- **git checkout** *SHA-1 du commit souhaité*<br>
- **git switch -c** *BRANCH_A_REBASE* pour basculer et renommer la nouvelle branche<br>
Faire ses modifs et git add, git commit, **mais pas de git push**...<br>
- **git rebase master**
- Ensuite il convient de résoudre les conflits en éditant les fichiers impactés<br>
- **git add** *fichiers corrigés*<br>
- **git rebase --continue**<br>
Maintenant il convient de ramener master sur la dernière branche de BRANCH_A_REBASE<br>
- **git checkout** *master* Se positionner sur la branche master<br>
- **git merge** *BRANCH_A_REBASE*<br>
- **git log**<br>

## <span style="color:blue">Supprimer une branche</span>
Création d'une branche qu'on va supprimer par la suite<br>
- **git branch** *BRANCH_A_SUPPRIMER*<br>
- **git branch**<br>
- **git checkout** *BRANCH_A_SUPPRIMER*<br>
Faire ses modifs et git add, git commit et git push --set-upstream origin BRANCH_A_SUPPRIMER...<br>
Pour supprimerune branche on ne doit pas etre prositionné dessus<br>
- **git checkout** *master*<br>
- **git branch -d** *BRANCH_A_SUPPRIMER* supprimer que localement<br>
- **git branch**<br>
- **git branch -a**<br>
- **git push origin --delete** *BRANCH_A_SUPPRIMER*<br>
- **git branch -a**<br>

# <span style="color:purple">Annexes</span>

## <span style="color:blue">Utilisation de ssh ou https
 - **git remote set-url origin** *[URL_SSH OU URL_HTTPS]*
