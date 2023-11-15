
- [initialisation d'un repo git](#initialisation-dun-repo-git)
- [Branche](#branche)
- [Release](#release)


# initialisation d'un repo git
**create a new repository with first commit**
```bash
git init
git add .
git commit -m "first commit"
git remote add origin <lien https>
git push -u origin main
```

**push an existing repository**
```bash
git remote add origin <lien https>
git branch -M main
git push -u origin main
```

# Branche

> En Git, une branche est une ligne de développement indépendante qui permet de travailler sur des fonctionnalités, des correctifs ou des améliorations sans affecter directement la branche principale (généralement appelée ``main`` ou ``master``). Les branches facilitent le développement collaboratif, la gestion des versions et l'expérimentation de nouvelles fonctionnalités. Elles permettent à plusieurs développeurs de travailler simultanément sur des aspects différents du projet sans conflits constants, et une fois les changements testés et validés, ils peuvent être fusionnés avec la branche principale. Les branches sont utiles pour isoler le travail en cours, explorer de nouvelles idées, et maintenir un historique de développement organisé.


**Pour créer une nouvelle branche:**
```bash
git branch <nom_de_la_branche>
```

**Pour créer et se déplacer simultanément sur la nouvelle branche:**
```bash
git checkout -b <nom_de_la_branche> 
```
(ou git switch -c <nom_de_la_branche> depuis Git version 2.23)


**Pour se déplacer sur une branche existante:** 
```bash
git checkout <nom_de_la_branche>
```
(ou git switch <nom_de_la_branche> depuis Git version 2.23)


**Pour voir la liste des branches dans le dépôt local:** 
```bash
git branch
```

**Pour voir les branches distantes (sur le serveur):**
```bash
git branch -r
```

**Pour supprimer une branche locale:**
```bash
git branch -d <nom_de_la_branche>
```


**Pour supprimer une branche distante:**
```bash
git push origin --delete <nom_de_la_branche>
```

**Pour fusionner une branche dans la branche active:**
```bash
git merge <nom_de_la_branche>
```
Utiliser `--no-ff` pour forcer une fusion même pour les fusions rapides: 
```bash
git merge --no-ff <nom_de_la_branche>
```

**Pousser et Tirer des Branches sur GitHub**

Push une nouvelle branche sur GitHub: 
```bash
git push origin <nom_de_la_branche>
```
Pull les changements de la branche distante:
```bash
git pull origin <nom_de_la_branche>
```

**Résolution de Conflits:**

Lorsqu'il y a des conflits lors de la fusion, Git vous demandera de les résoudre manuellement avant de finaliser la fusion.

# Release

> Une release (version) dans le contexte de développement logiciel est une version spécifique d'un programme ou d'une application à un moment donné. Elle est généralement identifiée par un numéro de version, tel que "v1.0" ou "1.2.3". Les releases sont utilisées pour marquer des étapes importantes du développement et sont souvent associées à des fonctionnalités nouvelles, des corrections de bugs ou d'autres améliorations. Les releases permettent aux développeurs de suivre et de documenter les différentes itérations de leur logiciel, facilitant ainsi le suivi des changements et la gestion des versions. Elles sont également utilisées pour déployer des versions spécifiques dans des environnements de production ou pour partager des versions stables avec les utilisateurs finaux.

La gestion des releases dans Git est généralement associée à la création de tags pour marquer des versions spécifiques de votre code. Voici un processus général pour créer une release sur Git:

**Assurez-vous d'être sur la branche principale (par exemple, main ou master):**
```bash
git checkout main
```
**Assurez-vous que votre branche locale est à jour avec la branche distante:**
```bash
git pull origin main
```
**Créez une nouvelle branche pour la release (si vous préférez):**
```bash
git checkout -b release/vX.X.X
```
Ici, X.X.X représente le numéro de version de votre release.

**Effectuez les tâches nécessaires pour la release:**

Mettez à jour le numéro de version dans votre code.
Effectuez des tests pour vous assurer que tout fonctionne correctement.

**Validez et ajoutez les modifications:**
```bash
git add .
git commit -m "Prépare la release vX.X.X"
```
**Créez un tag pour la release:**
```bash
git tag -a vX.X.X -m "Release vX.X.X"
```
Assurez-vous de remplacer X.X.X par le numéro de version réel.

**Poussez le tag vers le dépôt distant (GitHub):**
```bash
git push origin vX.X.X
```

**Fusionnez la branche de release avec la branche principale (si vous avez créé une branche de release):**
```bash
git checkout main
git merge release/vX.X.X
```

**Poussez les modifications fusionnées vers le dépôt distant:**
```bash
git push origin main
```

**Supprimez la branche de release (si vous avez créé une branche spécifique pour la release):**
```bash
git branch -d release/vX.X.X
```

Cela crée une release sur Git en marquant une version spécifique avec un tag. Les tags sont utiles pour suivre les versions de votre logiciel et peuvent être référencés dans votre historique de commits. N'oubliez pas de personnaliser ces étapes en fonction de votre flux de travail et de vos préférences.