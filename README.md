# Iglesia los almendros: página web

Página web estática de una sola página (un solo archivo `index.html`, sin instalar nada).
Muestra el título "Iglesia los almendros" y el versículo de Colosenses 3:23.

## Contenido del repositorio

```
/
├── index.html   ← la página completa (HTML + CSS + JavaScript)
└── README.md    ← este documento
```

Si agregas imágenes (por ejemplo una foto de portada), ponlas en una carpeta `imagenes/` y
llámalas desde `index.html` con una ruta relativa: `<img src="imagenes/portada.jpg" alt="...">`.

---

## 1. Subir la página a GitHub

### Opción A: desde el navegador (la más fácil, sin instalar nada)

1. Entra a <https://github.com> e inicia sesión (o crea una cuenta gratis).
2. Arriba a la derecha pulsa **+** → **New repository**.
3. Completa:
   - **Repository name:** `iglesia-los-almendros` (sin espacios ni tildes).
   - **Public** (necesario para usar GitHub Pages gratis).
   - Marca **Add a README file** solo si NO vas a subir este `README.md`.
4. Pulsa **Create repository**.
5. En el repositorio pulsa **Add file** → **Upload files**.
6. Arrastra `index.html` y `README.md`.
7. Abajo pulsa **Commit changes**.

### Opción B: desde la terminal con Git

```bash
# 1. Entra a la carpeta donde están index.html y README.md
cd ruta/a/tu/carpeta

# 2. Inicia el repositorio y guarda los archivos
git init
git add index.html README.md
git commit -m "Primera versión de la página"

# 3. Conéctalo con GitHub (crea antes el repositorio vacío en github.com)
git branch -M main
git remote add origin https://github.com/TU-USUARIO/iglesia-los-almendros.git
git push -u origin main
```

Cada vez que cambies algo: `git add .` → `git commit -m "Describe el cambio"` → `git push`.

---

## 2. Publicar con GitHub Pages (enlace público gratis)

1. En el repositorio entra a **Settings** (Configuración).
2. En el menú izquierdo pulsa **Pages**.
3. En **Build and deployment** → **Source** elige **Deploy from a branch**.
4. En **Branch** elige `main` y la carpeta `/ (root)`. Pulsa **Save**.
5. Espera 1 a 3 minutos y recarga. Arriba aparecerá el enlace:

   ```
   https://TU-USUARIO.github.io/iglesia-los-almendros/
   ```

Ese enlace es público: se abre sin iniciar sesión. Ahí puedes generar el código QR definitivo.

Referencia oficial: [Creating a GitHub Pages site](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site) y
[Configuring a publishing source](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site).

---

## 3. Desplegar en ChatGPT Sites

> **Importante:** no pude confirmar con fuentes oficiales que "ChatGPT Sites" exista como servicio
> ni cómo se conecta a GitHub. Revisa la documentación oficial de OpenAI antes de seguir. Lo que
> sigue es el procedimiento general para cualquier servicio de alojamiento de páginas estáticas;
> ajusta los nombres de los botones a lo que te muestre la plataforma.

Esta página es **estática**: no necesita servidor, base de datos ni proceso de compilación.
Por eso funciona en cualquier servicio que aloje archivos HTML.

Datos que normalmente pide una plataforma al conectar el repositorio:

| Campo | Valor para esta página |
|---|---|
| Repositorio | `TU-USUARIO/iglesia-los-almendros` |
| Rama (branch) | `main` |
| Comando de compilación (build) | *(dejar vacío; no hay build)* |
| Carpeta de publicación (publish / output directory) | `/` (la raíz, donde está `index.html`) |
| Framework | Ninguno / HTML estático |

Pasos generales:

1. Inicia sesión en la plataforma y elige **crear sitio nuevo** o **importar desde GitHub**.
2. Autoriza el acceso a tu cuenta de GitHub y elige el repositorio `iglesia-los-almendros`.
3. Rellena los campos de la tabla de arriba.
4. Pulsa **Deploy / Publicar** y espera el enlace.
5. Abre el enlace en una ventana privada para comprobar que se ve sin iniciar sesión.

Si la plataforma no se conecta a GitHub, casi todas permiten **subir el archivo `index.html` directamente**.

---

## 4. Antes de publicar: pendientes de la página

- **Correo del formulario:** el formulario de contacto abre el correo del visitante dirigido a
  `contacto@minegocio.cl`, que es un dato de ejemplo. Cámbialo por el correo real buscando
  `mailto:` dentro de `index.html`. (Ahora mismo el formulario está vacío, sin letras ni campos visibles.)
- **WhatsApp:** el botón flotante apunta a `https://wa.me/56900000000`, que es un número de
  ejemplo. Reemplaza `56900000000` por el número real, con código de país y sin `+`.
- **Título de la pestaña:** en `index.html`, la etiqueta `<title>` dice
  `Iglesia.los.almedros. MMM`. Corrígela a `Iglesia los almendros` si ese texto no es intencional.
- **Tipografía:** el título usa la fuente *Playfair Display* desde Google Fonts, así que necesita
  internet para verse así; sin conexión se muestra en Georgia.
- **Imagen superior:** aún falta incorporar la imagen que querías poner en la parte de arriba.
  Súbela a `imagenes/` y agrégala en el HTML.

## 5. Actualizar la página después

1. Edita `index.html` (en GitHub: abre el archivo → ícono del lápiz → **Commit changes**).
2. GitHub Pages se actualiza solo en 1 a 3 minutos.
3. Si usas otra plataforma conectada al repositorio, normalmente se vuelve a desplegar sola con cada cambio.

## 6. Código QR

El código QR que se hizo antes apunta a un enlace **privado** de otra plataforma, que pide iniciar
sesión. Cuando tengas el enlace público definitivo (por ejemplo el de GitHub Pages), hay que generar
un QR nuevo con ese enlace.

## 7. Problemas comunes

| Síntoma | Causa probable | Solución |
|---|---|---|
| GitHub Pages muestra error 404 | El archivo no se llama exactamente `index.html` o no está en la raíz | Renómbralo y súbelo a la raíz |
| El enlace no aparece en Pages | Repositorio privado, o rama mal elegida | Hazlo público y elige `main` + `/ (root)` |
| Los cambios no se ven | Caché del navegador o Pages aún publicando | Espera unos minutos y recarga con Ctrl+F5 |
| La letra del título se ve distinta | Sin conexión a Google Fonts | Verifica que haya internet |
| El QR pide iniciar sesión | Apunta al enlace privado | Generar QR nuevo con el enlace público |

## Fuentes

- [GitHub Pages: documentación oficial](https://docs.github.com/en/pages)
- [Quickstart for GitHub Pages](https://docs.github.com/en/pages/quickstart)
