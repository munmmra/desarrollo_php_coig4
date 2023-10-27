1.- Se realiza la instalación de XAMP
2.- descargar CodeIgniter
3.- extraer los archivos y renombrar la carpeta con el nombre del prollecto
4.- modificar el archivo App.php con la ruta de nuestro prollecto
    @public string $baseURL = 'http://localhost/nombre del proyecto/';
5.- agregar la siguiente linea en el archivo config.inn de xamp
    ;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;
    ;activación de code ignite    ;;
    ;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;
    extension = intl
6.- reiniciar el servidor