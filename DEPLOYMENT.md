# 🚀 Guide de Déploiement - Kongo Parfum

## Déploiement Frontend sur Vercel

### Backend et Frontend séparés

Ce projet a 2 parties qui se déploient séparément :

### Frontend (Angular)

```bash
# Déployer juste le frontend
cd kongo-frontend
npm run build
# Puis uploader le dossier dist/ sur Vercel
```

**Configuration Vercel :**

- Build Command: `npm run build`
- Output Directory: `dist`
- Framework: Angular

### Backend (Node.js)

Déployez sur Heroku ou Render :

```bash
cd kongo-backend
# Créer un Procfile
echo "web: npm start" > Procfile

# Push sur Heroku
heroku create kongo-parfum-api
git subtree push --prefix kongo-backend heroku main
```

## Étapes de déploiement complètes

1. **Frontend sur Vercel**
   - URL : `https://kongo-parfum.vercel.app`

2. **Backend sur Heroku/Render**
   - URL : `https://kongo-parfum-api.herokuapp.com`

3. **Configuration API**
   - Mettez à jour `environment.ts` avec l'URL du backend

## Variables d'environnement Backend

```env
DATABASE_URL=postgresql://...
JWT_SECRET=votre_secret
STRIPE_KEY=sk_...
```

---

**Besoin d'aide ?** Consultez la [doc Vercel](https://vercel.com/docs) et [Heroku](https://devcenter.heroku.com/)
