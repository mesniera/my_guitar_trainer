# 📤 Guide d'upload sur GitHub

## 🎯 Vue d'ensemble

Ce guide vous explique comment uploader **Guitar Trainer Pro v1.1.0** sur GitHub et activer GitHub Pages pour le rendre accessible en ligne.

---

## 📋 Fichiers à uploader

Tous ces fichiers sont dans le dossier `guitar-trainer-pro` :

### **Fichiers essentiels :**
✅ `index.html` - Application principale (100 Ko)
✅ `manifest.json` - Configuration PWA
✅ `service-worker.js` - Mode hors ligne
✅ `README.md` - Documentation
✅ `.gitignore` - Fichiers à ignorer

### **Icônes PWA :**
✅ `icon-192.png` - Icône 192×192
✅ `icon-512.png` - Icône 512×512
✅ `icon.svg` - Icône vectorielle

### **Politique de confidentialité :**
✅ `privacy.html` - Page de politique (pour App Store)
✅ `PRIVACY_POLICY.md` - Version Markdown

### **Documentation :**
✅ `CHANGELOG.md` - Historique des versions
✅ `INSTALLATION_PWA.md` - Guide d'installation
✅ `APP_STORE_DESCRIPTION.md` - Description App Store
✅ `CLOUD_BUILD_GUIDE.md` - Guide build iOS
✅ `FIX_SERVICE_WORKER_ERROR.md` - Dépannage

### **Configuration mobile (optionnel pour iOS) :**
✅ `capacitor.config.json` - Config Capacitor
✅ `ios-permissions-template.plist` - Permissions iOS

---

## 🚀 Méthode 1 : GitHub.com (Interface web - Recommandé)

### **Étape 1 : Créer un compte GitHub**
1. Aller sur [github.com](https://github.com)
2. Cliquer **"Sign up"** (si pas encore de compte)
3. Gratuit à 100% ✅

### **Étape 2 : Créer un nouveau repository**
1. Cliquer le **"+"** en haut à droite
2. Sélectionner **"New repository"**
3. Remplir :
   - **Repository name :** `guitar-trainer-pro`
   - **Description :** "🎸 Guitar training app with real-time audio detection"
   - **Public** ✅ (obligatoire pour GitHub Pages gratuit)
   - ❌ Ne PAS cocher "Add a README file"
4. Cliquer **"Create repository"**

### **Étape 3 : Upload des fichiers**

**Option A : Glisser-déposer (⭐ Plus simple)**
1. Sur la page du repo, cliquer **"uploading an existing file"**
2. **Glisser-déposer TOUS les fichiers** du dossier `guitar-trainer-pro`
3. Attendre l'upload (barre de progression)
4. Message de commit : `Initial commit - Guitar Trainer Pro v1.1.0`
5. Cliquer **"Commit changes"**

**Option B : Fichier par fichier**
1. Cliquer **"Add file"** → **"Create new file"**
2. Nom : `index.html`
3. Copier-coller le contenu
4. Répéter pour chaque fichier

### **Étape 4 : Activer GitHub Pages**
1. Dans votre repo, cliquer **"Settings"** (⚙️)
2. Sidebar gauche : **"Pages"** (dans "Code and automation")
3. **Source :** "Deploy from a branch"
4. **Branch :** 
   - Premier menu : **"main"**
   - Deuxième menu : **"/ (root)"**
5. Cliquer **"Save"**
6. ⏳ Attendre 1-2 minutes

### **Étape 5 : Accéder à votre app**
Après 1-2 minutes, votre app sera accessible à :
```
https://VOTRE-USERNAME.github.io/guitar-trainer-pro/
```

🎉 **C'est en ligne !**

---

## 🖥️ Méthode 2 : Git en ligne de commande

### **Installation Git (une seule fois)**

**Windows :**
1. Télécharger : [git-scm.com/download/win](https://git-scm.com/download/win)
2. Installer (options par défaut)
3. Ouvrir **Git Bash**

**Mac :**
```bash
# Git est déjà installé
git --version
```

**Linux :**
```bash
sudo apt-get install git  # Ubuntu/Debian
```

### **Configuration Git (une seule fois)**
```bash
git config --global user.name "Votre Nom"
git config --global user.email "votre-email@example.com"
```

### **Upload sur GitHub**

**1. Naviguer vers le dossier**
```bash
cd /chemin/vers/guitar-trainer-pro

# Vérifier qu'on est au bon endroit
ls
# Vous devriez voir : index.html, manifest.json, etc.
```

**2. Initialiser Git**
```bash
# Initialiser le repo local
git init

# Ajouter tous les fichiers
git add .

# Créer le premier commit
git commit -m "Initial commit - Guitar Trainer Pro v1.1.0"
```

**3. Lier à GitHub**
```bash
# Créer d'abord le repo sur GitHub.com
# Puis lier le repo local au repo GitHub
git remote add origin https://github.com/VOTRE-USERNAME/guitar-trainer-pro.git

# Renommer la branche en "main"
git branch -M main

# Envoyer les fichiers
git push -u origin main
```

**Si demande login :**
- Username : votre username GitHub
- Password : **Personal Access Token** (pas votre mot de passe)

### **Créer un Personal Access Token**
1. GitHub.com → Profil → **Settings**
2. Sidebar → **Developer settings** (tout en bas)
3. **Personal access tokens** → **Tokens (classic)**
4. **Generate new token (classic)**
5. Nom : "Git Push Token"
6. Expiration : 90 days
7. Cocher : ☑️ **repo** (toute la section)
8. **Generate token**
9. **COPIER LE TOKEN** (vous ne le reverrez plus !)
10. Utiliser ce token comme "password" dans Git

**4. Activer GitHub Pages**
Suivre l'Étape 4 de la Méthode 1 (via l'interface web)

---

## 🔄 Méthode 3 : GitHub Desktop (Interface graphique)

### **Installation**
1. Télécharger : [desktop.github.com](https://desktop.github.com)
2. Installer et se connecter

### **Upload**
1. **File** → **Add local repository**
2. Choisir le dossier `guitar-trainer-pro`
3. Si "not a git repository" → **Create repository**
4. **Commit to main** : "Initial commit - Guitar Trainer Pro v1.1.0"
5. **Publish repository** (en haut)
6. Décocher "Keep this code private"
7. **Publish**

Ensuite activer GitHub Pages via l'interface web (Méthode 1, Étape 4).

---

## ✅ Vérification

### **Vérifier l'upload :**
1. Aller sur `github.com/VOTRE-USERNAME/guitar-trainer-pro`
2. Vous devriez voir tous vos fichiers
3. Le README.md s'affiche en bas

### **Vérifier GitHub Pages :**
1. Settings → Pages
2. Message vert : "Your site is live at https://..."
3. Cliquer sur le lien
4. Votre app devrait s'afficher ! 🎉

---

## 🎯 URL finale

Votre application sera accessible à :
```
https://VOTRE-USERNAME.github.io/guitar-trainer-pro/
```

**Politique de confidentialité :**
```
https://VOTRE-USERNAME.github.io/guitar-trainer-pro/privacy.html
```
→ À utiliser dans App Store Connect

---

## 🔄 Mettre à jour l'app plus tard

### **Via interface web :**
1. Aller sur le fichier (ex: `index.html`)
2. Cliquer l'icône crayon (Edit)
3. Modifier le contenu
4. **Commit changes**

### **Via Git :**
```bash
# Modifier vos fichiers localement
# Puis :
git add .
git commit -m "Update: description des changements"
git push
```

GitHub Pages se met à jour automatiquement (1-2 minutes).

---

## 📱 Prochaines étapes après GitHub

Une fois votre app sur GitHub :

### **1. Tester sur mobile**
- Ouvrir l'URL sur votre smartphone
- Safari (iOS) : Partager → Ajouter à l'écran d'accueil
- Chrome (Android) : Menu → Ajouter à l'écran d'accueil
- ✅ L'app fonctionne comme une app native !

### **2. Build iOS (optionnel)**
- Suivre le guide : `CLOUD_BUILD_GUIDE.md`
- Utiliser Codemagic pour build sans Mac
- Publier sur l'App Store

### **3. Partager**
- Partager l'URL avec vos amis
- Poster sur Reddit (r/guitar, r/guitarlessons)
- Demander des retours

---

## ❓ Problèmes courants

### **"Permission denied" lors du push**
Solution : Utiliser un Personal Access Token (voir plus haut)

### **"Updates were rejected"**
Solution : Forcer le push (premier upload)
```bash
git push -u origin main --force
```

### **Pages ne s'affiche pas**
Solutions :
- Attendre 2-5 minutes (propagation)
- Vérifier Settings → Pages → Branch = "main" et "/ (root)"
- Vérifier que le repo est **Public**

### **Service Worker erreur 404**
Normal sur GitHub Pages au premier chargement. Recharger la page.

---

## 🎉 Récapitulatif

1. ✅ Créer compte GitHub
2. ✅ Créer repo `guitar-trainer-pro` (Public)
3. ✅ Upload tous les fichiers
4. ✅ Activer GitHub Pages (Settings → Pages)
5. ✅ Attendre 1-2 minutes
6. ✅ Accéder à l'URL : `https://USERNAME.github.io/guitar-trainer-pro/`

**Temps total : 10-15 minutes** ⚡

---

## 📞 Support

Si problème, consulter :
- [GitHub Docs](https://docs.github.com)
- [GitHub Pages Guide](https://pages.github.com)

Bon upload ! 🚀🎸
