EXPLICACION DEL PROYECTO
--

**Instalación**
  para llevar a cabo este proyecto se deben instalar las dependencias tailwindcss, postcss y autoprefixer

  *Tailwind*: Libreria o framework de css

  *postcss*: Manejador de css y frameworks css de un proyecto. Técnicamente es un set de plugins escritos en Javascript (bajo la plataforma NodeJS) que permiten hacer transformaciones en el código CSS de los proyectos. Es decir a un CSS de entrada, obtenemos un CSS de salida, que lógicamente estará más optimizado o aumentará sus prestaciones por diversos motivos

  *autoprefixer*: permite aplicar los prefijos CSS que sean necesarios al código fuente, de modo que nos ahorra trabajo y mantiene una mejor compatibilidad con los navegadores actuales y antiguos.

  **Archivos**
  Dentro del proyecto se crearán 2 archivos que serán las especificaciones de los estilos, contendran detalles, plugins, y demas cosas

  1) tailwind: se crea ejecutando npx tailwindcss init, aquí se guardará lo siguiente:

    ```
      /** @type {import('tailwindcss').Config} */
      module.exports = {
        content: ["./src/**/*.{html,js}"],
        theme: {
          extend: {},
        },
        plugins: [],
      }
    ```

  2) postcss: se crea ejecutando touch postcss.config.js, tambien se puede crear a mano jaja, aquí se guardará lo siguiente:

    ```
      module.exports = {
        plugins:[
          require("tailwindcss"),
          require("autoprefixer")
        ]
      }  
    ```

  **Carpeta CSS**
  Dentro de esta se guardara un archivo css (con cualquier nombre, en este caso sera **"miEstilo.css"**)  en el cual se alojaran las importaciones de tailwind

  ```
    @tailwind base;
    @tailwind components;
    @tailwind utilities;
  ``` 

  **Creación de archivo .HTML**
  Creamos la estructura habitual, pero en su link/css sera enviado a css/style.css

  **package.json/scripts**
  se crea un comando para darle ruta origen-destino al css 
    
  ```
    scripts: {
      "build": "postcss css/miEstilo.css -o public/css/style.css"
    }
  ```
  todo esto con el objetivo de que cuando ejecutemos npm run build se ejecutará el proyecto y a su vez se creará un archivo public normalizado que incluirá reglas de css basicas para empezar de 0 el proyecto 

**Inicio**
--

**Resoluciones de pantalla**
  Tailwind utiliza estos patrones de diseño: *responsive design*, *mobile first* y *utility first*. todos con el objstivo de hacer adaptables las vistas para los distintos dispositivos.

  las resoluciones en tailwind son las siguientes
  - DEFAULT, de 0px en adelante
  - SMALL (sm), de 640px en adelante.
  - MEDIUM (md), de 760px en adelante. 
  - LARGE (lg), de 1024px en adelante.
  - XLARGE (xl), de 1280px en adelante. 
  - X2LARGE (2xl), de 1536px en adelante.

  estos datos se pueden cambiar en los extends 



