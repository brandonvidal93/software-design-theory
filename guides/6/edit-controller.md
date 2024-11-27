# Ajustes

## Mofificando el Controlador del proyecto

Al igual que en la entidad debemos realizar la modificación de nuestro Controllador ubicado en la carpeta **`Controller`**. Debemos agregar el nuevo campo de **`imgUrl`** en cada uno de los métodos HTTP (POST, PUT) donde se guarden datos.

Nos quedaría de esta forma:

``` TypeScript
// Crear un producto (POST)
export const createProduct = async(req: Request, res: Response) => {
  try {
    const { name, description, price, imgUrl } = req.body;
    const product = new Product();
    product.name = name;
    product.description = description;
    product.price = price;
    product.imgUrl = imgUrl; // <----- Aquí va la nueva línea
    await productRepository.save(product);
    res.status(201).json(product);
  } catch(error) {
    res.status(500).json({
      message: "Error al crear el producto."
    });
  }
};

// Actualizar un producto existente
export const updateProduct = async(req: Request, res: Response) => {
  try {
    const { name, description, price, imgUrl } = req.body; // Tomamos los datos del request
    
    // Buscamos el producto para actualizarlo
    const product = await productRepository.findOneBy({
      id: parseInt(req.params.id)
    });

    // Validamos que product tenga información
    if (product) {
      product.name = name ?? product.name;
      product.description = description ?? product.description;
      product.price = price ?? product.price;
      product.imgUrl = imgUrl ?? product.imgUrl; // <----- Aquí va la nueva línea
      await productRepository.save(product); // Guardamos los cambios del producto
      res.json(product);
    } else {
      res.status(404).json({
        message: "No se encontró el producto."
      });
    }
  } catch(error) {
    res.status(500).json({
      message: "Error al actualizar el producto."
    });
  }
};
```

## [Volver al Menú](../../README.md)
