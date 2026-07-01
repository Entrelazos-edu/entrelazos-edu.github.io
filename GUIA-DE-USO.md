# 🌿 ENTRE LAZOS — Guía de Uso del Sitio Web

## 📁 Estructura de archivos

```
📁 entrelazos/
│
├── 📄 index.html                    ← Página principal (single-page)
│   └── Secciones: Hero, Servicios, Capacitaciones, Sobre Mí,
│       Blog Preview, Testimonios, Precios, Contacto
│
├── 📄 blog.html                     ← Página del blog (listado completo)
│   └── 6 artículos de ejemplo + newsletter + categorías
│
├── 📄 articulo-template.html        ← PLANTILLA para crear nuevos artículos
│   └── Copiar, renombrar y completar con tu contenido
│
└── 📁 articulos/
    └── 📄 inclusion-derecho.html   ← Artículo de ejemplo (funcional)
```

---

## 🚀 Cómo subir el sitio a internet (GitHub Pages)

### Paso 1: Crear cuenta en GitHub
1. Ve a https://github.com
2. Regístrate con tu email
3. Verifica tu cuenta

### Paso 2: Crear un repositorio
1. Haz clic en el botón verde "New" o "+"
2. Nombre del repositorio: `entrelazos` (o el que prefieras)
3. Selecciona "Public" (público)
4. Marca "Add a README file"
5. Haz clic en "Create repository"

### Paso 3: Subir los archivos
1. Dentro de tu repositorio, haz clic en "Add file" → "Upload files"
2. Arrastra todos los archivos (index.html, blog.html, articulo-template.html)
3. También arrastra la carpeta "articulos" completa
4. Escribe un mensaje como "Subiendo sitio web Entre Lazos"
5. Haz clic en "Commit changes"

### Paso 4: Activar GitHub Pages
1. Ve a "Settings" (pestaña arriba a la derecha)
2. En el menú lateral izquierdo, busca "Pages"
3. En "Source", selecciona "Deploy from a branch"
4. Selecciona "main" y carpeta "/ (root)"
5. Haz clic en "Save"
6. Espera 2-5 minutos
7. Tu sitio estará en: `https://TU-USUARIO.github.io/entrelazos/`

---

## ✍️ Cómo crear un nuevo artículo de blog

### Opción A: Usar la plantilla (recomendado)

1. **Abre** `articulo-template.html` en un editor de texto (Bloc de notas, VS Code, o similar)

2. **Guarda como** un nuevo archivo con nombre descriptivo:
   ```
   articulos/nombre-del-articulo.html
   ```
   Ejemplo: `articulos/comunidad-antidoto.html`

3. **Reemplaza estos elementos** (buscar y reemplazar):

   | Elemento | Qué cambiar | Ejemplo |
   |---|---|---|
   | `<title>` | Título del artículo | `Comunidad: el antídoto invisible — Blog \| Entre Lazos` |
   | `class="article-hero ..."` | Categoría visual | `edu`, `gestion`, o `psico` |
   | `<div class="article-category">` | Nombre de la categoría | `Psicología Social` |
   | `<h1>` | Título principal | `Comunidad: el antídoto invisible` |
   | `<p class="article-excerpt">` | Subtítulo/Resumen | Frase que invite a leer |
   | Fecha en `.article-meta` | Fecha real | `5 de marzo de 2026` |
   | Tiempo de lectura | Estimación | `5 minutos de lectura` |
   | Contenido en `.article-body` | Tu texto completo | Escribe aquí |
   | Breadcrumb final | Título del artículo | `Comunidad: el antídoto invisible` |

4. **Guarda el archivo** y súbelo a la carpeta `articulos/`

5. **Actualiza blog.html** para que aparezca en el listado:
   - Abre `blog.html`
   - Copia una tarjeta de artículo existente (`<article class="blog-card">...`)
   - Pégala al final del `blog-grid`
   - Actualiza: título, fecha, categoría, tags, extracto y link

---

## 🎨 Categorías visuales (colores)

| Categoría | Clase CSS | Color del hero |
|---|---|---|
| Educación Especial | `edu` | Verde oscuro `#1a3a2f` |
| Gestión Educativa | `gestion` | Dorado `#c8a97e` |
| Psicología Social | `psico` | Marrón cálido `#8b7355` |

> **Importante:** Cambia la clase en el `<section class="article-hero edu">` para que el encabezado tenga el color correcto.

---

## 🔗 Cómo vincular todo correctamente

### Desde la página principal (index.html):
- El menú "Blog" apunta a `blog.html` (mismo nivel)
- El botón "Explorar todos los artículos" apunta a `blog.html`
- Cada tarjeta de blog preview apunta a `blog.html#id-del-articulo`

### Desde el blog (blog.html):
- Cada tarjeta apunta a `articulos/nombre-del-articulo.html`
- El logo y "Inicio" apuntan a `index.html` (sube un nivel con `../`)

### Desde un artículo (articulos/*.html):
- Todos los links a inicio/servicios usan `../index.html`
- El link al blog usa `../blog.html`
- Los artículos relacionados usan solo el nombre: `empatia-siglo-xxi.html`

---

## 📱 Cómo probar el sitio antes de subirlo

1. **Descarga** todos los archivos a una carpeta en tu computadora
2. **Haz doble clic** en `index.html`
3. Se abrirá en tu navegador (Chrome, Firefox, Edge)
4. Navega por todas las secciones y verifica que los links funcionen
5. **Prueba en modo móvil:** en Chrome, presiona F12 → icono de celular

---

## 📝 Calendario sugerido de publicación

| Frecuencia | Tipo de contenido |
|---|---|
| **1 artículo cada 2 semanas** | Artículo de blog (600-1000 palabras) |
| **1 capacitación cada 2-3 meses** | Nuevo curso online |
| **Actualización mensual** | Precios, testimonios, servicios |

---

## ❓ Preguntas frecuentes

**¿Puedo usar imágenes reales en vez de los gradientes?**
Sí. Reemplaza el `<div class="icon">...</div>` dentro de `.blog-image` o `.article-hero` por:
```html
<img src="ruta/de/tu/imagen.jpg" alt="Descripción" style="width:100%;height:100%;object-fit:cover;">
```

**¿Cómo cambio los precios?**
Abre `index.html`, busca la sección `#precios` y modifica los números.

**¿El formulario de contacto envía emails reales?**
No, por ahora muestra un mensaje de confirmación. Para enviar emails reales necesitas un servicio como Formspree, Netlify Forms, o un backend.

**¿Puedo agregar más categorías?**
Sí, pero necesitas definir un nuevo color en el CSS y crear la clase correspondiente. Es mejor mantener las 3 actuales alineadas a tus 3 formaciones.

---

## 🎯 Próximos pasos recomendados

1. [ ] Comprar dominio `entrelazos.org` (en Namecheap, GoDaddy, o similar)
2. [ ] Conectar el dominio a GitHub Pages
3. [ ] Crear cuenta de Instagram para Entre Lazos
4. [ ] Escribir tu primer artículo real usando la plantilla
5. [ ] Configurar Formspree para que el formulario de contacto funcione
6. [ ] Crear cuenta de email profesional (hola@entrelazos.org)

---

**¿Necesitas ayuda con algún paso?** Pregunta sin problema. 🌿
