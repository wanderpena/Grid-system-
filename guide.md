# Grid System - Guía de Uso

Sistema de grid flexible basado en SCSS con soporte para Flexbox o CSS Grid.

## 📋 Tabla de Contenidos

- [Instalación](#instalación)
- [Configuración](#configuración)
- [Componentes](#componentes)
- [Ejemplos de Uso](#ejemplos-de-uso)
- [Clases Disponibles](#clases-disponibles)

## 🚀 Instalación

```scss
// Importa el archivo en tu proyecto SCSS
@import 'grid-system';
```

## ⚙️ Configuración

El sistema es altamente configurable mediante variables SCSS:

```scss
// Tipo de grid: 'flexbox' o 'grid'
$grid-type: 'flexbox';

// Habilitar clases opcionales
$enable-gaps: true;
$enable-offsets: true;

// Número de columnas
$grid-columns: 12;

// Breakpoints
$grid-breakpoints: (
  'sm': '48rem',   // 768px
  'md': '64rem',   // 1024px
  'lg': '80rem'    // 1280px
);

// Espaciados (gaps)
$gutters: (
  0: 0,
  1: clamp(0.33rem, calc(-0.09vw + 0.35rem), 0.27rem),
  2: clamp(0.8rem, calc(0.39vw + 0.72rem), 1.06rem),
  3: clamp(1.56rem, calc(2.13vw + 1.14rem), 3rem),
  4: clamp(2.44rem, calc(5.27vw + 1.39rem), 6rem),
  5: clamp(3.05rem, calc(8.04vw + 1.44rem), 8.48rem),
);

// Ancho máximo del contenedor
$container-max: 1280px;
```

## 🧱 Componentes

### Container

Contenedor con ancho máximo y padding horizontal:

```html
<div class="container">
  <!-- Contenido -->
</div>
```

Contenedor de ancho completo:

```html
<div class="container-fluid">
  <!-- Contenido -->
</div>
```

### Row

Contenedor para columnas:

```html
<div class="row">
  <div class="col">Columna</div>
  <div class="col">Columna</div>
</div>
```

### Columnas

Columnas básicas (ancho igual):

```html
<div class="row">
  <div class="col">1 de 3</div>
  <div class="col">2 de 3</div>
  <div class="col">3 de 3</div>
</div>
```

Columnas con tamaño específico:

```html
<div class="row">
  <div class="col-4">4 columnas</div>
  <div class="col-8">8 columnas</div>
</div>
```

Columnas auto (ancho basado en contenido):

```html
<div class="row">
  <div class="col-auto">Auto</div>
  <div class="col">Resto</div>
</div>
```

## 📱 Ejemplos de Uso

### Layout Básico

```html
<div class="container">
  <div class="row">
    <div class="col-12">Header completo</div>
  </div>
  <div class="row">
    <div class="col-md-8">Contenido principal</div>
    <div class="col-md-4">Sidebar</div>
  </div>
</div>
```

### Layout Responsivo

```html
<div class="container">
  <div class="row">
    <div class="col-12 col-sm-6 col-md-4 col-lg-3">
      <!-- Mobile: 100%, Tablet: 50%, Desktop: 33%, Large: 25% -->
    </div>
    <div class="col-12 col-sm-6 col-md-4 col-lg-3">
      <!-- Mobile: 100%, Tablet: 50%, Desktop: 33%, Large: 25% -->
    </div>
    <div class="col-12 col-sm-6 col-md-4 col-lg-3">
      <!-- Mobile: 100%, Tablet: 50%, Desktop: 33%, Large: 25% -->
    </div>
    <div class="col-12 col-sm-6 col-md-4 col-lg-3">
      <!-- Mobile: 100%, Tablet: 50%, Desktop: 33%, Large: 25% -->
    </div>
  </div>
</div>
```

### Gaps (Espaciado)

```html
<!-- Gap uniforme -->
<div class="row g-3">
  <div class="col-6">Columna con gap</div>
  <div class="col-6">Columna con gap</div>
</div>

<!-- Gap horizontal solamente -->
<div class="row gx-4">
  <div class="col-6">Columna</div>
  <div class="col-6">Columna</div>
</div>

<!-- Gap vertical solamente -->
<div class="row gy-2">
  <div class="col-12">Fila 1</div>
  <div class="col-12">Fila 2</div>
</div>

<!-- Gaps responsivos -->
<div class="row g-2 g-md-4 g-lg-5">
  <div class="col-6">Gap adaptativo</div>
  <div class="col-6">Gap adaptativo</div>
</div>
```

### Offsets (Desplazamiento)

```html
<!-- Offset básico -->
<div class="row">
  <div class="col-4 offset-4">Centrado</div>
</div>

<!-- Offset responsivo -->
<div class="row">
  <div class="col-12 col-md-6 offset-md-3">
    Centrado en tablets y desktop
  </div>
</div>
```

### Row Cols (Columnas uniformes)

```html
<!-- 3 columnas iguales por fila -->
<div class="row row-cols-3">
  <div class="col">Item 1</div>
  <div class="col">Item 2</div>
  <div class="col">Item 3</div>
  <div class="col">Item 4</div>
  <div class="col">Item 5</div>
  <div class="col">Item 6</div>
</div>

<!-- Row-cols responsivo -->
<div class="row row-cols-1 row-cols-sm-2 row-cols-md-3 row-cols-lg-4">
  <div class="col">Item</div>
  <div class="col">Item</div>
  <div class="col">Item</div>
  <div class="col">Item</div>
</div>
```

### Orden de Columnas

```html
<div class="row">
  <div class="col order-3">Primero en HTML, tercero visualmente</div>
  <div class="col order-1">Segundo en HTML, primero visualmente</div>
  <div class="col order-2">Tercero en HTML, segundo visualmente</div>
</div>

<!-- Orden responsivo -->
<div class="row">
  <div class="col-12 col-md-6 order-2 order-md-1">
    Primero en desktop, segundo en mobile
  </div>
  <div class="col-12 col-md-6 order-1 order-md-2">
    Segundo en desktop, primero en mobile
  </div>
</div>
```

### Alineación (Flexbox)

```html
<!-- Alineación vertical -->
<div class="row align-items-start" style="height: 200px;">
  <div class="col">Arriba</div>
</div>

<div class="row align-items-center" style="height: 200px;">
  <div class="col">Centro</div>
</div>

<div class="row align-items-end" style="height: 200px;">
  <div class="col">Abajo</div>
</div>

<!-- Alineación horizontal -->
<div class="row justify-content-start">
  <div class="col-4">Izquierda</div>
</div>

<div class="row justify-content-center">
  <div class="col-4">Centro</div>
</div>

<div class="row justify-content-end">
  <div class="col-4">Derecha</div>
</div>

<div class="row justify-content-between">
  <div class="col-4">Izquierda</div>
  <div class="col-4">Derecha</div>
</div>

<!-- Align-self (individual) -->
<div class="row" style="height: 200px;">
  <div class="col align-self-start">Arriba</div>
  <div class="col align-self-center">Centro</div>
  <div class="col align-self-end">Abajo</div>
</div>
```

## 📚 Clases Disponibles

### Columnas Base

- `.col` - Columna de ancho flexible
- `.col-auto` - Columna de ancho automático (basado en contenido)
- `.col-{1-12}` - Columnas de tamaño específico (1 a 12)

### Columnas Responsivas

- `.col-{breakpoint}` - Columna flexible en breakpoint
- `.col-{breakpoint}-auto` - Columna auto en breakpoint
- `.col-{breakpoint}-{1-12}` - Tamaño específico en breakpoint

Breakpoints: `sm`, `md`, `lg`

### Gaps

- `.g-{0-5}` - Gap horizontal y vertical
- `.gx-{0-5}` - Gap horizontal solamente
- `.gy-{0-5}` - Gap vertical solamente
- `.g-{breakpoint}-{0-5}` - Gap responsivo

### Offsets

- `.offset-{0-11}` - Desplazamiento de columnas
- `.offset-{breakpoint}-{0-11}` - Desplazamiento responsivo

### Row Cols

- `.row-cols-{1-6}` - Número de columnas por fila
- `.row-cols-auto` - Columnas de ancho automático
- `.row-cols-{breakpoint}-{1-6}` - Row-cols responsivo

### Orden (Flexbox)

- `.order-first` - Orden -1
- `.order-last` - Orden 13
- `.order-{0-12}` - Orden específico
- `.order-{breakpoint}-{0-12}` - Orden responsivo

### Alineación (Flexbox)

**Justify Content:**
- `.justify-content-start`
- `.justify-content-end`
- `.justify-content-center`
- `.justify-content-between`
- `.justify-content-around`
- `.justify-content-evenly`

**Align Items:**
- `.align-items-start`
- `.align-items-end`
- `.align-items-center`
- `.align-items-baseline`
- `.align-items-stretch`

**Align Self:**
- `.align-self-auto`
- `.align-self-start`
- `.align-self-end`
- `.align-self-center`
- `.align-self-baseline`
- `.align-self-stretch`

Todas las clases de alineación tienen versiones responsivas: `.{clase}-{breakpoint}`

## 🎯 Casos de Uso Comunes

### Grid de Productos (E-commerce)

```html
<div class="container">
  <div class="row row-cols-1 row-cols-sm-2 row-cols-md-3 row-cols-lg-4 g-3">
    <div class="col">
      <div class="product-card">Producto 1</div>
    </div>
    <div class="col">
      <div class="product-card">Producto 2</div>
    </div>
    <!-- ... más productos -->
  </div>
</div>
```

### Dashboard Layout

```html
<div class="container-fluid">
  <div class="row g-3">
    <div class="col-12">
      <header>Header</header>
    </div>
    <div class="col-12 col-lg-3">
      <nav>Sidebar</nav>
    </div>
    <div class="col-12 col-lg-9">
      <div class="row g-3">
        <div class="col-12 col-md-6 col-lg-4">
          <div class="widget">Widget 1</div>
        </div>
        <div class="col-12 col-md-6 col-lg-4">
          <div class="widget">Widget 2</div>
        </div>
        <div class="col-12 col-md-6 col-lg-4">
          <div class="widget">Widget 3</div>
        </div>
      </div>
    </div>
  </div>
</div>
```

### Galería de Imágenes

```html
<div class="container">
  <div class="row row-cols-2 row-cols-md-3 row-cols-lg-4 g-2">
    <div class="col">
      <img src="image1.jpg" alt="" class="img-fluid">
    </div>
    <div class="col">
      <img src="image2.jpg" alt="" class="img-fluid">
    </div>
    <!-- ... más imágenes -->
  </div>
</div>
```

### Formulario con Layout

```html
<div class="container">
  <form>
    <div class="row g-3">
      <div class="col-12 col-md-6">
        <label>Nombre</label>
        <input type="text" class="form-control">
      </div>
      <div class="col-12 col-md-6">
        <label>Apellido</label>
        <input type="text" class="form-control">
      </div>
      <div class="col-12">
        <label>Email</label>
        <input type="email" class="form-control">
      </div>
      <div class="col-12 col-md-8">
        <label>Dirección</label>
        <input type="text" class="form-control">
      </div>
      <div class="col-12 col-md-4">
        <label>Código Postal</label>
        <input type="text" class="form-control">
      </div>
      <div class="col-12">
        <button type="submit">Enviar</button>
      </div>
    </div>
  </form>
</div>
```

## 💡 Tips y Mejores Prácticas

1. **Anidación**: Puedes anidar rows dentro de columnas
   ```html
   <div class="row">
     <div class="col-12">
       <div class="row">
         <div class="col-6">Anidado</div>
         <div class="col-6">Anidado</div>
       </div>
     </div>
   </div>
   ```

2. **Mobile First**: Las clases sin breakpoint se aplican a todos los tamaños, luego usa breakpoints para pantallas más grandes

3. **Gaps vs Gutters**: Usa gaps (g-*, gx-*, gy-*) para espaciado entre columnas en lugar de márgenes personalizados

4. **Offsets**: Usa offsets para centrar contenido o crear layouts asimétricos

5. **Row-cols**: Ideal para grids de elementos uniformes (cards, productos, etc.)

## 🔧 Troubleshooting

### Las columnas no se alinean correctamente
- Verifica que estés usando `.row` como contenedor
- Asegúrate de que el total de columnas no exceda 12
- Revisa que no haya CSS personalizado conflictivo

### Los gaps no funcionan
- Confirma que `$enable-gaps: true` en la configuración
- Verifica que la clase gap esté en el `.row`, no en el `.col`

### Las clases responsivas no se aplican
- Revisa los breakpoints en `$grid-breakpoints`
- Asegúrate de que las media queries no estén siendo sobrescritas
- Verifica el orden de importación de tus archivos CSS

## 📄 Licencia

Este sistema de grid está diseñado para uso en proyectos personales y comerciales.
