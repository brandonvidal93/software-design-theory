# Desarrollo Backend

## Creación de los Controladores

Los controladores son archivos que tienen el código que gestiona o administra las peticiones HTTP que realiza una página a nuestra base de datos.

Las solicitudes que se realizan desde una página son:

- **GET:** Solicitud de información
- **POST:** Envío de información para guardar en base de datos.
- **PUT:** Actualización de información existente.
- **DELETE:** Eliminación de información existente.

1. Dentro de la carpeta **`src`** creamos la carpeta **`controllers`** y dentro de esta carpeta creamos el archivo **`productController.ts`**.

**Estructura del proyecto**
``` bash
backend-service/
├── node_modules/
├── src/
│   ├── controllers/
│   │   └── productController.ts
│   ├── entities/
│   │   └── Product.ts
│   └── data-source.ts
├── .gitignore
├── package-lock.json
├── package.json
└── tsconfig.json
```

2. El código de este archivo, es el que controla el acceso a la base de datos y valida que las peticiones se realicen correctamente.

``` typescript
import { Request, Response } from "express";
import { AppDataSource } from "../data-source";
import { Product } from "../entities/Produt";

const productRepository = AppDataSource.getRepository(Product);

// GET - Obtener Todos los Productos
export const getAllProducts = async(red: Request, res: Response) => {
  try {
    const products = await productRepository.find();
    res.json(products);
  } catch(error) {
    res.status(500).json({ message: "Error al obtener productos." });
  }
};

// GET by ID - Obetener Producto por ID
export const getProductById = async(req: Request, res: Response) => {
  try {
    const product = await productRepository.findOneBy({
      id: parseInt(req.params.id),
    });

    if(product) {
      res.json(product);
    } else {
      res.status(404).json({ message: "Producto no encontrado" });
    }
  } catch(error) {
    res.status(500).json({ message: "Error al obtener el producto." });
  }
};

// POST - Crear un nuevo Producto
export const createProduct = async(req: Request, res: Response) => {
  try {
    const { name, description, price } = req.body;
    const product = new Product();
    product.name = name;
    product.description = description;
    product.price = price;

    await productRepository.save(product);
    res.status(201).json(product);
  } catch(error) {
    res.status(500).json({ message: "Error al crear el producto." });
  }
};

// PUT - Actualizar un Producto existente
export const updateProduct = async(req: Request, res: Response) => {
  try {
    const { name, description, price } = req.body;
    const product = await productRepository.findOneBy({
      id: parseInt(req.params.id),
    });

    if(product) {
      product.name = name ?? product.name;
      product.description = description ?? product.description;
      product.price = price ?? product.price;

      await productRepository.save(product);
      res.json(product);
    } else {
      res.status(404).json({ message: "Producto no encontrado" });
    }
  } catch(error) {
    res.status(500).json({ message: "Error al actualizar el producto." });
  }
};

// DELETE - Borrar un Producto
export const deleteProduct = async(req: Request, res: Response) => {
  try {
    const product = await productRepository.findOneBy({
      id: parseInt(req.params.id),
    });

    if (product) {
      await productRepository.remove(product);
      res.json({ message: "Producto eliminado." });
    } else {
      res.status(404).json({ message: "Producto no encontrado." });
    }
  } catch(error) {
    res.status(500).json({ message: "Error al eliminar el producto." });
  }
};
```

**Nota:** Cada **Entidad** debe tener su propio **Controlador**.

Los códigos **`200, 201, 404, 500`** son códigos de respuesta para las peticiones que realizan las páginas web a la base de datos.

- **`200, 201`**: Respuesta correcta del servidor con la información.
- **`404`**: No se encontró información.
- **`500`**: Error en la conexión del servidor.

Es importante aprender cada uno de estos código para realizar una correcta revisión del código y encontrar rápidamente error o bugs en el código.

Conoce más acerca de los códigos HTTP [Ver aquí](https://developer.mozilla.org/es/docs/Web/HTTP/Status).