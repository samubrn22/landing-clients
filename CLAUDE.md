# Landing Clients — Pages poubelles

## Projet
Hub de landing pages pour les clients Kokoro.
Chaque client = une ou plusieurs landing pages dans `src/pages/`.

## Stack
- **Astro** (site statique)
- HTML/CSS/JS par page (CSS scopé, pas de framework)
- GSAP pour les animations scroll
- Déploiement : Hostinger Git auto-deploy

## Structure
```
src/
  pages/
    index.astro           ← formation-agent-ia.com/ (page d'accueil)
    onemice.astro         ← formation-agent-ia.com/onemice
    [client].astro        ← formation-agent-ia.com/[client]
```

## Déploiement
- Domaine : `formation-agent-ia.com` sur Hostinger
- Méthode : Git auto-deploy depuis `samubrn22/landing-clients`, branche `main`
- **Hostinger sert `public_html/` = racine du repo.** Les fichiers buildés doivent être à la racine.
- `npm run build` = `astro build` + copie automatique de `dist/*` à la racine

## Workflow deploy
```
npm run build          # Build Astro + copie dist/ à la racine
git add .
git commit -m "..."
git push origin main   # Auto-deploy Hostinger via webhook
```

## Conventions
- Une landing client = un fichier Astro dans `src/pages/`
- Design autonome par page (CSS/JS scopé)
- Pages avec design similaire → layout partagé. Design différent → fichier standalone.
