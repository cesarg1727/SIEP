# SIEP - Sistema Integrado de Evaluación Psicológica

Hub web estático que centraliza el acceso a las aplicaciones Shiny alojadas en shinyapps.io.
Diseño institucional UDLA (rojo #E30613, negro, blanco).

---

## 1. Personalizar las aplicaciones

Abre `index.html` en cualquier editor (Notepad, VS Code, etc.) y busca el arreglo `apps` cerca del final del archivo.

Reemplaza los valores por los datos reales de tus 4 aplicaciones:

```javascript
const apps = [
    {
        etiqueta: "Instrumento 01",
        nombre: "Escala de Ansiedad de Beck",            // <-- nombre real
        descripcion: "Evalúa síntomas de ansiedad...",   // <-- descripción
        url: "https://tu-usuario.shinyapps.io/beck/"     // <-- URL real
    },
    // ... resto de apps
];
```

### Para añadir una nueva app en el futuro

Solo agrega un nuevo objeto al arreglo:

```javascript
{
    etiqueta: "Instrumento 05",
    nombre: "Nueva Prueba",
    descripcion: "Descripción breve.",
    url: "https://tu-usuario.shinyapps.io/nueva-app/"
}
```

No necesitas tocar HTML, CSS ni nada más. La tarjeta aparecerá automáticamente.

---

## 2. Despliegue gratuito en GitHub Pages

### Paso 1: Crear cuenta y repositorio

1. Si no tienes cuenta, créala en https://github.com (gratis).
2. Haz clic en el botón verde **"New"** para crear un repositorio nuevo.
3. Nombre sugerido: `siep` (en minúsculas, sin espacios).
4. Marca la opción **"Public"**. *(Pages gratuito solo funciona con repos públicos)*
5. **No** marques "Add a README file" (ya lo tienes).
6. Clic en **"Create repository"**.

### Paso 2: Subir los archivos

**Opción A — desde el navegador (la más fácil):**

1. En tu repo recién creado, haz clic en **"uploading an existing file"**.
2. Arrastra los archivos `index.html` y `README.md`.
3. Abajo, clic en **"Commit changes"**.

**Opción B — con Git desde terminal:**

```bash
git clone https://github.com/tu-usuario/siep.git
cd siep
# (copia aquí los archivos index.html y README.md)
git add .
git commit -m "Versión inicial del SIEP"
git push
```

### Paso 3: Activar GitHub Pages

1. En tu repositorio, entra a **Settings** (pestaña superior derecha).
2. En el menú lateral izquierdo: **Pages**.
3. En "Source", selecciona la rama **`main`** (o `master`) y la carpeta **`/ (root)`**.
4. Clic en **Save**.
5. Espera 1-2 minutos. GitHub mostrará una URL tipo:

   ```
   https://tu-usuario.github.io/siep/
   ```

Esa es la dirección pública de tu SIEP. Compártela con quien quieras.

---

## 3. Actualizaciones futuras

Cada vez que edites el `index.html` (para añadir una nueva app, cambiar un texto, etc.):

- **Desde el navegador:** edita el archivo directamente en GitHub (ícono del lápiz) → "Commit changes". Los cambios se publican solos en 1-2 minutos.
- **Desde terminal:** `git add .` → `git commit -m "Nueva app X"` → `git push`.

---

## 4. Dominio personalizado (opcional)

Si en el futuro quieres una URL tipo `siep.udla.edu.ec`:

1. Compra/solicita el dominio.
2. En **Settings → Pages → Custom domain**, ingresa el dominio.
3. Configura un registro CNAME en tu proveedor DNS apuntando a `tu-usuario.github.io`.

---

## 5. Alternativas de despliegue (por si GitHub Pages no encaja)

| Plataforma | Ventaja | Contra |
|------------|---------|--------|
| **GitHub Pages** ✓ | Gratis permanente, versionado, profesional | Requiere cuenta GitHub |
| **Netlify** | Drag & drop en https://app.netlify.com/drop | Dominio con sufijo `.netlify.app` |
| **Cloudflare Pages** | Muy rápido, CDN global | Setup un poco más técnico |
| **Vercel** | Despliegue en segundos | Orientado más a apps con backend |

Todas son gratuitas para este tipo de sitio estático.

---

## 6. Estructura de archivos

```
siep/
├── index.html      <- Página principal (todo el código está aquí)
└── README.md       <- Este archivo
```

El proyecto intencionalmente es un único archivo HTML autocontenido: sin dependencias,
sin build step, sin servidor. Solo HTML, CSS y JavaScript estándar.

---

**Desarrollado para Universidad de las Américas · Ecuador**
