# Linux para ciberseguridad

## Tabla de contenido

- [¿Que es un sistema operativo?](#¿que-es-un-sistema-operativo)
- [¿Que es el codigo abierto?](#¿que-es-el-codigo-abierto?)
- [¿Que es una distribucion?](#¿que-es-una-distribucion)
- [Distribuciones basadas en otras](#distribuciones-basadas-en-otras)
- [Estructura de linux](#estructura-de-linux)
- [Componentes del sistema de ficheros](#componentes-del-sistema-de-ficheros)
- [Otros conceptos clave](#otros-conceptos-clave)

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
