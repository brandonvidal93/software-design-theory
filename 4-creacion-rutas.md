# Desarrollo Backend

## Creación de las Rutas

Las rutas son las direcciones **Url** por medio de las cuales una página accede a la información de la base de datos.

1. Dentro de la carpeta **`src`** creamos la carpeta **`routes`** y creamos el archivo **`productRoutes.ts`**

**Estructura del proyecto**
``` bash
backend-service/
├── node_modules/
├── src/
│   ├── controllers/
│   │   └── productController.ts
│   ├── entities/
│   │   └── Product.ts
│   ├── routes/
│   │   └── productRoutes.ts
│   └── data-source.ts
├── .gitignore
├── package-lock.json
├── package.json
└── tsconfig.json
```

2. Es este archivo van las rutas que dan acceso a las páginas a la base de datos y también la documentación sobre como se utilizan cada una de ellas.

``` typescript
import { Router } from "express";
import {
  getAllProducts,
  getProductById,
  createProduct,
  updateProduct,
  deleteProduct,
} from "../controllers/productController";

const productRoutes = Router();

/**
 * @swagger
 * tags:
 *   name: Products
 *   description: CRUD relacionado con productos
 */

/**
 * @swagger
 * /api/products:
 *   get:
 *     summary: Obtener todos los productos
 *     tags: [Products]
 *     responses:
 *       200:
 *         description: Lista de productos
 */
productRoutes.get("/", getAllProducts);

/**
 * @swagger
 * /api/products/{id}:
 *   get:
 *     summary: Obtener un producto por ID
 *     tags: [Products]
 *     parameters:
 *       - in: path
 *         name: id
 *         required: true
 *         schema:
 *           type: integer
 *         description: ID del producto
 *     responses:
 *       200:
 *         description: Detalles del producto
 *       404:
 *         description: Producto no encontrado
 */
productRoutes.get("/:id", getProductById);

/**
 * @swagger
 * /api/products:
 *   post:
 *     summary: Crear un nuevo producto
 *     tags: [Products]
 *     requestBody:
 *       required: true
 *       content:
 *         application/json:
 *           schema:
 *             type: object
 *             required:
 *               - name
 *               - description
 *               - price
 *             properties:
 *               name:
 *                 type: string
 *               description:
 *                 type: string
 *               price:
 *                 type: number
 *     responses:
 *       201:
 *         description: Producto creado
 *       500:
 *         description: Error en el servidor
 */
productRoutes.post("/", createProduct);

/**
 * @swagger
 * /api/products/{id}:
 *   put:
 *     summary: Actualizar un producto existente
 *     tags: [Products]
 *     parameters:
 *       - in: path
 *         name: id
 *         required: true
 *         schema:
 *           type: integer
 *         description: ID del producto
 *     requestBody:
 *       required: false
 *       content:
 *         application/json:
 *           schema:
 *             type: object
 *             properties:
 *               name:
 *                 type: string
 *               description:
 *                 type: string
 *               price:
 *                 type: number
 *     responses:
 *       200:
 *         description: Producto actualizado
 *       404:
 *         description: Producto no encontrado
 *       500:
 *         description: Error en el servidor
 */
productRoutes.put("/:id", updateProduct);

/**
 * @swagger
 * /api/products/{id}:
 *   delete:
 *     summary: Eliminar un producto
 *     tags: [Products]
 *     parameters:
 *       - in: path
 *         name: id
 *         required: true
 *         schema:
 *           type: integer
 *         description: ID del producto
 *     responses:
 *       200:
 *         description: Producto eliminado
 *       404:
 *         description: Producto no encontrado
 *       500:
 *         description: Error en el servidor
 */
productRoutes.delete("/:id", deleteProduct);

export default productRoutes;
```
