# Linux para ciberseguridad

## Tabla de contenido

- [¿Que es un sistema operativo?](#¿que-es-un-sistema-operativo)
- [¿Que es el codigo abierto?](#¿que-es-el-codigo-abierto?)
- [¿Que es una distribucion?](#¿que-es-una-distribucion)
- [Distribuciones basadas en otras](#distribuciones-basadas-en-otras)
- [Estructura de linux](#estructura-de-linux)
- [Componentes del sistema de ficheros](#componentes-del-sistema-de-ficheros)
- [Otros conceptos clave](#otros-conceptos-clave)
- [¿Que es un comando?](#¿que-es-un-comando)
- [Ficheros mas importantes en linux](#ficheros-mas-importantes-en-linux)
- [Principales directorios en linux](#principales-directorios-en-linux)
- [Variables de entorno](#variables-de-entorno)
- [Comandos de ayuda y soporte](#comandos-de-ayuda-y-soporte)
-
-
-
-
-
-
-
-
-
-
















## ¿Que es un sistema operativo?

Un sistema operativo o SO, es un conjunto de programas que gestionan los recursos de hardaware como la memori, el procesador los dispositovos de entrada y de salida. (de esto se encarga el kernel que viene a ser como el motor y esqueleto de un automovil lo que permite que todo funcione por dentro) el sistema operativo completo ademas del kernel, inclye los comandos, interfaces graficas, bibliotecas para hacer mas amigable lainteraccion con una maquina (el sistema operativo vien a se le volante, sillon, espejos y grenos de nuestro vehiculo permitiendo usarlo de forma comoda y controlada)

## ¿Que es el codigo abierto?

El codigo abierto (Opens source) es un modelo de desarrollo de software basado en la colaboracion abierta,donde el codigo fuente es publico. Ampliando la participacion de terceros permitiendo que estos modifiquen el codigo fuente y compartan esta tecnologia,

## ¿Que es una distribucion?

Una distribucion o distro es un conjunto de software especifico, incluido el sistema operativo ya compilado y configurado para su uso

***Imagen referencial de las distribuciones y su evolucion:*** https://wpollock.com/Unix/us__en_us__ibm100__linux__linux_timeline.pdf

***Informacion de los sistmas operativos y caracteristicas:*** https://archiveos.org/

***Principales cambios y actualizaciones de las distribuciones:*** https://distrowatch.com/

## Distribuciones basadas en otras

Si ya existe la rueda ¿para que re inventarla? lo mejor es usarla y mejorarla, con este pensamiento se parte de distribuciones base como (Debian o Ubuntu y se empiezan agregar o quitar funciones segun las necesidades del proyecto) gracias a esto existe una bifurcacion de distribuciones basadas en distros ya creadas que se adaptan a diferentes necesidades, educativos, empresariales, hacking, de rendimiento, etc.

## Estructura de linux

La estructura de linux se basa en una estructura gerarquica partiendo desde la raiz, en esta estructura todo se representa como un fichero desde: los archivos, los documentos, los dispositivos y procesos. ***Los ficheros almacena datos o configuraciones que influyen directamente en el comportamiento del sistema***. Los ficheros se pueden organizar en particiones, cada uno con su propio sistema de archivos

## Componentes del sistema de ficheros

En el nucleo del sistema de ficheros estan los INODOS, BLOQUES y SUPER BLOQUES

- **INODOS** = Guarda informacion o metadatos de un fichero como permisos, propietarios o tamaño que ocupa (no almacena el nombre del archivo solo su informacion) si los inodos no tienen referencia se pueden usar para guardar informacion de forma oculta no infalible ***inodos huerfanos***

- **BLOQUES** = Unidades de datos donde se guarda la informacion de los ficheros, donde se relacionan el nombre del fichero y numero de direccion del inodo (para saber a nivel de sistema que fichero esta dentro de que directorio)

- **SUPER BLOQUE** = Contiene la informacion crucial del sistema de ficheros, como el tamñano, numero de inodo estado del sistema de archivos, tipo de sistema de archivos (ext4)

## Otros conceptos clave

- *Fichero == Archivo*
- *Directorio == Carpeta*
- **Enlace duro(hard link)**: Referencia adicional al inodo de un archivo existente (Es muy util porque puedo acceder a un archivo desde una carpeta diferente)

- **Enalce blando(soft link)**: Referencia a una ruta o un fichero (Como un acceso directo una o una referencia a la ruta de otro archivo)

**PERMISOS:** Los permisos en linux se dividen en tres: 
- lectura(read): Ver contenido
- escritura(write): Modificar contenido
- ejecucion(Execute): Ejecutar al archivo o acceder a un directorio

Se pueden asignar estos permisos a tres tipos de usuarios dentro del sistema.
1) Propietario(u): Quien creo el fichero o directorio 
2) Grupo(g): Grupo al que pertence el propietario
3) Otros(o): Todos los demas usuarios

**Lo importante y critico son los permisos que tengo no la direccion en la que me encuentro para ejecutar comandos.**

***- Los permisos se asignan de forma octal o simbolica***

***- The quieter you become, the more you are able to hear*** 

## ¿Que es un comando?
Son instrucciones que es usuario envia al sistema operativo atraves de una shell, las cuales generalmente ejecutan un programa o una funcion interna, estos tambien pueden incluir argumento

## Shell vs emulador de terminal
**Emulador de terminal:** Interfaz grafiaca que permite la entrada y salida de texto, y sirve como entorno donde se ejecuta una shell

**Shell:** Interprete de los comandos que el usarion envia para que el sistema opertivo las ejecute ya sea un fragmento de codigo o una funcion

- sh(shell): Una de las primeras shell presente en casi todas las distribuciones.
- bash(Bourne again shell): Ampliamente usada en GNUlinux, Permite hacer scripting avanzado
- zsh: Shell moderna con autocompletado, resaltado y mayor interactividad

El emulador de terminal el canal
La shell es el interprete
El sistema operativo es el ejecutor

## Ficheros mas importantes en linux

- **/etc/passwd** = Contiene informacion basica de los usuarios del sistema (nombre,UID[identificador de usuario], GID[Identificador de grupo])
- **/etc/group** = Lista los grupos del sistema y los usuarios que pertenecen a ellos 
- **/etc/shadow** = Contraseñas de los usuarios encriptadas y configuracion de expiracion 
- **/etc/fstab** = Define como y donde montar las particiones al iniciar el sistema
- **/etc/network/interfaces** = Configura interfaces de red de forma manual
- **/etc/hostname** = nombre del host del sistema (nombre de la maquina)
- **/etc/resolv.conf** = Servidores DNS para traducir los nombres de dominio en otros sistemas con Ubuntu se gestiona con Netplan

## Principales directorios en linux

Hay directorios ocultos y estos empiezan con ./

**/boot** = Informacion necesaria para el arranque del sistema (kernel,GRUB[GNU GRand Unified Bootloader])
**/etc** = Ficheros de configuracion del sistema y aplicaciones
**/var** = Datos variables: logs, correos, cache, colas de imprecion, etc
**/var/log** = Contiene los logs del sistema como syslog, auth.log, etc
**/usr** = Contine ficheros y directorios de uso general para los usuarios del sistema
**/usr/bin** = Comandos y programas ejecutables para todos los usuarios
**/usr/lib** = Librerias necesarias para ejecutar binarios
**/home** = Directorios personales de cada usuarion no-root
**/root** = Directorio personal del usuario root
**/tmp** = Archivos temporales del sistema, descarga de aplicaciones, scripts se limpia al reiniciar
**/dev** = representacion de dispositivos Fisicos [hardaware]
**/sbin** = Ejecutables del sistema y recuperacion, usados por root para administrar

**Directorios delicados/especiales:** 

**/procp** = Sistema de archivos virtual, expone informacion de procesos y kernel en tiempo real
**/sys** = Hardaware del sistema, y control del hardware y del kernel

***/etc configura, /usr ejecuta, /var registra, /dev conecta, /home guarda, /root manda, /proc revela.***

## Variables de entorno
son valores los cuales el sistema y progrmas usan para definir comportamientos, se guardan en memoria y afectan el comportamiento de SO

1)**echo $NOMBRE_VARIABLE** = conocer el contenido de una variable
2)**export VAIABLE=VALOR** = Creacion de una variable y asignacion de un valor
3)**export VARIABLE=NUEVO_VALOR** = Reasignacion de un valor a una variable
4)**unser VARIABLE** = Eliminacion de variable

- **env** = Enlista las variables
- **export** = Crreamos una variable
- **echo** = contenido de una variable
- **unset** = Eliminacion de una variable

***Variables importantes para el entorno:***

- **PATH** = Rutas donde se buscan los ejecutables
- **HOME** = Directorio ***Home*** del usuario
- **USER** = Nombre del usuario actual
- **SHELL** = Shell actual en uso
- **TERM** = Terminal actual en uso
- **EDITOR** = Editor de texto predeterminado

***Variables de entorno persisten***

Son aquellas variables que no se borran cuando se reinicia elsistema. **las variables que defino con export solo estan hasta que la sesion este abierta**

**¿Como hacer variables persistentes?**

Para ello debemos saber que Shell estamos usando podemo ver lo con **echo $SHELL** (o llendo al fichero /etc/passwd y buscar nuestro usuario con la informacion) una vez con esto claro, para crear variables persistente debemos registrarlas en el archio correspondiente de nuestra shell en este caso ***.bashrc*** que es un archivo oculto

1) Nano ~/bashrc
2) export NOMBRE_VARIABLE CONTENIDO
3) Guardamos las modificaciones con ctrl + 0, enter, ctrl + x
4) Recargamos el archivo source ~/bashrc

## Comandos de ayuda y soporte