# Fiche mémo — Commandes essentielles WSL & Git

## 📁 Navigation

### 1. `pwd` — Afficher le dossier courant
```bash
pwd
# Résultat : /home/user/projet
```

### 2. `cd nom_dossier` — Se déplacer dans un dossier
```bash
cd projet
cd Documents/code
```

### 3. `cd ..` — Remonter d'un niveau
```bash
cd ..
# Depuis /home/user/projet -> /home/user
```

### 4. `ls` — Lister le contenu d'un dossier
```bash
ls
# affiche : README.md  src  package.json
```

### 5. `ls -la` — Lister avec détails et fichiers cachés
```bash
ls -la
# affiche permissions, propriétaire, taille, date, fichiers cachés (.git, .env...)
```

---

## 🌳 Arborescence

### 6. `tree` — Afficher la structure en arbre
```bash
sudo apt install tree   # installation si nécessaire
tree
# affiche l'arborescence complète du dossier courant
tree -L 2                # limite l'affichage à 2 niveaux de profondeur
```

### 7. `mkdir nom_dossier` — Créer un dossier
```bash
mkdir mon-projet
mkdir -p src/components   # crée les dossiers parents si besoin
```

### 8. `rmdir nom_dossier` — Supprimer un dossier vide
```bash
rmdir dossier-vide
```

### 9. `rm -r nom_dossier` — Supprimer un dossier et son contenu
```bash
rm -r ancien-projet
rm -rf ancien-projet   # force la suppression sans confirmation (attention !)
```

### 10. `find . -name "fichier"` — Rechercher un fichier
```bash
find . -name "*.js"        # tous les fichiers .js dans le dossier courant
find . -name "config.json" # cherche un fichier précis
```

---

## 🔐 Droits et permissions

### 11. `chmod 755 fichier` — Modifier les permissions
```bash
chmod 755 script.sh
# 7 = propriétaire (lecture+écriture+exécution)
# 5 = groupe (lecture+exécution)
# 5 = autres (lecture+exécution)
```

### 12. `chmod +x script.sh` — Rendre un fichier exécutable
```bash
chmod +x deploy.sh
./deploy.sh   # peut maintenant être exécuté directement
```

### 13. `chown user:group fichier` — Changer le propriétaire
```bash
sudo chown moi:moi fichier.txt
sudo chown -R moi:moi mon-dossier/   # récursif sur tout un dossier
```

### 14. `ls -l` — Voir les permissions détaillées
```bash
ls -l
# -rwxr-xr-- 1 user group 1024 Sep 8 10:00 script.sh
# rwx = propriétaire, r-x = groupe, r-- = autres
```

### 15. `sudo commande` — Exécuter avec droits administrateur
```bash
sudo apt update
sudo apt install git
```

---

## 🔧 Git

### 16. `git init` — Initialiser un dépôt Git
```bash
git init
# crée un dossier .git caché, démarre le suivi de version
```

### 17. `git status` — Voir l'état des fichiers
```bash
git status
# affiche : fichiers modifiés, ajoutés, non suivis
```

### 18. `git add .` — Ajouter les fichiers au prochain commit
```bash
git add .              # ajoute tous les fichiers modifiés
git add fichier.txt    # ajoute un seul fichier
```

### 19. `git commit -m "message"` — Enregistrer les changements
```bash
git commit -m "Ajout de la page de connexion"
```

### 20. `git log --oneline` — Voir l'historique condensé
```bash
git log --oneline
# a1b2c3d Ajout de la page de connexion
# e4f5g6h Commit initial
```

---

## 💡 Bonus : combos utiles

```bash
git add . && git commit -m "message"     # ajouter et committer en une ligne
cd .. && ls                               # remonter et lister
mkdir projet && cd projet                 # créer et entrer dans le dossier
```
