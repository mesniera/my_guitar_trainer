# Guide Cloud Build - Sans Mac

## Prérequis
- Compte GitHub (gratuit)
- Compte Apple Developer (99€/an)
- Compte Codemagic (gratuit)

## Étape 1 : Pousser code sur GitHub

```bash
cd guitar-trainer-pro

# Initialiser git si pas déjà fait
git init

# Créer .gitignore
echo "node_modules/" > .gitignore
echo "ios/App/Pods/" >> .gitignore
echo ".DS_Store" >> .gitignore

# Commit initial
git add .
git commit -m "Initial commit - Guitar Trainer Pro"

# Créer repo sur GitHub.com
# Puis lier :
git remote add origin https://github.com/VOTRE-USERNAME/guitar-trainer-pro.git
git push -u origin main
```

## Étape 2 : Configurer Codemagic

1. Aller sur https://codemagic.io/signup
2. Sign up avec GitHub
3. Autoriser accès à vos repos
4. Sélectionner "guitar-trainer-pro"

## Étape 3 : Configuration build iOS

Dans Codemagic, créer fichier `codemagic.yaml` :

```yaml
workflows:
  ios-release:
    name: iOS Release Build
    max_build_duration: 60
    environment:
      ios_signing:
        distribution_type: app_store
        bundle_identifier: com.yourname.guitartrainer
      vars:
        XCODE_WORKSPACE: "ios/App/App.xcworkspace"
        XCODE_SCHEME: "App"
      node: 18
    scripts:
      - name: Install dependencies
        script: |
          npm install
          npm install -g @capacitor/cli
      - name: Capacitor sync
        script: |
          npx cap sync ios
      - name: Build iOS
        script: |
          xcode-project build-ipa \
            --workspace "$XCODE_WORKSPACE" \
            --scheme "$XCODE_SCHEME"
    artifacts:
      - build/ios/ipa/*.ipa
    publishing:
      app_store_connect:
        api_key: $APP_STORE_CONNECT_KEY_ID
        key_id: $APP_STORE_CONNECT_KEY_IDENTIFIER
        issuer_id: $APP_STORE_CONNECT_ISSUER_ID
```

## Étape 4 : Certificats iOS (Important!)

**Option A : Auto-gestion par Codemagic**
1. Dans Codemagic → Settings → Code signing
2. Connecter Apple Developer account
3. Codemagic génère certificats automatiquement ✅

**Option B : Manuellement**
1. Aller sur https://developer.apple.com/account/resources/certificates
2. Créer iOS Distribution certificate
3. Créer Provisioning Profile
4. Télécharger les deux
5. Upload dans Codemagic settings

## Étape 5 : Lancer le build

1. Dans Codemagic, cliquer "Start new build"
2. Sélectionner branche "main"
3. Workflow "ios-release"
4. Cliquer "Start build"

⏱️ Attendre 15-30 min (compilation)

## Étape 6 : Récupérer .ipa

1. Build terminé ✅
2. Télécharger le fichier .ipa dans "Artifacts"
3. Ce fichier = votre app compilée pour iOS

## Étape 7 : Upload App Store Connect

**Option 1 : Via Transporter (app macOS)**
⚠️ Nécessite Mac

**Option 2 : Via Codemagic auto-publish**
✅ Configuré dans codemagic.yaml ci-dessus
L'app est automatiquement envoyée à App Store Connect

**Option 3 : Via Web (nouveau!)**
1. Aller sur https://appstoreconnect.apple.com
2. My Apps → Votre app → TestFlight
3. Build peut être uploadé via Transporter web (beta)

## Résumé coûts

- GitHub : Gratuit
- Codemagic : Gratuit (500 min/mois)
- Apple Developer : 99€/an
- **Total : 99€**

## Mises à jour futures

Pour chaque nouvelle version :
1. Modifier code localement
2. `git push origin main`
3. Codemagic rebuild automatiquement
4. Download nouvelle .ipa
5. Upload App Store

**Temps total : 15 min de votre part**
```
