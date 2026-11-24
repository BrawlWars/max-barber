# Réservation coupe (type Planity)

## 1. Firebase (gratuit)
1. https://console.firebase.google.com → **Ajouter un projet**.
2. **Build → Firestore Database → Créer** (mode test, région europe-west).
3. **Paramètres du projet → Vos applications → </> (Web)** → copie l'objet `firebaseConfig` dans `index.html` (`FIREBASE_CONFIG`).
4. Firestore → **Règles** : colle ceci puis Publier :
```
rules_version = '2';
service cloud.firestore {
  match /databases/{db}/documents {
    match /{document=**} { allow read, write: if true; }
  }
}
```
5. Dans `index.html`, change `ADMIN_PIN` (code du barbier).

## 2. GitHub Pages
1. Crée un repo GitHub, ajoute `index.html` (et ce README).
2. **Settings → Pages → Deploy from a branch → main / (root)**.
3. Le site sera sur `https://TON-PSEUDO.github.io/NOM-DU-REPO/`.

## Utilisation
- Clients : ouvrent le lien et réservent.
- Barbier : lien « Espace barbier » en bas de page, code → ouvre des créneaux et voit les RDV.
