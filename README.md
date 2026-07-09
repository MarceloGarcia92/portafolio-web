# Portafolio web — Marcelo García C.

Sitio estático de un solo archivo (`index.html`). Sin dependencias, sin servidor, carga instantánea.

## Personalizar antes de publicar

En `index.html`, revisa/ajusta:
- Los enlaces a repos (`github.com/MarceloGarcia92/...`) — deben coincidir con los nombres reales que uses.
- Email de contacto y URL de LinkedIn.
- Textos de cada proyecto (problema / enfoque / resultado).

## Desplegar en GitHub Pages (gratis)

1. Crea un repo público, por ejemplo `MarceloGarcia92/portfolio`.
2. Sube `index.html` a la raíz.
3. En el repo: **Settings → Pages → Source: Deploy from a branch → `main` / root**.
4. Tu sitio queda en `https://MarceloGarcia92.github.io/portfolio/`.

> Truco: si nombras el repo `MarceloGarcia92.github.io`, el sitio vive en la raíz `https://MarceloGarcia92.github.io/`.

## Desplegar en Vercel (gratis, dominio propio fácil)

1. Entra a [vercel.com](https://vercel.com) con tu cuenta de GitHub.
2. **Add New → Project** e importa el repo (o arrastra la carpeta).
3. Framework preset: **Other**. Deploy.
4. Opcional: conecta un dominio propio en **Settings → Domains**.

## Probar en local

Abre `index.html` directamente en el navegador, o sirve la carpeta:

```bash
python3 -m http.server 8080   # http://localhost:8080
```
