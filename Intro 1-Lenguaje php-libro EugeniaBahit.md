# El lenguaje php, libro - Eugenia Bahit

El conjunto de tecnologias que conforman la creacion de una aplicacion web, se enfocan en: Sistema operativo, Servidor Web, Servidor de bases de datos, Lenguaje de programación alto de alto nivel.

Generalmente se conocen dos conjuntos de tecnologias a las que se pueden nombrar como siguiente.

**GLAMP** estas siglas representan un conjunto de tecnologias que entendido lo anterior son: sistema operativo **GNU/LINUX**   servidor web **Apache**   servidor de BD **MySQL** Lenguaje de Programación hibrido multiparadigma**PHP**

**WAMP** estas siglas representan un conjunto de tecnologias que entendido lo anterior son: sistema operativo **Windows** servidor web **Apache** servidor de BD **MySQL** Lenguaje de Programación hibrido multiparadigma **PHP** 

La mayoría de las veces, encontraremos bibliografía que al momento de referirse a las tecnologías GLAMP, suprimen la “G” del comienzo, cometiendo el grave error de llamarlas simplemente LAMP. (En el caso unicamente de GLAMP)

### Diferencia entre GNU/Linux y Linux

Linux es un kernel, es decir, el nucleo de un Sistema Operativo. mientras que GNU/LINUX, es el sistema operativo que utiliza el Kernel Linux como nucleo.

El Kernel Linux, parte fundamental del Sistema Operativo, fue  desarrollado por Linus Torvals, utilizando como modelo a UNIX. Una de las diferencias fundamentales entre los núcleos Linux y UNIX, es que el primero, es Software Libre, mientras que el segundo no lo es.

Por otra parte, mientras existe un único Kernel Linux (con versiones diferentes), existen decenas y hasta cientos de distribuciones GNU/Linux, es decir, diferentes Sistemas Operativos basados en el Kernel Linux, entre las cuales se destacan: Debian, Ubuntu, Kubuntu, Fedora, Gentoo, Slackware, CentOS, ArchLinux, Asturix, entre otros cientos.

La Free Software Foundation, organización sin fines de lucro, fundada por Richard **Stallman**, principal precursor del Software Libre, es el organismo que creó, difunde y promueve, el Sistema Operativo GNU/Linux, a través del Proyecto GNU.

## Preparación del Entorno-Environment

### 1.- Instalacion de sistema Operativo GNU/LINUX

Cabe mencionar que en este pado fue realizada la instalación de un sistema operativo GNU/LINUX, (En este caso para fines practicos UBUNTU).

### 1 .- Instalacion de Apache en Ubuntu

Una vez en la terminal del sistema GNU/LINUX, Lo primero que haremos, sera asegurarnos de actualizar los repositorios asi tambien paquetes existentes en el sistema.

```powershell
sudo apt-get update
```

Ingresamos la contraseña de nuestro sistema.

**sudo**: te convierte en super usuario. Único usuario que tiene permisos para instalar paquetes en tu sistema operativo.

apt-get: es la utilidad para manejar paquetes en distribuciones GNU/Linux basadas en Debian. Alternativamente, puede utilizar el comando **aptitude **.

**update**: opción de apt-get que sincroniza los archivos del índice de paquetes con los repositorios oficiales (dicho de otra forma, obtiene un índice de actualizaciones)

--->Recuerda: siempre, antes de instalar cualquier paquete, debes ejecutar previamente, los comandos sudo apt-get update y luego sudo apt-get upgrade.

### Ahora si intalación de Apche, Para ello, realizamos lo siguiente.

En la terminal misma escribimos:

```powershell
sudo apt-get install apache2
```

**install**es la opción de **apt-get** que indica que se instalará uno o más paquetes **apache2** es el nombre del paquete que se instalará.

Para asegurar o corroborar la instalación de Apache correctamente y esta este funcionando, escribimos.

```powershell
sudo /ect/init.d/apache2 start
```

#### other opction of Apache

**Iniciar Apache**

```powershell
sudo /etc/init.d/apache2 start
```

**Apagar Apache**

```powershell
sudo /etc/init.d/apache2 stop
```

**Reiniciar Apache**

```powershell
sudo /etc/init.d/apache2 restart

//se debe utilizar siempre, tras realizar alguna modificación a
Apache
```

### well done::::

Cuando Apache ha sido instalado e inicializado, podremos ver la pagina de bienvenida, ingresando la URL http://localhost o http://127.0.0.1 en nuestro navegador de internet.

desde la terminal es posible abrir una URL en Firefox desde la terminal, escribiendo:

```powershell
firefox http://127.0.0.1 or https://www.google.com
```


