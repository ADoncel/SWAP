Ejercicios propuestos para el Tema 7
====================================
Antonio Doncel Campos
------------------------------------

**7.1 ¿Qué tamaño de unidad de unidad RAID se obtendrá al configurar un RAID 0 a partir de dos discos de 100 GB y 100 GB?
¿Qué tamaño de unidad de unidad RAID se obtendrá al configurar un RAID 0 a partir de tres discos de 200 GB cada uno?**

*Con dos discos de 100GB se obtiene un RAID 0 de 200GB de capacidad.
*Con tres discos de 200GB se obtiene un RAID 0 de 600GB de capacidad.

**7.2 ¿Qué tamaño de unidad de unidad RAID se obtendrá al configurar un RAID 1 a partir de dos discos de 100 GB y 100 GB?
¿Qué tamaño de unidad de unidad RAID se obtendrá al configurar un RAID 1 a partir de tres discos de 200 GB cada uno?**

*Al ser un RAID 1 se tratan como hardware independiente, por tanto sería 100GB.
*Al ser un RAID 1 se tratan como hardware independientes, por tanto sería 200GB.

**7.3 ¿Qué tamaño de unidad de unidad RAID se obtendrá al configurar un RAID 5 a partir de tres discos de 120 GB cada uno?**

*Como se trata de un RAID5, se usa uno para la paridad de los datos. Por tanto, seria 120 + 120 = 240GB, siendo el último de 120GB el que se mantendrá para la paridad de los datos.

**7.4 Buscar información sobre los sistemas de ficheros en red más utilizados en la actualidad y comparar sus
características. Hacer una lista de ventajas e inconvenientes de todos ellos, así como grandes sistemas en los que se utilicen.

Configurar en una máquina virtual un servidor NFS. Montar desde otra máquina virtual en la misma subred la carpeta exportada y comprobar que ambas pueden acceder a la misma para lectura y escritura.**

* NFS es un protocolo de nivel de aplicación, según el Modelo OSI. Es utilizado para sistemas de archivos distribuido en un entorno de red de computadoras de área local. Posibilita que distintos sistemas conectados a una misma red accedan a ficheros remotos como si se tratara de locales. Entre sus características destacan: 
**1** El sistema NFS está dividido al menos en dos partes principales: un servidor y uno o más clientes. Los clientes acceden de forma remota a los datos que se encuentran almacenados en el servidor.
**2** Las estaciones de trabajo locales utilizan menos espacio de disco debido a que los datos se encuentran centralizados en un único lugar pero pueden ser accedidos y modificados por varios usuarios, de tal forma que no es necesario replicar la información.
**3** Los usuarios no necesitan disponer de un directorio “home” en cada una de las máquinas de la organización. Los directorios “home” pueden crearse en el servidor de NFS para posteriormente poder acceder a ellos desde cualquier máquina a través de la infraestructura de red.
**4** También se pueden compartir a través de la red dispositivos de almacenamiento como disqueteras, CD-ROM y unidades ZIP. Esto puede reducir la inversión en dichos dispositivos y mejorar el aprovechamiento del hardware existente en la organización.
**5** Todas las operaciones sobre ficheros son síncronas. Esto significa que la operación sólo retorna cuando el servidor ha completado todo el trabajo asociado para esa operación. En caso de una solicitud de escritura, el servidor escribirá físicamente los datos en el disco, y si es necesario, actualizará la estructura de directorios, antes de devolver una respuesta al cliente. Esto garantiza la integridad de los ficheros.

Fuente: http://es.wikipedia.org/wiki/Network_File_System

* Samba es una reimplementación del protocolo de red SMB/CIFS. Facilita el intercambio de ficheros y de impresoras entre sistemas Linux y Windows, o entre sistemas Linux -como una alternativa a Nfs. Se configura fácilmente. Más información en http://en.wikipedia.org/wiki/Server_Message_Block

* AFS ("Andrew File System") o AFS1 es un sistema de archivos distribuido a través de la red que fue desarrollado como parte del proyecto Andrew por la Universidad Carnegie Mellon.2 Su nombre proviene de Andrew Carnegie y Andrew Mellon. Es utilizado fundamentalmente en entornos de computación distribuida. Más información en http://es.wikipedia.org/wiki/Andrew_File_System