# Trabajando HTML con PHP en un mismo archivo

Como se comentó anteriormente, es posible "mezclar" código HTML con PHP, sin necesidad de imprimir etiquetas HTML mediante PHP. Es decir, conservar la independencia de ambos lenguajes en el mismo archivo.

El mejor procedimiento para hacer esto, es comenzar escribiendo el código HTML y utilizando comentarios para recordarnos dónde debemos insertar el código PHP

vease como realizar esto acontinuacion:

```php
<?php
$alicuota_iva = 21;
$codigo_de_producto = 1284;
$nombre_producto = "Agua Mineral Manantial x 500 ml";
$precio_bruto = 3.75;
$iva = 3.75 * 21 / 100;
$precio_neto = $precio_bruto + $iva;
?>
<!doctype html>
<html>
<head>
     <title>Detalles del producto <?php echo $nombre_producto; ?></title>
</head>
<body>
     <p><b>Producto:</b> (<?php echo $codigo_de_producto; ?>)
     <?php echo $nombre_producto; ?><br/>
     <b>Precio:</b> USD <?php echo $precio_neto; ?>.- (IVA incluido)</p>
</body>
</html>
```

como se pudo observar con anterioridad embeber codigo entre php y html es preferente que dentro del html se inserten adeacuada mente lineas o instruciones php, del contrario embeber codigo html dentro de codigo php es una mala practica.

### php permite incluir archivos

inclusion de archivos em php., PHP nos permite insertar cualquier tipo de archivos con formato de texto, dentro de un archivo PHP.

entre los tipos que podemos insertar son:

**.php, .txt, .htm, .html**

estas cuatro funciones necesitan recibir como parámetro, la ruta local o remota del archvo a ser incluido.

```php
<?php
include("archivo.php, ruta",ruta local);
include_once("archivo.txt",ruta local);
require("archivo.html",ruta local);
require_once("archivo.htm",ruta local);
?>
```

Ejemplos de inclusion de archivos remotos.

```php
<?php
include("http://www.miweb.com/archivo.php?foo=bar");
include_once("http://www.miweb.com/archivo.php");
require("http://www.miweb.com/archivo.html");
require_once("http://www.miweb.com/archivo.txt");
?>
```

funcion si queremos incluir el archivo mi_fichero.php ya interpretado conforme el valor del parameto foo

```php
include("mi fichero.php?foo=15")
```

de lo anterior , php arrojará un error, ya que buscará un archivo llamado mi_fichero.php?foo=15 en vez de interpretarlo.

Sin embargo, podremos incluir remotamente para que se nos devuelva el archivo interpretado, mediante:

```php
include("http://miweb.com/mi_fichero.php?foo=15");
```

### Diferencias entre require() y include()

**include**() intenta importar al archivo indicado y en caso de no poder hacerlo, arroja un error y continúa ejecutando el resto  
del script

**require**(), cuando no logra importar el  archivo indicado, arroja un error y finaliza sin permitir que el resto del script continúe ejecutándose.

### obstantemente php dispone de una funcion que permite almacenar en una variable los valores de un archivo que  ya esta procesado.

```php
$contenido= file_get_contents("http://miweb.com/mi_fichero.php?foo=15");
```

### _once

la única diferencia que existe entre **include **e **include_once()** e **require** y **require_once**, es que si el archivo indicado con "**_once**" ya ha sido incluido no volverá a importarse.

### sintaxis básica para los condicionales en PHP

se resume en :

```php
/*
si condición X se cumple {
    hacer esto;
    // fin de la evaluación
}
*/

//aqui sintaxis basica:

if(condicion A){
    //Algorimo si se cumple condición A
} else if(condición B){
    //algoritmo si se cumple la condicion B
} else {
    //Algoritmo si no se cumplen las condiciones anteriores
    }
}
```

Operadores logicos y de comparación.

ya los hemos visto e igual son los mismos que otras sintaxis de python,java,c,js

### Nota del operador and

lo cierto, es que tanto el operador **and** como el **&&** poseén una precedencia izquierda (es decir, que la condición es evaluada de izquierda a derecha) y lo mismo sucede con **or** y **||**

# 
