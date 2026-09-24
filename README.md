# ANDREAS-SHOP — Registre Stock & Ventes

Application de gestion de stock et de ventes (Achats · Sorties · Stock au
P.A.M.P. · Ventes · Bénéfice), installable sur téléphone et utilisable
hors ligne une fois ouverte une première fois.

## Déployer sur GitHub Pages

1. Créez un nouveau dépôt sur [github.com](https://github.com) (par exemple
   `andreas-shop`), public.
2. Ajoutez tous les fichiers de ce dossier (`index.html`, `manifest.json`,
   `sw.js`, `icons/`) à la racine du dépôt :
   - Sur github.com : bouton **Add file → Upload files**, glissez tout le
     contenu de ce dossier (en conservant le sous-dossier `icons/`), puis
     **Commit changes**.
   - Ou en ligne de commande :
     ```bash
     git init
     git add .
     git commit -m "ANDREAS-SHOP"
     git branch -M main
     git remote add origin https://github.com/VOTRE-COMPTE/andreas-shop.git
     git push -u origin main
     ```
3. Dans le dépôt : **Settings → Pages**.
4. Sous **Build and deployment → Source**, choisissez **Deploy from a
   branch**.
5. Sous **Branch**, choisissez `main` et le dossier `/ (root)`, puis
   **Save**.
6. Au bout d'une à deux minutes, votre application est en ligne à l'adresse
   `https://VOTRE-COMPTE.github.io/andreas-shop/`.

## Installer sur un téléphone

Ouvrez l'adresse ci-dessus dans le navigateur du téléphone (avec internet,
la première fois), puis :

- **iPhone (Safari)** : bouton Partager → **Sur l'écran d'accueil**.
- **Android (Chrome)** : menu ⋮ → **Installer l'application** (ou
  **Ajouter à l'écran d'accueil**).

Une icône ANDREAS-SHOP apparaît sur l'écran d'accueil. Après cette première
ouverture, l'application fonctionne hors ligne grâce au service worker
(`sw.js`), qui met en cache les fichiers de l'application.

## Mettre à jour l'application

Après toute modification de `index.html`, changez la valeur de
`CACHE_NAME` en haut de `sw.js` (par exemple `andreas-shop-v2`) avant de
publier, afin que les téléphones qui ont déjà installé l'application
récupèrent bien la nouvelle version au lieu de garder l'ancienne en cache.

## Données

Toutes les données (articles, achats, sorties, ventes) sont stockées
uniquement dans le navigateur de chaque appareil (`localStorage`). Rien
n'est envoyé à un serveur : ouvrir l'application sur un autre appareil
donne un stock vide, indépendant des autres appareils.
