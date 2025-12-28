# Guide d'installation - Guitar Trainer Pro PWA 📱

## Installation sur iOS (iPhone/iPad)

1. **Ouvrez Safari** (important : utilisez Safari, pas Chrome)
2. Naviguez vers l'URL de l'application
3. Appuyez sur le bouton **Partager** (icône avec flèche vers le haut) en bas de l'écran
4. Faites défiler et appuyez sur **"Sur l'écran d'accueil"**
5. Donnez un nom à l'application (ex: "Guitar Trainer")
6. Appuyez sur **"Ajouter"**
7. L'icône apparaît sur votre écran d'accueil !

### Utilisation
- Ouvrez l'app depuis l'écran d'accueil
- Elle s'ouvre en plein écran comme une vraie app
- Fonctionne hors ligne après la première utilisation

---

## Installation sur Android

### Méthode 1 : Chrome (recommandé)
1. **Ouvrez Chrome**
2. Naviguez vers l'URL de l'application
3. Une bannière apparaît : **"Ajouter Guitar Trainer à l'écran d'accueil"**
4. Appuyez sur **"Installer"** ou **"Ajouter"**
5. L'icône apparaît sur votre écran d'accueil !

### Méthode 2 : Menu manuel
1. Ouvrez Chrome et naviguez vers l'application
2. Appuyez sur le menu ⋮ (trois points) en haut à droite
3. Sélectionnez **"Ajouter à l'écran d'accueil"** ou **"Installer l'application"**
4. Confirmez l'installation
5. L'app est installée !

### Utilisation
- Lancez l'app depuis l'écran d'accueil ou le tiroir d'applications
- Fonctionne en plein écran
- Fonctionne hors ligne

---

## Hébergement de l'application

Pour que votre PWA soit installable, vous devez l'héberger sur un serveur HTTPS. Voici quelques options gratuites :

### Option 1 : GitHub Pages (Gratuit, facile)
1. Créez un compte GitHub
2. Créez un nouveau repository
3. Uploadez tous les fichiers (index.html, manifest.json, service-worker.js, icons)
4. Allez dans Settings → Pages
5. Activez GitHub Pages
6. Votre URL sera : `https://votre-username.github.io/guitar-trainer-pro/`

### Option 2 : Netlify (Gratuit, très facile)
1. Créez un compte sur netlify.com
2. Glissez-déposez votre dossier `guitar-trainer-pro`
3. Netlify génère automatiquement une URL HTTPS
4. URL de type : `https://guitar-trainer-abc123.netlify.app`

### Option 3 : Vercel (Gratuit, rapide)
1. Créez un compte sur vercel.com
2. Importez votre projet
3. Deploy automatique
4. URL HTTPS fournie instantanément

### Option 4 : Firebase Hosting (Gratuit)
1. Compte Google nécessaire
2. Installez Firebase CLI
3. `firebase init hosting`
4. `firebase deploy`
5. URL : `https://votre-projet.web.app`

---

## Vérification de l'installation

Une fois hébergée sur HTTPS, testez :

### Sur mobile
1. Visitez l'URL
2. Vérifiez qu'une bannière d'installation apparaît
3. Installez et testez

### Outils de développement
- **Chrome DevTools** : Ouvrez l'application → F12 → Onglet "Application" → vérifiez Manifest et Service Worker
- **Lighthouse** : Audit PWA pour vérifier tous les critères

---

## Fonctionnalités PWA activées ✅

- ✅ **Installable** sur écran d'accueil
- ✅ **Fonctionne hors ligne** (après première visite)
- ✅ **Plein écran** (pas de barre d'adresse)
- ✅ **Icône personnalisée** avec design guitare
- ✅ **Thème sombre** natif
- ✅ **Wake Lock** (empêche mise en veille)
- ✅ **Accès microphone** (nécessite HTTPS)
- ✅ **Responsive** mobile et desktop

---

## Notes importantes

### HTTPS obligatoire
- Les PWA nécessitent HTTPS (sauf localhost pour le développement)
- GitHub Pages, Netlify, Vercel fournissent HTTPS automatiquement

### Permissions
- L'accès au microphone nécessite HTTPS
- L'utilisateur doit autoriser l'accès au microphone lors du premier lancement

### Compatibilité
- **iOS** : Safari 11.1+
- **Android** : Chrome 40+, Firefox, Edge
- **Desktop** : Chrome, Edge, Opera (Windows/Mac/Linux)

---

## Test en local (développement)

Pour tester localement avant déploiement :

```bash
# Avec Python
cd guitar-trainer-pro
python3 -m http.server 8000

# Puis ouvrez : http://localhost:8000
```

Note : En local (localhost), HTTPS n'est pas requis pour les PWA.

---

## Support

Si l'installation ne fonctionne pas :
1. Vérifiez que vous êtes sur HTTPS
2. Vérifiez que manifest.json et service-worker.js sont accessibles
3. Ouvrez les DevTools pour voir les erreurs
4. Essayez en navigation privée
5. Videz le cache du navigateur

Profitez de votre entraînement guitare ! 🎸
