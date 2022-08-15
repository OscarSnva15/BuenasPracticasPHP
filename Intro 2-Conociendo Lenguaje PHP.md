# Conociendo Lenguaje PHP

### Etiquetas de cierre y apertura

Para definir que un archivo debe ser interpretado en php

```php
<?php
//Aqui irá todo el contenido del lenguaje PHP
?>
```

La anterior opcion, se sugiere como alternativa recomenda, puesto que independientemente del valor establecido en **short_open_tag** en el php.ini, funcionará por defecto y sin necesidad de modificar el archivo php.ini, en cualquier servidor.

Por otr lado otras ventajas son;

1.-La utilización de XML en el servidor ya que el lenguaje XML utiliza como etiquetas de apertura y cierre , <? y ?>. Alternativamente, permite también <?xml y ?>. Por lo tanto, utilizando <?php permite ejecutar código XML como tal.

2.- Evita tener que embeber código XML dentro de PHP.

3.- Es una forma de definir un lenguaje estandar de PHp.

**AVISO** : par poder utilizar XML(además de PHP), se recomienda establecer el valor de **short_open_tag** en **Off**, en el archivo php.ini, puesto que el valor por defecto se encuentra estabñecido en **ON**.

-->Embeber código se refiere a hacer un print (o echo) con PHP, Para escribir utilizando otro lenguaje. Es una de las practicas de programación mas desancosejadas. ya que dificulta la lectura dl codigo haciendo dificil la escalabilidad y mantenimiento de aplicaciones.

**Aviso** Notesé que no existe posibilidad de moficar **short_open_tag** en tiempo de ejecución.

conocer el valor actual de short_open_tag, ejecutar el siguiente comando.

```php
php -r 'echo phpinfo();' | grep short_opeb_tag
```

una forma resumida de lo anterior se puede resumir como acontinuación se muestra.

```
php -i | grep short_open_tag
```

Dondel el parametro **-i** da la misma salida que **phpinfo()**

De este tema abordado anteriormente tambien se tiene que podemos buscar este valor en el archivo.ini directamente.

```powershell
grep short_open_tag /etc/php5/apache2/php.ini
```

**Aviso:** Remplace /ect/php5/apache2/php.ini por la ruta del php.ini en su servidor, de ser necesario.


