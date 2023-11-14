
- [initialisation d'un repo git](#initialisation-dun-repo-git)
  - [create a new repository with first commit](#create-a-new-repository-with-first-commit)
  - [push an existing repository](#push-an-existing-repository)
- [Branche](#branche)
  - [Création de Branches et se déplacer](#création-de-branches-et-se-déplacer)
  - [Liste des Branches](#liste-des-branches)
  - [Suppression de Branches](#suppression-de-branches)
  - [Fusion (Merge) de Branches](#fusion-merge-de-branches)
  - [Pousser et Tirer des Branches sur GitHub](#pousser-et-tirer-des-branches-sur-github)
  - [Résolution de Conflits :](#résolution-de-conflits-)


# initialisation d'un repo git
## create a new repository with first commit
```bash
git init
git add .
git commit -m "first commit"
git remote add origin <lien https>
git push -u origin main
```

## push an existing repository
```bash
git remote add origin <lien https>
git branch -M main
git push -u origin main
```

# Branche
Une branche en Git est une référence mobile pointant vers un commit spécifique.
La branche par défaut s'appelle généralement ``main`` ou ``master``.
## Création de Branches et se déplacer

Pour créer une nouvelle branche : 
```bash
git branch <nom_de_la_branche>
```

Pour créer et se déplacer simultanément sur la nouvelle branche : 
```bash
git checkout -b <nom_de_la_branche> 
```
(ou git switch -c <nom_de_la_branche> depuis Git version 2.23)


Pour se déplacer sur une branche existante : 
```bash
git checkout <nom_de_la_branche>
```
(ou git switch <nom_de_la_branche> depuis Git version 2.23)


## Liste des Branches

Pour voir la liste des branches dans le dépôt local : 
```bash
git branch
```

Pour voir les branches distantes (sur le serveur) : 
```bash
git branch -r
```

## Suppression de Branches

Pour supprimer une branche locale : 
```bash
git branch -d <nom_de_la_branche>
```


Pour supprimer une branche distante :
```bash
git push origin --delete <nom_de_la_branche>
```

## Fusion (Merge) de Branches

Pour fusionner une branche dans la branche active : 
```bash
git merge <nom_de_la_branche>
```
Utiliser `--no-ff` pour forcer une fusion même pour les fusions rapides : 
```bash
git merge --no-ff <nom_de_la_branche>
```

## Pousser et Tirer des Branches sur GitHub

Pour pousser une nouvelle branche sur GitHub : 
```bash
git push origin <nom_de_la_branche>
```
Pour tirer (pull) les changements de la branche distante :
```bash
git pull origin <nom_de_la_branche>
```

## Résolution de Conflits :

Lorsqu'il y a des conflits lors de la fusion, Git vous demandera de les résoudre manuellement avant de finaliser la fusion.