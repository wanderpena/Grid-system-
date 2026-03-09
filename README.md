# Sistema de Grid SCSS

Sistema de grid flexible y completo basado en SCSS con soporte para **Flexbox** o **CSS Grid**.

## 🎯 Características

- ✅ **Dual Mode**: Soporte para Flexbox o CSS Grid
- ✅ **12 Columnas**: Sistema flexible de 12 columnas
- ✅ **Responsivo**: 3 breakpoints configurables (sm, md, lg)
- ✅ **Gaps Fluidos**: Sistema de espaciado con clamp() para diseño responsive
- ✅ **Offsets**: Desplazamiento de columnas
- ✅ **Row Cols**: Columnas uniformes por fila
- ✅ **Orden**: Control del orden de columnas
- ✅ **Alineación**: Justify content, align items, align self
- ✅ **Totalmente Configurable**: Variables SCSS para personalización completa

## 📦 Instalación

### Paso 1: Copiar archivos

Copia `grid-system.scss` a tu proyecto:

```
proyecto/
├── scss/
│   └── grid-system.scss
└── index.html
```

### Paso 2: Importar en tu proyecto

```scss
// En tu archivo principal SCSS
@import 'grid-system';
```

### Paso 3: Compilar SCSS

Usa tu herramienta favorita para compilar SCSS:

**Con Sass CLI:**
```bash
sass scss/main.scss css/main.css
```

**Con npm scripts:**
```json
{
  "scripts": {
    "sass": "sass --watch scss:css"
  }
}
```

## ⚙️ Configuración

Personaliza el grid system modificando las variables SCSS **antes** de importar el archivo:

```scss
// Configuración personalizada
$grid-type: 'flexbox';           // 'flexbox' o 'grid'
$enable-gaps: true;              // Habilitar clases de gap
$enable-offsets: true;           // Habilitar clases de offset
$grid-columns: 12;               // Número de columnas

// Breakpoints personalizados
$grid-breakpoints: (
  'sm': '48rem',                 // 768px
  'md': '64rem',                 // 1024px
  'lg': '80rem',                 // 1280px
  'xl': '96rem'                  // 1536px (opcional)
);

// Espaciados personalizados
$gutters: (
  0: 0,
  1: 0.25rem,
  2: 0.5rem,
  3: 1rem,
  4: 1.5rem,
  5: 3rem
);

// Ancho del contenedor
$container-max: 1280px;

// Importar grid system
@import 'grid-system';
```

## 🚀 Uso Rápido

### Container y Row

```html
<div class="container">
  <div class="row">
    <div class="col">Columna 1</div>
    <div class="col">Columna 2</div>
    <div class="col">Columna 3</div>
  </div>
</div>
```

### Columnas de Tamaño Específico

```html
<div class="container">
  <div class="row">
    <div class="col-4">33.33%</div>
    <div class="col-8">66.67%</div>
  </div>
</div>
```

### Responsive

```html
<div class="container">
  <div class="row">
    <div class="col-12 col-md-6 col-lg-4">
      Mobile: 100% | Tablet: 50% | Desktop: 33%
    </div>
  </div>
</div>
```

### Con Gaps

```html
<div class="container">
  <div class="row g-3">
    <div class="col-6">Con espaciado</div>
    <div class="col-6">Con espaciado</div>
  </div>
</div>
```

## 📚 Documentación Completa

Para ver todos los ejemplos y la documentación completa, consulta:
- **[USAGE-GUIDE.md](USAGE-GUIDE.md)** - Guía completa de uso
- **[demo.html](demo.html)** - Demo interactiva con todos los ejemplos

## 🎨 Ver Demo

Abre `demo.html` en tu navegador para ver todos los ejemplos visuales del sistema.

## 📋 Clases Disponibles

### Columnas
- `.col` - Ancho flexible
- `.col-{1-12}` - Tamaño específico
- `.col-{breakpoint}-{1-12}` - Responsive

### Gaps
- `.g-{0-5}` - Gap horizontal y vertical
- `.gx-{0-5}` - Gap horizontal
- `.gy-{0-5}` - Gap vertical

### Offsets
- `.offset-{0-11}` - Desplazamiento
- `.offset-{breakpoint}-{0-11}` - Responsive

### Alineación (Flexbox)
- `.justify-content-{start|end|center|between|around|evenly}`
- `.align-items-{start|end|center|baseline|stretch}`
- `.align-self-{auto|start|end|center|baseline|stretch}`

### Orden
- `.order-{0-12}`
- `.order-first` / `.order-last`

## 🔄 Migrar entre Flexbox y CSS Grid

Solo cambia la variable `$grid-type`:

```scss
// Cambiar a CSS Grid
$grid-type: 'grid';

// Volver a Flexbox
$grid-type: 'flexbox';
```

Recompila tu SCSS y ¡listo!

## 🌟 Ejemplos Comunes

### Layout Blog

```html
<div class="container">
  <div class="row g-4">
    <div class="col-12 col-lg-8">
      <article>Contenido principal</article>
    </div>
    <div class="col-12 col-lg-4">
      <aside>Sidebar</aside>
    </div>
  </div>
</div>
```

### Grid de Productos

```html
<div class="container">
  <div class="row row-cols-1 row-cols-sm-2 row-cols-md-3 row-cols-lg-4 g-3">
    <div class="col"><div class="product-card">Producto</div></div>
    <div class="col"><div class="product-card">Producto</div></div>
    <div class="col"><div class="product-card">Producto</div></div>
    <div class="col"><div class="product-card">Producto</div></div>
  </div>
</div>
```

### Dashboard

```html
<div class="container-fluid">
  <div class="row g-3">
    <div class="col-12 col-md-6 col-lg-3">
      <div class="widget">Widget 1</div>
    </div>
    <div class="col-12 col-md-6 col-lg-3">
      <div class="widget">Widget 2</div>
    </div>
    <div class="col-12 col-md-6 col-lg-3">
      <div class="widget">Widget 3</div>
    </div>
    <div class="col-12 col-md-6 col-lg-3">
      <div class="widget">Widget 4</div>
    </div>
  </div>
</div>
```

## 🛠️ Compilación Avanzada

### Con Webpack

```javascript
// webpack.config.js
module.exports = {
  module: {
    rules: [
      {
        test: /\.scss$/,
        use: ['style-loader', 'css-loader', 'sass-loader']
      }
    ]
  }
};
```

### Con Vite

```javascript
// vite.config.js
export default {
  css: {
    preprocessorOptions: {
      scss: {
        additionalData: `@import "./src/scss/variables.scss";`
      }
    }
  }
};
```

### Con Gulp

```javascript
// gulpfile.js
const gulp = require('gulp');
const sass = require('gulp-sass')(require('sass'));

gulp.task('sass', function() {
  return gulp.src('./scss/**/*.scss')
    .pipe(sass().on('error', sass.logError))
    .pipe(gulp.dest('./css'));
});

gulp.task('watch', function() {
  gulp.watch('./scss/**/*.scss', gulp.series('sass'));
});
```

## 📊 Estructura de Archivos

```
grid-system/
├── grid-system.scss      # Sistema de grid principal
├── USAGE-GUIDE.md       # Guía de uso completa
├── README.md            # Este archivo
├── demo.html            # Demo interactiva
└── demo-styles.css      # Estilos para la demo
```

## 🎓 Recursos de Aprendizaje

- [Flexbox Guide](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [CSS Grid Guide](https://css-tricks.com/snippets/css/complete-guide-grid/)
- [SCSS Documentation](https://sass-lang.com/documentation)
- [Responsive Design](https://web.dev/responsive-web-design-basics/)

## 💡 Tips y Mejores Prácticas

1. **Mobile First**: Define estilos base sin breakpoint, luego añade para pantallas más grandes
2. **Usa Row Cols**: Para grids uniformes (productos, cards), usa `row-cols-*`
3. **Gaps sobre Margins**: Usa el sistema de gaps en lugar de margins personalizados
4. **Offsets para Centrar**: Usa `offset-*` para centrar contenido o crear layouts asimétricos
5. **Contenedor Apropiado**: Usa `.container` para ancho máximo o `.container-fluid` para ancho completo

## 🐛 Troubleshooting

### Problema: Las columnas no suman 12
```html
<!-- Incorrecto -->
<div class="row">
  <div class="col-8">...</div>
  <div class="col-8">...</div> <!-- 8 + 8 = 16 -->
</div>

<!-- Correcto -->
<div class="row">
  <div class="col-6">...</div>
  <div class="col-6">...</div> <!-- 6 + 6 = 12 -->
</div>
```

### Problema: Los gaps no funcionan
```html
<!-- Incorrecto: gap en col -->
<div class="row">
  <div class="col g-3">...</div>
</div>

<!-- Correcto: gap en row -->
<div class="row g-3">
  <div class="col">...</div>
</div>
```

### Problema: Clases responsivas no se aplican
Verifica que:
1. Los breakpoints estén configurados correctamente
2. El CSS esté compilado
3. No haya CSS conflictivo con mayor especificidad

## 📝 Licencia

Este proyecto es de código abierto y está disponible para uso personal y comercial.

## 🤝 Contribuir

¿Encontraste un bug o tienes una sugerencia? 
- Reporta issues
- Envía pull requests
- Comparte tus mejoras

## 📞 Soporte

Para más información, consulta:
- Documentación completa: `USAGE-GUIDE.md`
- Demo interactiva: `demo.html`
- Ejemplos de código en la guía de uso

---

Desarrollado con ❤️ para facilitar el desarrollo de layouts responsivos
