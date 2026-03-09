# Grid System - Cheatsheet

## 📐 Estructura Básica

```html
<div class="container">
  <div class="row">
    <div class="col">Columna</div>
  </div>
</div>
```

## 📏 Columnas

| Clase | Ancho |
|-------|-------|
| `.col` | Flexible (igual a hermanos) |
| `.col-auto` | Ajustado al contenido |
| `.col-1` a `.col-12` | 8.33% a 100% |

## 📱 Breakpoints

| Breakpoint | Tamaño | Prefijo |
|------------|--------|---------|
| Extra small | < 768px | (ninguno) |
| Small | ≥ 768px | `sm` |
| Medium | ≥ 1024px | `md` |
| Large | ≥ 1280px | `lg` |

## 🎯 Patrones Comunes

### Layout 2 Columnas
```html
<div class="row">
  <div class="col-md-8">Principal</div>
  <div class="col-md-4">Sidebar</div>
</div>
```

### Layout 3 Columnas
```html
<div class="row">
  <div class="col-md-4">Col 1</div>
  <div class="col-md-4">Col 2</div>
  <div class="col-md-4">Col 3</div>
</div>
```

### Mobile → Desktop
```html
<div class="row">
  <div class="col-12 col-md-6 col-lg-4">
    <!-- 100% → 50% → 33% -->
  </div>
</div>
```

### Grid de Cards
```html
<div class="row row-cols-1 row-cols-md-2 row-cols-lg-3 g-3">
  <div class="col"><div class="card">...</div></div>
  <div class="col"><div class="card">...</div></div>
  <div class="col"><div class="card">...</div></div>
</div>
```

## 🔲 Gaps (Espaciado)

| Clase | Aplicación |
|-------|------------|
| `.g-0` a `.g-5` | Horizontal y vertical |
| `.gx-0` a `.gx-5` | Solo horizontal |
| `.gy-0` a `.gy-5` | Solo vertical |
| `.g-md-3` | Responsive |

### Valores de Gap
- `g-0`: 0
- `g-1`: ~0.27-0.33rem
- `g-2`: ~0.8-1.06rem
- `g-3`: ~1.56-3rem
- `g-4`: ~2.44-6rem
- `g-5`: ~3.05-8.48rem

## ↔️ Offsets

```html
<!-- Centrar columna -->
<div class="col-6 offset-3">Centrado</div>

<!-- Offset responsive -->
<div class="col-md-4 offset-md-2">Desplazado</div>
```

## 🔢 Row Cols

```html
<!-- 4 columnas por fila -->
<div class="row row-cols-4">
  <div class="col">1</div>
  <div class="col">2</div>
  <div class="col">3</div>
  <div class="col">4</div>
  <!-- Nueva fila automáticamente -->
  <div class="col">5</div>
</div>

<!-- Responsive -->
<div class="row row-cols-1 row-cols-sm-2 row-cols-md-3">
  <!-- 1 columna → 2 columnas → 3 columnas -->
</div>
```

## 🎯 Alineación Vertical

```html
<!-- Toda la fila -->
<div class="row align-items-start">...</div>
<div class="row align-items-center">...</div>
<div class="row align-items-end">...</div>

<!-- Columna individual -->
<div class="col align-self-start">...</div>
<div class="col align-self-center">...</div>
<div class="col align-self-end">...</div>
```

## ↔️ Alineación Horizontal

```html
<div class="row justify-content-start">...</div>
<div class="row justify-content-center">...</div>
<div class="row justify-content-end">...</div>
<div class="row justify-content-between">...</div>
<div class="row justify-content-around">...</div>
<div class="row justify-content-evenly">...</div>
```

## 🔄 Orden

```html
<div class="row">
  <div class="col order-3">Primero en HTML, tercero visual</div>
  <div class="col order-1">Segundo en HTML, primero visual</div>
  <div class="col order-2">Tercero en HTML, segundo visual</div>
</div>

<!-- Helpers -->
<div class="col order-first">Primero (-1)</div>
<div class="col order-last">Último (13)</div>
```

## 📦 Contenedores

```html
<!-- Ancho máximo (1280px) -->
<div class="container">...</div>

<!-- Ancho completo -->
<div class="container-fluid">...</div>
```

## 🎨 Ejemplos Completos

### Hero Section
```html
<div class="container">
  <div class="row align-items-center" style="min-height: 100vh;">
    <div class="col-12 col-lg-6">
      <h1>Título</h1>
      <p>Descripción</p>
    </div>
    <div class="col-12 col-lg-6">
      <img src="hero.jpg" alt="">
    </div>
  </div>
</div>
```

### Pricing Cards
```html
<div class="container">
  <div class="row row-cols-1 row-cols-md-3 g-4">
    <div class="col">
      <div class="card">Básico</div>
    </div>
    <div class="col">
      <div class="card">Pro</div>
    </div>
    <div class="col">
      <div class="card">Enterprise</div>
    </div>
  </div>
</div>
```

### Blog Layout
```html
<div class="container">
  <div class="row g-4">
    <!-- Header -->
    <div class="col-12">
      <header>...</header>
    </div>
    
    <!-- Contenido + Sidebar -->
    <div class="col-12 col-lg-8">
      <article>...</article>
    </div>
    <div class="col-12 col-lg-4">
      <aside>...</aside>
    </div>
  </div>
</div>
```

### Footer con 4 columnas
```html
<footer>
  <div class="container">
    <div class="row row-cols-1 row-cols-sm-2 row-cols-lg-4 g-4">
      <div class="col">Empresa</div>
      <div class="col">Productos</div>
      <div class="col">Recursos</div>
      <div class="col">Legal</div>
    </div>
  </div>
</footer>
```

## 🎓 Tips Rápidos

### ✅ Hacer
- Usa `.container` para contenido centrado
- Suma columnas = 12 por fila
- Usa `row-cols-*` para grids uniformes
- Aplica gaps en `.row`, no en `.col`
- Mobile first: base sin breakpoint

### ❌ Evitar
- No pongas `.row` dentro de `.row` sin `.col` entre medio
- No uses más de 12 columnas por fila
- No mezcles offsets con widths que sumen > 12
- No apliques margins a `.col` (usa gaps)

## 🔧 Variables SCSS

```scss
// Personalizar antes de importar
$grid-type: 'flexbox';
$grid-columns: 12;
$container-max: 1280px;

$grid-breakpoints: (
  'sm': '48rem',
  'md': '64rem',
  'lg': '80rem'
);

$gutters: (
  0: 0,
  1: 0.25rem,
  2: 0.5rem,
  3: 1rem,
  4: 1.5rem,
  5: 3rem
);
```

## 🚀 Compilación

```bash
# CLI
sass grid-system.scss output.css

# Watch mode
sass --watch grid-system.scss:output.css

# Compressed
sass --style=compressed grid-system.scss output.min.css
```

## 📱 Media Queries Manuales

```scss
// Usar el mixin incluido
@include mq(md) {
  .mi-clase {
    // Estilos para medium+
  }
}

// O escribir manual
@media (min-width: 64rem) {
  .mi-clase {
    // Estilos para medium+
  }
}
```

---

**Documentación completa**: Ver `USAGE-GUIDE.md`  
**Demo visual**: Abrir `demo.html`
