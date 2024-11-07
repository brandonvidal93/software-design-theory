# Desarrollo Backend

## Configuración Servidor Backend

Después de realizar el desarrollo de las **Entidades**, **Controladores**, **Rutas**, **data-source**, **Swagger**. Podremos configurar el servidor para poder utilizarlo en nuestro equipo.

1. Dentro de la carpeta **`src`** creamos el archivo **`index.ts`** el cual será nuestro archivo principal y manejará toda la configuración del servidor.

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
│   ├── swagger/
│   │   └── swagger.ts
│   ├── data-source.ts
│   └── index.ts
├── .gitignore
├── package-lock.json
├── package.json
└── tsconfig.json
```

Codigo del archivo **`index.ts`**.

``` typescript
import express, { Application } from "express";
import cors from "cors";
import { AppDataSource } from "./data-source";
import productRoutes from "./routes/productRoutes";
import swaggerUI from "swagger-ui-express";
import swaggerSpec from "./swagger/swagger";

const app: Application = express();
const PORT = process.env.PORT ?? 3000;

// Middleware - Guardianes de ruta
app.use(cors());
app.use(express.json());

// Rutas
app.use("/api/products", productRoutes);

// Documentación Swagger
app.use("/api-docs", swaggerUI.serve, swaggerUI.setup(swaggerSpec));

// Inicialización de la base de datos y el servidor
AppDataSource.initialize()
  .then(() => {
    app.listen(PORT, () => {
      console.log(`Servidor corriendo en http://localhost:${PORT}\n`);

      console.log(`Endpoints:`);
      console.log(`API Products http://localhost:${PORT}/api/products`);

      console.log(`Documentación:`);
      console.log(`Swagger en http://localhost:${PORT}/api-docs`);
    });
  })
  .catch((error) => console.log(error));
```

## [Volver al Menú](../../README.md)