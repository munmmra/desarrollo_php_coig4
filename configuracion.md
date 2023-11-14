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
13.- Crear en phpmyadmin la base de datos
14.- crear la tabla 
    CREATE TABLE news (
        id INT UNSIGNED NOT NULL AUTO_INCREMENT,
        title VARCHAR(128) NOT NULL,
        slug VARCHAR(128) NOT NULL,
        body TEXT NOT NULL,
        PRIMARY KEY (id),
        UNIQUE slug (slug)
    );
15.- ingresamos información de trabajo
    INSERT INTO news VALUES
    (1,'Elvis sighted','elvis-sighted','Elvis was sighted at the Podunk internet cafe. It looked like he was writing a CodeIgniter app.'),
    (2,'Say it isn\'t so!','say-it-isnt-so','Scientists conclude that some programmers have a sense of humor.'),
    (3,'Caffeination, Yes!','caffeination-yes','World\'s largest coffee shop open onsite nested coffee shop for staff only.');
16.- realizar la configuración de la base de datos en el archivo .env
    database.default.hostname = localhost
    database.default.database = nombre de la base de datos
    database.default.username = usuario
    database.default.password = contraseña
    database.default.DBDriver = MySQLi
17.- crear el modelo, en el directorio app/Models crear el modelo
    @NewsModel.php
18.- definición del métodos para el manejo de la interacción con la base de datos
    public function getNews($slug = false)
19.- creamos la ruta que accedera a las noticias en el archivo de las rutas
        @use App\Controllers\News; // Add this line
        @$routes->get('news', [News::class, 'index']);           // Add this line
        @$routes->get('news/(:segment)', [News::class, 'show']); // Add this line
20.- creación del controlador News
        @app/Controllers/News.php
21.- creacion de lavista para desplegar la informacion del controlador News, en la ruta
    @app/Views/news/index.php
22.- crear la vista para mostrar la informacion del controlador News en la ruta vew
    @app/Views/news/view.php
23.- activar el CSRF en el archivo app/Config/Filters.php
24.- agregar las rutas al archivo app/Config/Routes.php para la creación de nuevas noticias
25.- crear la vista para el formulario de creación de noticias
    @app/Views/news/create.php
25.- agregar el método new() en el controlador News
26.- crear el metodo create() en el controlador News






    

