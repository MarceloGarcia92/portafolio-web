# Desplegar el portafolio en Cloudflare Pages

Sitio: `index.html` estático (un solo archivo). Costo: **$0**, ancho de banda **ilimitado**, HTTPS y CDN global (300+ ubicaciones) incluidos.

> ⚠️ **Elige un método y quédate con él.** Cloudflare **no** permite cambiar de "Conectar con Git" a "Subida directa" (ni al revés) en el mismo proyecto. Si te equivocas, tendrías que crear un proyecto nuevo.

---

## Opción A — Integración con Git (RECOMENDADA: auto-deploy en cada `push`)

Ideal para ti porque tu portafolio vivirá en GitHub. Cada vez que actualices el `index.html` y hagas `push`, Cloudflare lo publica solo.

### 1. Sube el portafolio a un repo de GitHub
Crea un repo (ej. `MarceloGarcia92/portfolio`) con el `index.html` en la **raíz**. Desde esta carpeta:

```bash
cd portfolio-web
git init
git add index.html
git commit -m "Portafolio web"
git branch -M main
git remote add origin https://github.com/MarceloGarcia92/portfolio.git
git push -u origin main
```

### 2. Conecta el repo en Cloudflare
1. Entra a [dash.cloudflare.com](https://dash.cloudflare.com) (crea cuenta gratis si no tienes).
2. Menú lateral: **Workers & Pages** → **Create** → pestaña **Pages** → **Connect to Git**.
3. Autoriza GitHub y selecciona el repo `portfolio`.

### 3. Configura el build (sitio estático, sin build)
- **Framework preset:** `None`
- **Build command:** *(déjalo vacío)*
- **Build output directory:** `/`  *(la raíz, porque el index.html está ahí)*

### 4. **Save and Deploy**
En ~1 min tu sitio queda en `https://portfolio.pages.dev` (el subdominio usa el nombre del proyecto).

---

## Opción B — Subida directa (lo más rápido HOY, sin GitHub)

Si quieres verlo publicado en 2 minutos sin tocar Git todavía.

1. [dash.cloudflare.com](https://dash.cloudflare.com) → **Workers & Pages** → **Create** → pestaña **Pages** → **Upload assets**.
2. Nombre del proyecto: `portfolio` (define tu subdominio `portfolio.pages.dev`).
3. **Arrastra la carpeta `portfolio-web`** (o solo el `index.html`) a la zona de subida.
4. **Deploy site**. Listo.

> Para actualizar el sitio, vuelves a subir los archivos manualmente (no hay auto-deploy en este método).

---

## Después de desplegar

- **Subdominio gratis:** `https://portfolio.pages.dev` con HTTPS automático. No necesitas más para empezar.
- **Dominio propio (opcional, a futuro):** dentro del proyecto → **Custom domains** → **Set up a domain** → sigues las instrucciones DNS. Gratis, sin límite de dominios.

## Checklist antes de compartir el enlace

Tu `index.html` enlaza a estos repos con "Ver código →". Deben existir en tu GitHub o darán **404**:

- `MarceloGarcia92/hand-pose-cnn`
- `MarceloGarcia92/pleural-effusion-cnn`
- `MarceloGarcia92/eo-ml-pipeline`
- `MarceloGarcia92/medbot-rasa`
- `MarceloGarcia92/meal-planner`

Puedes desplegar igual y ajustar los enlaces después (el sitio funciona; solo esos botones fallarían hasta que subas los repos).
