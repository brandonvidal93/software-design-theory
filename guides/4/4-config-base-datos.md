# Desarrollo Backend

## Configuración de Base de datos

1. En la carpeta **`src`** creamos el archivo **`data-source.ts`**.

**Estructura del proyecto**
``` bash
backend-service/
├── node_modules/
├── src/
│   ├── entities/
│   │   └── Product.ts
│   └── data-source.ts
├── .gitignore
├── package-lock.json
├── package.json
└── tsconfig.json
```

2. En este archivo va a ir toda la configuración de nuestra base de datos y allí colocamos la entidades que creemos para que se monten las tablas dentro de la base de datos.

``` typescript
import "reflect-metadata";
import { DataSource } from "typeorm";
import { Product } from "./entities/Produt";


export const AppDataSource = new DataSource({
  type: "sqlite",
  database: "database.sqlite",
  synchronize: true,
  logging: false,
  entities: [Product],
  migrations:[],
  subscribers:[]
});
```

## [Volver al Menú](../../README.md)