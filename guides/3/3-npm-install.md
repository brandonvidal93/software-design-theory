# Node JS

# Instalar librerías

Es importante tener presente que, cuando hacemos **`git clone`** de algún Repositorio de otro desarrollador o ya sea nuestro. Por lo general la carpeta **`node_modules`** no se descarga y debemos instalar las librerías en nuestro equipo, sino, el Repositorio no podrá funcionar correctamente.

En todo Repositorio donde se manejen librerías, se deben instalar con el comando **`npm install`**, siguiento estos pasos:

1. Nos ubicamos en la carpeta donde tenemos los archivos de nuestro proyecto y damos **clic** en la ruta de ubicación, borramos la dirección y escribimos **`(CMD)`**

![alt text](../../img/3/image-3.png)

![alt text](../../img/3/image-4.png)

2. Presionamos la tecla **`Enter`**, esto abrirá la Terminal de Windonws en la ruta de nuestro proyecto.

![alt text](../../img/3/image-5.png)

**Nota:** Debemos fijarnos que estemos ubicados en la ruta del proyecto para continuar con el proceso.

3. En la Terminal escribimos el siguiente comando:

```bash
npm install
```

4. Presionamos la tecla **`Enter`** para que comience el proceso de instalación. Si todo se ejecuta correctamente se descargarán las librerías del proyecto que se encuentran registradas en el **`package.json`**.

## [Volver al Menú](../../README.md)