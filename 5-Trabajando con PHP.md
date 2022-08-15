# 5.-Trabajando con PHP y Matrices

Una matriz (array) es un mapa de datos ordenado que asocia "claves" a sus valores correspondientes. Es así, que estas matrices, nos son de gran utilidad para crear desde
diccionarios de datos hasta árboles de múltiples diccionarios.

**La sintaxis básica**

```php
array(clave => valor, );
```

donde **clave** puede ser un **Entero**

```php
$nombre_de_mujer = array(0 => 'Ana', 1 =>'gabriela', 2=>'Cecilia', );
```

O una **cadena de texto**

```php
$telefonos = array('juan'=> '15 40 14 23 12', javier=> '42 23 69 45',);
```

y como valor pueden ser de cualquier tipo:

```php
$datos_juan = array('apellido'=> 'Pérez', 'Fecha de Nacimiento'=> '23-11-1997',
                          'Telefonos'=> array('casa' => '23,11,1970', 
                                              'Cel' => '55654564'),
                    'casado'=> True, 'Pasaporte'= False,);
```

### Impirmir en pantalla con print_r

para imprimir una matriz completa en pantalla, se puede utilizar la funcion print_r($array):

```php
php > $array = array(0 => 'Ana', 1 => 'Gabriela', 2 => 'Noelia',);

print_r($array);
Array
(
[0] => Ana
[1] => Gabriela
[2] => Noelia
)

```

La forma de declarar un array, es simplemente asignarlo a una variable, teniendo en cuenta, que un array, puede estar inicialmente vacio:

```php
$mi_array = array();
```

Acesso a los items de un array

AVISO:  La sintaxis básica para acceder a un array es  
**array[indice]** o **array['clave']**, 



Los valores de un array pueden no tener explicitamente una clave asociada,

```php
$mi_array = array('Ana', 'Gabriela', 'Julia', 'Noelia');

//en este caso se accedera a ellos mediante el indice

echo $mi_array[3]
//Imprimirá Noelia
```

Modificando Elementos:

```php
$mi_array = array('Ana', 'Gabriela', 'Julia', 'Noelia');
$mi_array[2] = 'Ximena';
echo $mi_array[2; 
//Imprimirá Ximena
```

Agregar valor:

```php
$mi_array = array('Ana', 'Gabriela', 'Julia', 'Noelia');
$mi_array[] = 'Cecilia';
print_r($mi_array);
//El nuevo valor será agregado al final de la lista, cecilia va hasta el final como va lñlegando
```

vease lo anterior asi

```php
print_r($mi_array);
Array
(
    [0] => Ana
    [1] => Gabriela
    [2] => Julia
    [3] => Noelia
    [4] => Cecilia
)
```

si se desea asociar dicho valor a una clave, esta debe inidcarse:

```php
//Tengo mi array definido
$telefonos_de_amigos = array('Juan' => '15 4017-2530',
'Javier' => '4921 – 1200',);


//agregamos un valor al array pero indicando la clave que tendrá
$telefonos_de_amigos['Luis'] = '4321-5012';
$telefonos_de_amigos['Carlos'] = '15 3239-0432';

```

Solo una aclaracion con las claves.

![](C:\Users\oscar\AppData\Roaming\marktext\images\2022-08-14-13-15-51-image.png)

Vale aclarar además, que si por error intentamos agregar un  nuevo elemento, usando como clave o como índice, alguna clave o índice existente, estaríamos MODIFICANDO dicho elemento en vez de estar agregando uno nuevo.
