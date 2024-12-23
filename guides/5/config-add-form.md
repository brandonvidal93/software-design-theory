# Desarrollo Frontend

## Terminando de configurar el `add-product.html`

Abrimos nuestro archivo **`add-product.html`** para terminar de configurarlo.

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

2. Creamos nuestro formulario para registrar información, **debes tener en cuenta que los campos del formulario deben ser los mismos que las características de la entidad del Backend para que pueda enviarse la información y guardar**.

``` html
<div class="row">
  <div class="col">
    <form id="product-form">
      <div class="mb-3">
        <label for="name" class="form-label">Nombre del producto</label>
        <input type="text" class="form-control" id="name" placeholder="Nombre del producto" required>
      </div>

      <div class="mb-3">
        <label for="description" class="form-label">Descripción</label>
        <textarea type="text" class="form-control" id="description" placeholder="Descripción del producto" required></textarea>
      </div>

      <div class="mb-3">
        <label for="price" class="form-label">Precio</label>
        <input type="number" class="form-control" id="price" placeholder="Precio del producto" required>
      </div>

      <div class="mb-3">
        <label for="imgUrl" class="form-label">Imagen del Producto</label>
        <input type="text" class="form-control" id="imgUrl" placeholder="Imagen del producto" required>
      </div>

      <button type="submit" class="btn btn-success">Guardar</button>
    </form>
  </div>
</div>
```

Ten presente que cada **`<input>`** tiene un atributo llamado **id** en este se deben colocar los nombres exactos de las características de la entidad que creaste para tu proyecto.

Y en la etiqueta **`<label>`** en el atributo **for** colocar este mismo nombre para que el **label** haga referencia a cada campo del formulario.

3. Agregaremos los **`<scripts>`** de **`api.js`** y un script para guardar la información:

``` html
<script type="module" src="js/api.js"></script>
<script type="module">
  import { addProduct } from './js/api.js';
  // Guardar Formulario de agregar producto en base de datos
  document.getElementById('product-form').addEventListener('submit', async (e) => {
    e.preventDefault();
    const newProduct = {
      name: document.getElementById('name').value,
      description: document.getElementById('description').value,
      price: parseFloat(document.getElementById('price').value),
      imgUrl: document.getElementById('imgUrl').value
    };
    await addProduct(newProduct);
    window.location.href = 'index.html'; // Redirige al inicio de la página
  });
</script>
```

Nuestro archivo **`add-product.html`** quedará de la siguiente manera:

``` html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>Tienda Online</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-QWTKZyjpPEjISv5WaRU9OFeRpok6YctnYmDr5pNlyT2bRjXh0JMhjY6hW+ALEwIH" crossorigin="anonymous">
  </head>
  <body>
    <!-- Barra de Navegación -->
    <nav class="navbar navbar-expand-lg bg-body-tertiary bg-dark" data-bs-theme="dark">
      <div class="container-fluid">
        <a class="navbar-brand" href="index.html">Tienda Online</a>
        <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarSupportedContent">
          <ul class="navbar-nav me-auto mb-2 mb-lg-0">
            <li class="nav-item">
              <a class="nav-link" aria-current="page" href="index.html">Catálogo</a>
            </li>
            <li class="nav-item">
              <a class="nav-link active" href="add-product.html">Agregar Producto</a>
            </li>
          </ul>
        </div>
      </div>
    </nav>

    <!-- FORMULARIO PARA AGREGAR PRODUCTO -->
    <main class="container pt-3 pb-3">
      <div class="row">
        <div class="col">
          <h1 class="text-center">Formulario de Registro</h1>
        </div>
      </div>
      <div class="row">
        <div class="col">
          <form id="product-form">
            <div class="mb-3">
              <label for="name" class="form-label">Nombre del producto</label>
              <input type="text" class="form-control" id="name" placeholder="Nombre del producto" required>
            </div>

            <div class="mb-3">
              <label for="description" class="form-label">Descripción</label>
              <textarea type="text" class="form-control" id="description" placeholder="Descripción del producto" required></textarea>
            </div>

            <div class="mb-3">
              <label for="price" class="form-label">Precio</label>
              <input type="number" class="form-control" id="price" placeholder="Precio del producto" required>
            </div>

            <div class="mb-3">
              <label for="imgUrl" class="form-label">Imagen del Producto</label>
              <input type="text" class="form-control" id="imgUrl" placeholder="Imagen del producto" required>
            </div>

            <button type="submit" class="btn btn-success">Guardar</button>
          </form>
        </div>
      </div>
    </main>
    
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js" integrity="sha384-YvpcrYf0tY3lHB60NNkmXc5s9fDVZLESaAA55NDzOxhy9GkcIdslK1eN7N6jIeHz" crossorigin="anonymous"></script>
    <script type="module" src="js/api.js"></script>
    <script type="module">
      import { addProduct } from './js/api.js';
      // Guardar Formulario de agregar producto en base de datos
      document.getElementById('product-form').addEventListener('submit', async (e) => {
        e.preventDefault();
        const newProduct = {
          name: document.getElementById('name').value,
          description: document.getElementById('description').value,
          price: parseFloat(document.getElementById('price').value),
          imgUrl: document.getElementById('imgUrl').value
        };
        await addProduct(newProduct);
        window.location.href = 'index.html'; // Redirige al catálogo
      });
    </script>
  </body>
</html>
```

## [Volver al Menú](../../README.md)