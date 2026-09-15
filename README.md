# Spanglish · Academia de Inglés

Web oficial de **Spanglish**, academia de inglés en **Morata de Tajuña (Madrid)**.

Landing de una sola página, estática, sin frameworks ni dependencias: HTML5 semántico,
CSS3 y un pequeño script en JavaScript vanilla. Preparada para GitHub Pages.

---

## Estructura del proyecto

```
/
├── index.html                  Landing completa (una sola página)
├── css/
│   └── styles.css              Estilos, mobile-first
├── js/
│   └── main.js                 Menú móvil, sección activa y año del footer
├── assets/
│   ├── img/
│   │   ├── logo-spanglish.svg      Logo horizontal (provisional)
│   │   ├── isotipo-spanglish.svg   Isotipo usado en la cabecera
│   │   └── og-image.svg            Imagen para redes sociales
│   └── icons/
│       └── favicon.svg
├── .github/workflows/deploy.yml   Despliegue a GitHub Pages
├── .nojekyll
├── .gitignore
└── README.md
```

---

## Cómo probar localmente

No hace falta compilar nada. Basta con abrir `index.html` en el navegador,
aunque se recomienda servirlo por HTTP para que rutas y metadatos se comporten igual que en producción:

```bash
# Opción 1 — Python
python -m http.server 8080

# Opción 2 — Node.js
npx serve .
```

Después, abrir <http://localhost:8080>.

En VS Code también puede usarse la extensión *Live Server*.

---

## Cómo trabajar en rama

```bash
git checkout main
git pull
git checkout -b feat/nombre-descriptivo

# ...cambios...

git add .
git commit -m "feat: descripción breve del cambio"
git push -u origin feat/nombre-descriptivo
```

## Cómo crear el Pull Request

Desde la web de GitHub: al subir la rama aparece el aviso *«Compare & pull request»*,
o bien desde <https://github.com/Juanda-ecaweb/spanglishmorata/pulls> → **New pull request**
(base: `main`, compare: la rama de trabajo).

Con GitHub CLI:

```bash
gh pr create --base main --head feat/spanglish-web-v1 --title "Web Spanglish v1" --body "Landing inicial"
gh pr view --web
```

## Cómo hacer merge

1. Revisar los cambios en la pestaña **Files changed** del PR.
2. Comprobar la vista previa local de la rama.
3. Pulsar **Merge pull request** → **Confirm merge**.
4. Borrar la rama cuando ya no se necesite (**Delete branch**).

> El merge a `main` es lo que dispara la publicación.

## Cómo activar GitHub Pages

1. Ir a **Settings → Pages** del repositorio.
2. En *Build and deployment* → *Source*, seleccionar **GitHub Actions**.
3. No es necesario crear la rama `gh-pages`: el workflow publica directamente desde `main`.

## Cómo comprobar el deployment

1. Pestaña **Actions** → workflow *Deploy to GitHub Pages*.
2. Cuando el job termine en verde, la URL aparece en el paso *Deploy to GitHub Pages*
   y en **Settings → Pages**.
3. URL prevista: <https://juanda-ecaweb.github.io/spanglishmorata/>

---

## Datos pendientes de confirmar

- [ ] Logo definitivo en SVG/PNG (los actuales son una reconstrucción provisional).
- [ ] Foto de María (hoy se muestra un círculo con sus iniciales).
- [ ] URL real de Facebook.
- [ ] URL real de Instagram.
- [ ] Dirección exacta de la academia (para JSON-LD y mapa).
- [ ] Horarios de atención.
- [ ] Email de contacto (hoy no se muestra).
- [ ] Dominio propio definitivo (requiere `CNAME` y actualizar `canonical` y Open Graph).
- [ ] Exportar `og-image.svg` a PNG 1200×630 (algunas redes no leen SVG).

## Notas de contenido

- La web **no muestra precios** de forma deliberada; las tarifas se comunican por WhatsApp.
- No se atribuyen a la profesora titulaciones ni acreditaciones no confirmadas.
- El JSON-LD solo incluye datos verificados (localidad, provincia, teléfono).
