Ejercicios propuestos para el Tema 3
====================================
Antonio Doncel Campos
------------------------------------

##3.1 Buscar con qué órdenes de terminal o herramientas gráficas podemos configurar bajo Windows y bajo Linux el enrutamiento del tráfico de un servidor para pasar el tráfico desde una subred a otra.

Para Linux he encontrado dos tutoriales diferentes uno usando iptables y otro creado scripts de balanceo en apache:
**iptables**: http://www.ite.educacion.es/formacion/materiales/85/cd/linux/m6/enrutamiento_en_linux.html
**scripts apache**: https://www.youtube.com/watch?v=U1cm9xH5r_Q

Bajo Windows no he conseguido encontrar como realizar el balanceo por comandos ya que cuenta con una herramienta grafica propia llamada **Network Load Balancer (NLB)**: https://technet.microsoft.com/en-us/library/cc770558.aspx

Las herramientas externas para los distintos operativos que se han encontrado son: 
* Quagga.
* XORP.
* GNU Zebra.
* HAProxy.
* Azure Load Balancer.

##3.2 Buscar con qué órdenes de terminal o herramientas gráficas podemos configurar bajo Windows y bajo Linux el filtrado y bloqueo de paquetes.
**Linux** Comandos: iptables, ip o tc.
**Windows** Comando: route.
**Herramientas gráficas:**
	* Shorewall.
	* WireShark.
	* PRTG.
	* CocoaPacket Analyzer.
	* Acrylic Wifi.