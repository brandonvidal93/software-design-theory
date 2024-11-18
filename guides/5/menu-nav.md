# Desarrollo Frontend

## Creando el menú de navegación

Para crear el menú de nuestro proyecto usaremos un componente prediseñado de Bootstrap para esto.

En la página de Bootstrap en la sección de **Components** buscaremos la opción **Navbar**.

Utilizaremos el siguiente código:

``` html
  <!-- Barra de Navegación -->
  <nav class="navbar navbar-expand-lg bg-body-tertiary bg-dark" data-bs-theme="dark">
    <div class="container-fluid">
      <a class="navbar-brand" href="index.html">Nombre Proyecto</a>
      <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav me-auto mb-2 mb-lg-0">
          <li class="nav-item">
            <a class="nav-link" aria-current="page" href="index.html">Catálogo</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="add-product.html">Agregar Producto</a>
          </li>
        </ul>
      </div>
    </div>
  </nav>
```

- En donde dice **Nombre Proyecto** va el nombre de tu Página.
- Donde dice **Catálogo** será el menú hacia nuestra página principal.
- Donde dice **Agregar Producto** será el menú hacia nuestra página de formulario.

Cada una de estas opciones es una etiqueta **`<a>`** las cuales tienen los atributos **href** en donde ven relacionados las rutas de los archivos de las páginas mencionadas anteriormente.

- **`<a href="index.html">Nombre Proyecto</a>`**
- **`<a href="index.html">Catálogo</a>`**
- **`<a href="add-product.html">Agregar Producto</a>`**

En la página **`index.html`** y **`add-product.html`** agregaremos este menú. Quedamos de la siguiente forma.

#### Archivo `index.html`

``` html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>Título de la Página</title>

    <!-- Estilos Bootstrap -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-QWTKZyjpPEjISv5WaRU9OFeRpok6YctnYmDr5pNlyT2bRjXh0JMhjY6hW+ALEwIH" crossorigin="anonymous">
  </head>
  <body>
    <!-- Barra de Navegación -->
    <nav class="navbar navbar-expand-lg bg-body-tertiary bg-dark" data-bs-theme="dark">
      <div class="container-fluid">
        <a class="navbar-brand" href="index.html">Nombre Proyecto</a>
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
    
    <!-- Componentes -->
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js" integrity="sha384-YvpcrYf0tY3lHB60NNkmXc5s9fDVZLESaAA55NDzOxhy9GkcIdslK1eN7N6jIeHz" crossorigin="anonymous"></script>
  </body>
</html>
```

#### Archivo `add-product.html`

``` html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>Añadir Producto</title>

    <!-- Estilos Bootstrap -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-QWTKZyjpPEjISv5WaRU9OFeRpok6YctnYmDr5pNlyT2bRjXh0JMhjY6hW+ALEwIH" crossorigin="anonymous">
  </head>
  <body>
    <!-- Barra de Navegación -->
    <nav class="navbar navbar-expand-lg bg-body-tertiary bg-dark" data-bs-theme="dark">
      <div class="container-fluid">
        <a class="navbar-brand" href="index.html">Nombre Proyecto</a>
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
    
    <!-- Componentes -->
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js" integrity="sha384-YvpcrYf0tY3lHB60NNkmXc5s9fDVZLESaAA55NDzOxhy9GkcIdslK1eN7N6jIeHz" crossorigin="anonymous"></script>
  </body>
</html>
```

## [Volver al Menú](../../README.md)