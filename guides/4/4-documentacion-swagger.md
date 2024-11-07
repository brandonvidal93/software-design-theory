# Desarrollo Backend

## Documentación del Backend

Es importante realizar la documentación de nuestros servicios para que todo el equipo de desarrollo sepa como funciona la aplicación.

Para esto utilizaremos la librería **Swagger** para documentar el Backend.

1. Dentro de **`src`** creamos la carpeta **`swagger`** y dentro de esta creamos el archivo **`swagger.ts`**

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
│   └── data-source.ts
├── .gitignore
├── package-lock.json
├── package.json
└── tsconfig.json
```

2. Este código se encargará de crear una plataforma en la cual podremos observar los servicios disponibles, su **Url** y forma de utilizar.

``` typescript
import swaggerJsdoc, { Options } from 'swagger-jsdoc';

const swaggerOptions: Options = {
  definition: {
    openapi: "3.0.0",
    info: {
      title: "Backend Service API",
      version: "1.0.0",
      description: "API para Catálogo de Productos y Gestión de Pedidos",
    },
    servers: [
      {
        url: "http://localhost:3000/",
      },
    ],
  },
  apis: ["./src/routes/productRoutes.ts"],
};

const swaggerSpec = swaggerJsdoc(swaggerOptions);

export default swaggerSpec;
```