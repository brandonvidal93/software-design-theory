# Desarrollo Backend

## Creación de Entidades

Las entidades son lo objetos que represetan los datos del mundo real, con ellas podemos realizar la manipulación de la información que ingresa a nuestro software.

En este caso como vamos a manejar Productos en nuestra página, crearemos la entidad **`Product`**

1. Creamos una carpeta llamada **`src`** en la cual irán todos los archivos de nuestro proyecto.

**Estructura del proyecto**
``` bash
backend-service/
├── node_modules/
├── src/
├── .gitignore
├── package-lock.json
├── package.json
└── tsconfig.json
```

2. Dentro de la carpeta **`src`** creamos nuestra carpeta de entidades llamada **`entities`**

**Estructura del proyecto**
``` bash
backend-service/
├── node_modules/
├── src/
│   ├── entities/
├── .gitignore
├── package-lock.json
├── package.json
└── tsconfig.json
```

3. Dentro de **`entities`** creamos la entidad producto **`Product.ts`**

**Estructura del proyecto**
``` bash
backend-service/
├── node_modules/
├── src/
│   ├── entities/
│   │   └── Product.ts
├── .gitignore
├── package-lock.json
├── package.json
└── tsconfig.json
```

4. Agregamos el siguiente código que para realizar la configuración de nuestra entidad.

``` typescript
import { Entity, PrimaryGeneratedColumn, Column } from "typeorm";
import { Order } from "./Order";

@Entity()
export class Product {
  @PrimaryGeneratedColumn()
  id!: number;

  @Column()
  name!: string;

  @Column("text")
  description!: string;

  @Column("decimal")
  price!: number;
}
```

Recuerda que una entidad representa algo del mundo real en el software, ejemplo si tu página es sobre casa y apartamentos tu entidad se debería llamar **`Builds.ts`** y llevas los campos o características. El nombre siempre de ir con la primera letra en Mayúscula por convención de desarrollo.