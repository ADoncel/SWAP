Ejercicios propuestos para el Tema 2
====================================
Antonio Doncel Campos
------------------------------------

##2.1 Calcular la disponibilidad del sistema si tenemos dos réplicas de cada elemento (en total 3 elementos en cada subsistema)
Partimos de un sistema formado por Web, Applications, Database, DNS, Firewall, Switch, un Data Center e ISP con las siguientes disponibilidades: 
* Web: 85%
* Applications: 90%
* Database: 99.9%
* DNS: 98%
* Firewall: 85%
* Switch: 99%
* Data Center: 99.99%
* ISP: 95%

Utilizaremos la fórmula **As = Ac1 + ((1 - Ac1) * Ac2)** para medir la mejora de un elemento al replicarlo y **As = Ac1 * Ac2 * Ac3 * ... * Acn** que mide la disponibilidad final de sistema.

Si añadimos una replica de cada componente: 
* Web: 0.85 + (1-0.85) * 0.85 = 0.9775
* Applications: 0.9 + (1-0.9) * 0.9 = 0.99
* Database: 0.999 + (1-0.999) * 0.999 = 0.999999
* DNS: 0.98 + (1-0.98) * 0.98 = 0.9996
* Firewall: 0.9775 (La misma que el componente Web).
* Switch: 0.99 + (1-0.99) * 0.99 = 0.9999
* Data Center: 0.9999 + (1-0.9999) * 0.9999 = 0.99999999
* ISP: 0.95 + (1-0.95) * 0.95 = 0.9975

Disponibilidad al replicar una vez: 94.3%

Si añadimos otra réplica tendremos: 
* Web: 0.0.9775 + (1-0.9775) * 0.85 = 0.996625
* Applications: 0.99 + (1-0.99) * 0.9 = 0.999
* Database: 0.999999 + (1-0.999999) * 0.999 = 0.999999999
* DNS: 0.9996 + (1-0.9996) * 0.98 = 0.999992
* Firewall: **0.996625** (La misma que el componente Web).
* Switch: 0.9999 + (1-0.9999) * 0.99 = 0.999999
* Data Center: 0.99999999 + (1-0.99999999) * 0.9999 = 0.999999999999
* ISP: 0.9975 + (1-0.9975) * 0.95 = 0.999875

Disponibilidad al replicar por segunda vez: 99.213%

##2.2 Buscar frameworks y librerías para diferentes lenguajes que permitan hacer aplicaciones altamente disponibles con relativa facilidad.
##Como ejemplo, examina PM2 https://github.com/Unitech/pm2 que sirve para administrar clústeres de NodeJS.
1. **NodeJS:** PM2.
2. **Java:** JBoss.
3. **JavaScript:** AngularJS.
4. **Python:**: Django, TurboGears.
5. **PHP:** Yii, PHPOpenbiz, CakePHP.
6. **Otras**
	* Juno OS: Librería de alta disponibilidad para comunicaciones basadas en intercambio de paquetes.
	* Nagios XI: Librería incluída en Nagios para implementar rutinas de alta disponibilidad.
	* UltraMonkey, Linux Virtual Server: Frameworks para alta disponibilidad en GNU/Linux.

##2.3 ¿Cómo analizar el nivel de carga de cada uno de los subsistemas en el servidor? Buscar herramientas y aprender a usarlas.**
* LoadRunner: Software propietario de HP para medir carga en servidores.
* ApacheBench: Herramienta creada por la fundación Apache para realizar pruebas de carga.
* Siege: Creada por JoeDog Software.
* HeavyLoad: Software libre para realizar pruebas de carga a servidores web.

##2.4 En este ejercicio debemos buscar diferentes tipos de productos:**
Buscar ejemplos de balanceadores software y hardware (productos comerciales):
* Software: Kemp, HAProxy, LVS (Linux Virtual Server), Nginx, Pound, Pen, Zen Load Balancer. 
* Hardware: CISCO, F5 BIG-IP LTM, Radware AppDirector, Ondemand Switch, Coyote Point, Barracuda, etc.

Buscar productos comerciales para servidores de aplicaciones:
* GlassFish, Java EE, Microsoft .Net, BEA WebLogic, IBM WebSphere, Sun-Netscape IPlanet, Sun One, Orace IAS, HP Bluestone, Base4 Server o Zope (Código abierto).

Buscar productos comerciales para servidores de almacenamiento:
* HP ProLiant, Amazon EC2, Windows Azure, Dell PowerEdge, Lenovo ThinkServer, FlyTech, etc.