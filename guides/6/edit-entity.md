# Ajustes

## Mofificando la Entidad del proyecto

Para agregar la Url de nuestra imagen debemos comenzar desde la entidad de nuestro proyecto la cual está ubicada en el **Backend** en la carpeta **entities**. Debemos agregar un nuevo campo de tipo **string** llamado **`imgUrl`**.

Nuestro archivo debe quedar de la siguiente manera:

``` TypeScript
import { Entity, PrimaryGeneratedColumn, Column } from "typeorm";

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

  @Column("text")
  imgUrl!: string;
}
```

## [Volver al Menú](../../README.md)