# Lenguaje de servidor PHP

Instrucciones: se ejecutan en una sola linea.

Estructuras de control: son las que contienen instruciones.

```php
<?php
estructura de control {
instrucción 1;
instrucción 2;
}
?>
```

Estandarización del codigo

Como regla de estilo, se sugiere utilizar identación de 4 espacios en blanco y dejar una línea en blanco, entre estructuras de control

```php
<?php
estructura de control 1 {            
    instrucción a;
        
    estructura de control 1.1 {
        instrucción b;

        estructura de control 1.1.1{
            instrucción c;
        }
    }
    estructura de control 1.2 {
        instrucción d;
    }
}
estructura de control 2 {
    instrucción e;
}
?>
```

### variables y tipos de datos

puede almacenar datos de los cuales ya hemos conocido como en js, java, c.

Una varaible se puede **crear**,**definir**, **modificar** y **eliminar**

**crear una varible:**

Las variables en PHP se definen anteponiendo el sigo dólar ($) seguido del nombre que se le quiera dar a esta.

```php
$nombre
```

del mismo modo reglas de declaracion, no espacios, no caracteres especiales, unicamente guiones bajos.

**Asignar valores a una variable**:

Para asignar valor a una variable, se coloca el sigo igual (=) segudio del valor

```php
<?php
$datoEdad = 10;
$datoMensaje = "Hola"
$datoStatus = False;
$vence = True;
$stock_deposito_27 = 25;
?>
```

Es posible tener el valor de una variable asignado a una variable

```php
<?php
$nombre_de_producto_por_defecto = "Producto alimenticio";
$nombre_producto = $nombre_de_producto_por_defecto;
echo $nombre_producto; // imprime: Producto alimenticio
?>
```

concatenar valores entre variables

```php
<?php
$nombre_de_producto_por_defecto = "Producto";
$nombre_producto = "{$nombre_de_producto_por_defecto}s en oferta";
echo $nombre_producto; // imprime: Productos en oferta
?>
```

concatenacion de variables para salida de mensajes

```php
<?php
$codigo_de_producto = 1284;
$nombre_producto = "Agua Mineral Manantial x 500 ml";
$precio = 3.75;
$vence = False;
$hay_stock = True;
$stock_en_deposito_1 = 20;
$stock_en_deposito_27 = 5;
$stock_en_deposito_73A = 54;
//the next instrucion is interesting. how concat
$detalles_del_producto = "(" . $codigo_de_producto . ") " .
$nombre_producto . ". Precio: USD " . $precio . ".-";
?>
```

### NULL, var_dump() , isset()

No solo es posible modificar el valor de una variable. También  
es posible:

Vaciar su contenido

```php
<?php
$producto = "Coca-Cola x 1,5 Lt.";
//de esta forma siguiente se vacia la variabl, pero manteniendo su tipo de valor
$producto = "";
```

Vaciarla sin conservar su tipo

```php
$producto = "Coca Cola x1,5 Lts"
//ACONTINUACION COMO SE MUESTRA SE VACIARA LA VIABLE SIM CONSERVAR SU TIPO
$producto = NULL
```

eliminar (destruirla) por completo

```php
<?php
$producto = "Coca-Cola x 1,5 Lts.";
se elimina la variable de la forma siguiente.
unset($producto);
?>
```

PHP nos permite conocer el tipo y valor de una variable, mediante la función var_dump()

```php
<?php
$producto = "Coca-Cola x 1,5 Lts.";
var_dump($producto);
# salida: string(20) "Coca-Cola x 1,5 Lts."
```

get type para conocer el tipo de valor en una vairable

```php
<?php
$a = 25;
$tipo_a = gettype($a);
echo $tipo_a; #imprimirá integer
?>
```

Sabe con **isset**  si sgue existiendo una variable, esta devolverá TRUE si ha sido definida y no es NULL la variable. de lo contrario retornará FALSE



```php
<?php
$producto = "Coca-Cola x 1,5 Lts.";
echo isset($producto);
# retorna True
$producto = "";
echo isset($producto);
# Retorna True
$producto = NULL;
echo isset($producto);
# retorna False
unset($producto);
echo isset($producto);
# retorna False
?>
```

Cuando una variable ya no es necesaria, debe priorizarse el uso de unset sobre NULL, ya que con unset(), se libera la dirección de la memoria en la cual había sido escrita dicha variable.

### Operadores aritmeticos son los mismos que hemos visto en lenguajes de Java, JS, C

### Buenas practicas Recordar para la estandarización de un código:

Utiliza nombres descriptivos para las variables;

Si el nombre es compuesto, separa cada palabra por un guión bajo;

Escribe los nombres de variables en minúsculas; 

Cuando debas asignar múltiples valores a una variable,  utiliza una sola instrucción toda vez que sea posible;

Utiliza comillas dobles para encerrar las cadenas de texto, en vez de comillas simples;

Utiliza espacios en blanco antes y después de un operador aritmético para facilitar la lectura;

### Convertir mediante una función el tipo de una ariable,

```php
//sintaxis
settype($variable, "nuevo_tipo"):
```

```php
$a = "33 Manzanas";
settype($a, "integer");
var_dump($a)

//salida int(33)
```


