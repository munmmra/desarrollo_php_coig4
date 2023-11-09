1.- Se realiza la instalación de XAMPP
2.- descargar CodeIgniter
3.- extraer los archivos y renombrar la carpeta con el nombre del proyecto
4.- mover la carpeta al acceso público del servidor (htdocs, en el caso de xampp para Windows)
5.- modificar el archivo App.php del proyecto, ../app/Config/App.php
    @public string $baseURL = 'http://localhost/nombre del proyecto/public/';
6.- agregar la siguiente linea en el archivo config.inn de xampp
    ;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;
    ;activación de code ignite    ;;
    ;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;
    extension = intl
7.- reiniciar el servidor
8.- crear una copia del archivo env
9.- renombrer el archivo env a .env
10.- importamos el controlador en el archivo app/Config/Routes.php en la seccrión
     correspondiente
     #use App\Controllers\nombre del archivo que contiene el controlador;
     @use App\Controllers\Pages;
    
10.- agregar rutas en el archivo app/Config/Routes.php
    # $routes->get('nombre del controlador',
                   [nombre del controlador::class, 'metodo que manejara la solicitud']);
    @$routes->get('pages', [Pages::class, 'index']);
    !ruta con parámetros
    # $routes->get('(:placeholder)',
                   [nombre del controlador::class, 'metodo que manejara la solicitud']);
    # $routes->get('(:segment)', [Pages::class, 'view']);
11.- Creaar un nuevo archivo para el definir el controlado 
    # app/Controllers/Nombre_del_controlador.php
12.- Crear una vista app/Views/templates/header.php


    

