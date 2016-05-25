Practica 6 - Discos en RAID
==================================================
Antonio Doncel Campos
--------------------------------------------------

**El objetivo de esta práctica es configurar varios discos en RAID 1.

Hay que llevar a cabo las siguientes tareas:

* Realizar la configuración de dos discos en RAID 1 bajo Ubuntu 12.04, automatizando
el montaje del dispositivo creado al inicio del sistema.
* Simular un fallo en uno de los discos del RAID (mediante comandos con el mdadm),
retirarlo “en caliente”, comprobar que se puede acceder a la información que hay
almacenada en el RAID, y por último, añadirlo al conjunto y comprobar que se reconstruye correctamente.

Adicionalmente, y como tarea opcional para conseguir una mayor nota en esta
práctica, se propone realizar una configuración de servidor NFS. La idea es que la
máquina con el dispositivo RAID sea un servidor NFS y otra máquina monte dicha
unidad usando este protocolo.**

<div align="center"><img src="img/"></div>