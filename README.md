# allocco-landing

Lo que sirve hoy allocco.com.ar, vía GitHub Pages (`.github/workflows/pages.yml`
publica `public/` en cada push a `main`).

`public/` **no se edita a mano**: es el build del sitio, que vive en
[Hansen-Labs-Tech/allocco-web](https://github.com/Hansen-Labs-Tech/allocco-web).
Para actualizarlo, desde allocco-web:

```bash
npm run build && npm run verify
node scripts/publicar-github-pages.mjs ../allocco-landing/public
```

y commitear + pushear este repo. El script conserva `CNAME` y reemplaza los
301 de Cloudflare por páginas de redirección, porque Pages no lee `_redirects`.

Cuando el dominio pase a Cloudflare (ver `DEPLOY.md` en allocco-web), este repo
deja de hacer falta.

La landing "en construcción" original está en el historial (commit `bbbabb7`).
