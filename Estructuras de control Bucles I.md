# Estructuras de control Bucles I

Recorer posisiciones, **Foreach** es un constructor nativo de php, que permite realizar operaciones iterativas (ciclicas) con matrices., recorriendo uno a uno los elementos de una matriz, comenzando por el primer elemento.

```php
foreach($array as $valor_por_elemento){
    //algoritmo a realizar con cada uno de los elementos
}
```

Dónde array será el nombre de la matriz a ser iterada y valor_por_elemento, un nombre que utilizaremos como identificador del elemento, el cual retornará su valor.

```php
$nombres_propios = array('Ana', 'Julia', 'Luisa', 'Alberto', 'Cecilia',
'Carlos',);
foreach($nombres_propios as $nombre) {
echo $nombre . chr(10);
}
/*
Salida:
Ana
Julia
Luisa
Alberto
Cecilia
Carlos
*/
```

Es posible tambien, iterar obteniendo las claves de cada elemento, ademas de su valor. Para ello, se utiliza la siguiente sintaxis:

```
foreach($array as $clave => $valor) {
// algoritmo a ejecutar en cada iteración
}
```

un ejemplo de iteración compleja con foreach

```php
$datos_de_juan = array('Apellido' => 'Pérez',
'Fecha de nacimiento' => '23-11-1970',
'Teléfonos' => array('Casa' => '4310-9030',
'Móvil' => '15 4017-2530',
'Trabajo' => '4604-9000'),
'Casado' => True,
'Pasaporte' => False,);

foreach($datos_de_juan as $titulo => $dato) {
    if(!is_array($dato)) {
        if($dato === True) {
            $dato = 'SI';
        }else if ($dato === False) {
            $dato = 'NO';
        }
        echo "{$titulo}: {$dato}" . chr(10);
    } else {
            foreach($dato as $tipo_telefono => $numero) {
            echo "Teléfono {$tipo_telefono}: {$numero}" . chr(10);
       }
    }
}
```

La funcion **is_array($array)** nos permite evaluar una variable y conocer si es de tipo "array". Devuelve TRUE si efectivamente es un array y FALSE  en casi contrario.

### WHILE

Así como foreach puede parecer uno de los bucles más complejos, while, resulta ser el más simple de todos.

While, simplemente evaluará de forma booleana (true o false) una expresión de iterativamente, hasta que la expresión evaluada retorne False, y parará

Su sisntaxis en la siguiente:

```php
while (expresión) {
// algoritmo a ejecutar hasta expresión retorne False

}
/*
mientras que (esta condición se cumpla) {
hacer esto
}
*/

$n = 0;
while ($n <= 5) {
echo $n . chr(10);
$n++; // incremento el valor de $n en 1. Equivale a $n = $ + 1;
}
```

Funcion **strtoupper()** , nativa de php coloca u convierte los caracteres de un string en MAYUSCULAS

POR EXAMPLE:

```php
$nombres = array('Ana', 'Julia', 'Luisa', 'Alberto', 'Cecilia', 'Carlos',);
foreach($nombres as &$nombre) {
    $nombre = strtoupper($nombre);
}
print_r($nombres);
/*
Array
(
[0] => ANA
[1] => JULIA
[2] => LUISA
[3] => ALBERTO
[4] => CECILIA
[5] => CARLOS
)
*/
```

bucle while, la misma sinatxis que en otros lenguajes.

pero , Vale la pena hacer notar, que si al iniciar una iteración con while, la primera expresión es falsa, no se continuará ejecutando el bucle.

```php
$years = array();
$year = 1990;
while ($year < 1990) {
$years[] = $year;
$year++;
}
print_r($years);
```

Do while: funciona de manera prácticamente idéntica La única diferencia, el algoritmo iterativo se ejecutará sí o sí, una vez al comienzo y luego, evaluará la expresión, y volverá a ejecutar el algoritmo si la expresión es verdadera.

```php
do {
/* algoritmo a ejecutarse al principio de la iteración
y toda vez que expresión sea verdadera
*/
} while ($expresion);


/*
Lectura humana:
hacer {
    esto, la primera y vez y luego hacerlo...
}mientras que (esta condición se cumpla);
*/
```

Bucle for funciona de la misma forma que en otros lenguajes js, c,java

# goto

es un “operador” al que podríamos llamar “ operador sintáctico”, que se utiliza para “**saltar**” a una zona específica del programa, vea el ejemplo siguiente

```php
<?php
echo "Hola Mundo!";
goto mi_etiqueta;
echo "Esto no se mostrará, ya que goto lo saltará";

mi_etiqueta:
    echo chr(10) . "Esto sí será mostrado" . chr(10);
    goto ya_basta_de_ejecutarse;

otra_etiqueta:
echo "Ahora ya no voy a imprimirme!" . chr(10);

ya_basta_de_ejecutarse:
exit();
?>
```
