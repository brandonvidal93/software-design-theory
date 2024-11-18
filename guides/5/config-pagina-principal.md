# Desarrollo Frontend

## Terminando de configurar el `index.html`

Nos ubicamos en nuestro archivo index en el cual vamos a terminar de configurar todo para que los productos puedan mostrarse en la página. 

También cuando le demos clic en cada botón **Ver más** se verá página con los detalles del producto.

Crearemos una sección principal en la cual colocaremos lo siguiente

``` html
<main class="container pt-3 pb-3">
  <!-- Aquí van todos los elementos -->
</main>
```

1. Coloquemos un título principal:
``` html
<div class="row">
  <div class="col">
    <h1 class="text-center">Conoce nuestros Productos</h1>
  </div>
</div>
```

2. Agregaremos el contenedor donde se van a poner nuestros productos:

``` html
<div class="row gap-3 justify-content-center" id="product-list">
  <!-- Productos -->
</div>
```

3. Agregaremos los **`<scripts>`** de **`api.js`** y **`app.js`**:

``` html
<script type="module" src="js/api.js"></script>
<script type="module" src="js/app.js"></script>
```

Nuestro archivo **`index.html`** quedará de la siguiente manera:

``` html
<!-- index.html -->
<!DOCTYPE html>
<html lang="es">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Catálogo de Productos</title>
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-QWTKZyjpPEjISv5WaRU9OFeRpok6YctnYmDr5pNlyT2bRjXh0JMhjY6hW+ALEwIH" crossorigin="anonymous">
</head>

<body>
  <!-- HEADER Y MENU -->
  <nav class="navbar bg-dark navbar-expand-lg bg-body-tertiary" data-bs-theme="dark">
    <div class="container-fluid">
      <a class="navbar-brand" href="index.html">Tienda Online</a>
      <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav me-auto mb-2 mb-lg-0">
          <li class="nav-item">
            <a class="nav-link active" aria-current="page" href="index.html">Catálogo</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="add-product.html">Agregar Producto</a>
          </li>
        </ul>
      </div>
    </div>
  </nav>
  <main class="container pt-3 pb-3">
    <div class="row">
      <div class="col">
        <h1 class="text-center">Conoce nuestros Productos</h1>
      </div>
    </div>

    <div class="row gap-3 justify-content-center" id="product-list"></div>
  </main>

  <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js" integrity="sha384-YvpcrYf0tY3lHB60NNkmXc5s9fDVZLESaAA55NDzOxhy9GkcIdslK1eN7N6jIeHz" crossorigin="anonymous"></script>
  <script type="module" src="js/api.js"></script>
  <script type="module" src="js/app.js"></script>
</body>

</html>
```

## [Volver al Menú](../../README.md)