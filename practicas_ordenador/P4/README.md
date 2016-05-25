Práctica 4 - Comprobar el rendimiento de servidores web
==================================================
Antonio Doncel Campos
--------------------------------------------------

**En esta práctica se deben usar las dos herramientas para medir, primero el
rendimiento de una sola máquina servidora (haciendo peticiones a la IP de la máquina
1, p.ej.), y a continuación el rendimiento de la granja web cuando usamos balanceo de
carga tanto con nginx como con haproxy (haciendo las peticiones a la dirección IP del
balanceador).**

**Todas las ejecuciones se harán desde una máquina independiente a las que forman la
granja web, ya sea un terminal de la máquina anfitriona u otra máquina virtual nueva.**

**Puesto que en la práctica anterior usamos dos programas diferentes para hacer el
balanceo, en esta práctica comprobaremos el rendimiento de la granja web cuando el
balanceador es nginx y también cuando es haproxy, por lo que tendremos tres
baterías de pruebas correspondientes a las tres configuraciones a evaluar: (1) servidor
solo, (2) granja web con nginx, (3) granja web con haproxy.**

**Se harán un mínimo de 10 mediciones para obtener media y desviación estándar con
cada métrica recogida y se mostrarán los resultados en forma de tabla y gráficas para
comparar los resultados obtenidos con las tres configuraciones.**

**Para conseguir una mayor nota en esta práctica se propone buscar alguna otra
herramienta para medir las prestaciones y utilizarla tanto con la máquina individual
como con la granja web. Podemos usar cualquier herramienta de las comentadas al
principio, o bien otra que encontremos o conozcamos.**

**Como resultado de la práctica 4 se mostrará al profesor el funcionamiento de las
herramientas. Asimismo, se redactará un documento en el que se describirán las
baterías de tests realizadas (órdenes ejecutadas, etc), y se mostrarán los resultados
obtenidos (tablas de tiempos, etc).**

Para realizar los benchmark se ha programado este script PHP en ambos servidores.
<div align="center"><img src="img1.-script_S1.png"></div>

Tabla de resultados obtenidos con Apache Benchmark.
<table cellspacing=0 border=1>
    <tr>
    	<td style=min-width:50px>Apache Benchmark Nginx</td>
    </tr>
    <tr>
    	<td style=min-width:50px></td>
        <td style=min-width:50px>Tiempo de test (s)</td>
        <td style=min-width:50px>Solicitudes fallidas</td>
        <td style=min-width:50px>Solicitudes por segundo</td>
    </tr>
    <tr>
        <td style=min-width:50px>T1</td>
        <td style=min-width:50px>3.88</td>
        <td style=min-width:50px>82</td>
        <td style=min-width:50px>257.58</td>
    </tr>
    <tr>
        <td style=min-width:50px>T2</td>
        <td style=min-width:50px>2.49</td>
        <td style=min-width:50px>91</td>
        <td style=min-width:50px>400.54</td>
	</tr>
    <tr>
        <td style=min-width:50px>T3</td>
        <td style=min-width:50px>2.83</td>
        <td style=min-width:50px>89</td>
        <td style=min-width:50px>352.88</td>
    </tr>
    <tr>
        <td style=min-width:50px>T4</td>
        <td style=min-width:50px>2.53</td>
        <td style=min-width:50px>95</td>
        <td style=min-width:50px>393.9</td>
    </tr>
    <tr>
        <td style=min-width:50px>T5</td>
        <td style=min-width:50px>2.43</td>
        <td style=min-width:50px>88</td>
        <td style=min-width:50px>410.02</td>
	</tr>
    <tr>
        <td style=min-width:50px>T6</td>
        <td style=min-width:50px>2.62</td>
        <td style=min-width:50px>103</td>
        <td style=min-width:50px>380.69</td>
	</tr>
    <tr>
        <td style=min-width:50px>T7</td>
        <td style=min-width:50px>2.95</td>
        <td style=min-width:50px>81</td>
        <td style=min-width:50px>338.41</td>
	</tr>
    <tr>
        <td style=min-width:50px>T8</td>
        <td style=min-width:50px>2.60</td>
        <td style=min-width:50px>103</td>
        <td style=min-width:50px>383.78</td>
	</tr>
    <tr>
        <td style=min-width:50px>T9</td>
        <td style=min-width:50px>2.64</td>
        <td style=min-width:50px>106</td>
        <td style=min-width:50px>378.37</td>
	</tr>
    <tr>
        <td style=min-width:50px>T10</td>
        <td style=min-width:50px>3.339</td>
        <td style=min-width:50px>96</td>
        <td style=min-width:50px>299.45</td>
    </tr>
    <tr>
        <td style=min-width:50px>Media:</td>
        <td style=min-width:50px>2.8070192904213962</td>
        <td style=min-width:50px>93.02909787849957</td>
        <td style=min-width:50px>356.26356604989604</td>
    </tr>
    <tr>
        <td style=min-width:50px>Desviacion</td>
        <td style=min-width:50px>0.43079680825187294</td>
        <td style=min-width:50px>8.3090312311363945</td>
        <td style=min-width:50px>46.148441317123677</td>
    </tr>
</table>
<table cellspacing=0 border=1>
    <tr>
    	<td style=min-width:50px>Apache Benchmark Haproxy</td>
    </tr>
    <tr>
    	<td style=min-width:50px></td>
        <td style=min-width:50px>Tiempo de test (s)</td>
        <td style=min-width:50px>Solicitudes fallidas</td>
        <td style=min-width:50px>Solicitudes por segundo</td>
    </tr>
    <tr>
        <td style=min-width:50px>T1</td>
        <td style=min-width:50px>15.21</td>
        <td style=min-width:50px>92</td>
        <td style=min-width:50px>65.73</td>
    </tr>
    <tr>
        <td style=min-width:50px>T2</td>
        <td style=min-width:50px>14.34</td>
        <td style=min-width:50px>115</td>
        <td style=min-width:50px>69.73</td>
	</tr>
    <tr>
        <td style=min-width:50px>T3</td>
        <td style=min-width:50px>14.41</td>
        <td style=min-width:50px>101</td>
        <td style=min-width:50px>69.40</td>
    </tr>
    <tr>
        <td style=min-width:50px>T4</td>
        <td style=min-width:50px>14.89</td>
        <td style=min-width:50px>86</td>
        <td style=min-width:50px>67.16</td>
    </tr>
    <tr>
        <td style=min-width:50px>T5</td>
        <td style=min-width:50px>14.381</td>
        <td style=min-width:50px>86</td>
        <td style=min-width:50px>69.54</td>
	</tr>
    <tr>
        <td style=min-width:50px>T6</td>
        <td style=min-width:50px>14.17</td>
        <td style=min-width:50px>99</td>
        <td style=min-width:50px>70.85</td>
	</tr>
    <tr>
        <td style=min-width:50px>T7</td>
	    <td style=min-width:50px>15.241</td>
	    <td style=min-width:50px>119</td>
	    <td style=min-width:50px>65.61</td>
	</tr>
    <tr>
        <td style=min-width:50px>T8</td>
        <td style=min-width:50px>17.18</td>
        <td style=min-width:50px>114</td>
        <td style=min-width:50px>58.21</td>
	</tr>
    <tr>
        <td style=min-width:50px>T9</td>
        <td style=min-width:50px>15.12</td>
        <td style=min-width:50px>102</td>
        <td style=min-width:50px>66.13</td>
	</tr>
    <tr>
        <td style=min-width:50px>T10</td>
        <td style=min-width:50px>14.996</td>
        <td style=min-width:50px>87</td>
        <td style=min-width:50px>66.68</td>
    </tr>
    <tr>
        <td style=min-width:50px>Media:</td>
        <td style=min-width:50px>14.973342420219772</td>
        <td style=min-width:50px>99.403353829623711</td>
        <td style=min-width:50px>66.812975535555736</td>
    </tr>
    <tr>
        <td style=min-width:50px>Desviacion</td>
        <td style=min-width:50px>0.82105215425087363</td>
        <td style=min-width:50px>11.886547017532047</td>
        <td style=min-width:50px>3.4075287834440964</td>
    </tr>
</table>
<table cellspacing=0 border=1>
    <tr>
    	<td style=min-width:50px>Apache Benchmark Sin balanceador</td>
    </tr>
    <tr>
    	<td style=min-width:50px></td>
        <td style=min-width:50px>Tiempo de test (s)</td>
        <td style=min-width:50px>Solicitudes fallidas</td>
        <td style=min-width:50px>Solicitudes por segundo</td>
    </tr>
    <tr>
        <td style=min-width:50px>T1</td>
        <td style=min-width:50px>26.99</td>
        <td style=min-width:50px>113</td>
        <td style=min-width:50px>37.04</td>
    </tr>
    <tr>
        <td style=min-width:50px>T2</td>
        <td style=min-width:50px>23.05</td>
        <td style=min-width:50px>96</td>
        <td style=min-width:50px>43.38</td>
	</tr>
    <tr>
        <td style=min-width:50px>T3</td>
        <td style=min-width:50px>23.43</td>
        <td style=min-width:50px>108</td>
        <td style=min-width:50px>42.67</td>
    </tr>
    <tr>
        <td style=min-width:50px>T4</td>
        <td style=min-width:50px>22.32</td>
        <td style=min-width:50px>103</td>
        <td style=min-width:50px>44.8</td>
    </tr>
    <tr>
        <td style=min-width:50px>T5</td>
	    <td style=min-width:50px>22.584</td>
	    <td style=min-width:50px>101</td>
	    <td style=min-width:50px>44.28</td>
	</tr>
    <tr>
        <td style=min-width:50px>T6</td>
        <td style=min-width:50px>22.416</td>
        <td style=min-width:50px>91</td>
        <td style=min-width:50px>44.61</td>
	</tr>
    <tr>
        <td style=min-width:50px>T7</td>
        <td style=min-width:50px>22.55</td>
        <td style=min-width:50px>117</td>
        <td style=min-width:50px>44.35</td>
	</tr>
    <tr>
        <td style=min-width:50px>T8</td>
        <td style=min-width:50px>22.37</td>
        <td style=min-width:50px>102</td>
        <td style=min-width:50px>44.69</td>
	</tr>
    <tr>
        <td style=min-width:50px>T9</td>
        <td style=min-width:50px>22.346</td>
        <td style=min-width:50px>93</td>
        <td style=min-width:50px>44.75</td>
	</tr>
    <tr>
        <td style=min-width:50px>T10</td>
        <td style=min-width:50px>22.28</td>
        <td style=min-width:50px>100</td>
        <td style=min-width:50px>44.87</td>
    </tr>
    <tr>
        <td style=min-width:50px>Media:</td>
        <td style=min-width:50px>22.998856122630087</td>
        <td style=min-width:50px>102.09964698382942</td>
        <td style=min-width:50px>43.479587040477135</td>
    </tr>
    <tr>
        <td style=min-width:50px>Desviacion</td>
        <td style=min-width:50px>1.3663602014110339</td>
        <td style=min-width:50px>7.9018985060553639</td>
        <td style=min-width:50px>2.2698907462695201</td>
    </tr>
</table>

Para usar Siege se ha tenido que configurar una maquina nueva de Ubuntu en la que instalarla
esta vez 14.04 Desktop. Tambien se le ha añadido un 0 mas al bucle del código PHP para que
pudieran apreciarse mejor los resultaos.

Tabla de resultados de Siege.
<table cellspacing=0 border=1>
    <tr>
        <td style=min-width:50px>Siege Benchmark Nginx</td>
    </tr>
    <tr>
        <td style=min-width:50px></td>
        <td style=min-width:50px>Disponivilidad (%)</td>
        <td style=min-width:50px>Tiempo respuesta (s)</td>
        <td style=min-width:50px>Operaciones por segundo</td>
        <td style=min-width:50px>Operaciones fallidas</td>
        <td style=min-width:50px>Operación mas larga</td>
    </tr>
    <tr>
        <td style=min-width:50px>T1</td>
        <td style=min-width:50px>100</td>
        <td style=min-width:50px>0.4</td>
        <td style=min-width:50px>61.63</td>
        <td style=min-width:50px>0</td>
        <td style=min-width:50px>3.77</td>
    </tr>
    <tr>
        <td style=min-width:50px>T2</td>
        <td style=min-width:50px>100</td>
        <td style=min-width:50px>0.4</td>
        <td style=min-width:50px>62.24</td>
        <td style=min-width:50px>0</td>
        <td style=min-width:50px>3.74</td>
    </tr>
    <tr>
        <td style=min-width:50px>T3</td>
        <td style=min-width:50px>100</td>
        <td style=min-width:50px>0.4</td>
        <td style=min-width:50px>62.83</td>
        <td style=min-width:50px>0</td>
        <td style=min-width:50px>3.85</td>
    </tr>
    <tr>
        <td style=min-width:50px>T4</td>
        <td style=min-width:50px>100</td>
        <td style=min-width:50px>0.41</td>
        <td style=min-width:50px>61.35</td>
        <td style=min-width:50px>0</td>
        <td style=min-width:50px>4.46</td>
    </tr>
    <tr>
        <td style=min-width:50px>T5</td>
        <td style=min-width:50px>100</td>
        <td style=min-width:50px>0.4</td>
        <td style=min-width:50px>61.96</td>
        <td style=min-width:50px>0</td>
        <td style=min-width:50px>4.03</td>
    </tr>
    <tr>
        <td style=min-width:50px>T6</td>
        <td style=min-width:50px>100</td>
        <td style=min-width:50px>0.39</td>
        <td style=min-width:50px>64.06</td>
        <td style=min-width:50px>0</td>
        <td style=min-width:50px>3.94</td>
    </tr>
    <tr>
        <td style=min-width:50px>T7</td>
        <td style=min-width:50px>100</td>
        <td style=min-width:50px>0.4</td>
        <td style=min-width:50px>62.83</td>
        <td style=min-width:50px>0</td>
        <td style=min-width:50px>4.43</td>
    </tr>
    <tr>
        <td style=min-width:50px>T8</td>
        <td style=min-width:50px>100</td>
        <td style=min-width:50px>0.39</td>
        <td style=min-width:50px>62.93</td>
        <td style=min-width:50px>0</td>
        <td style=min-width:50px>3.64</td>
    </tr>
    <tr>
        <td style=min-width:50px>T9</td>
        <td style=min-width:50px>100</td>
        <td style=min-width:50px>0.39</td>
        <td style=min-width:50px>63.53</td>
        <td style=min-width:50px>0</td>
        <td style=min-width:50px>4.16</td>
    </tr>
    <tr>
        <td style=min-width:50px>T10</td>
        <td style=min-width:50px>100</td>
        <td style=min-width:50px>0.39</td>
        <td style=min-width:50px>63.37</td>
        <td style=min-width:50px>0</td>
        <td style=min-width:50px>3.88</td>
    </tr>
    <tr>
        <td style=min-width:50px>Media:</td>
        <td style=min-width:50px>100</td>
        <td style=min-width:50px>0.39694855391464973</td>
        <td style=min-width:50px>62.66855581041402</td>
        <td style=min-width:50px>0</td>
        <td style=min-width:50px>3.9812916905612972</td>
    </tr>
    <tr>
        <td style=min-width:50px>Desviacion</td>
        <td style=min-width:50px>0</td>
        <td style=min-width:50px>6.403124237432843E-3</td>
        <td style=min-width:50px>0.82590798518963149</td>
        <td style=min-width:50px>0</td>
        <td style=min-width:50px>0.26694568735980728</td>
    </tr>
    <tr>
        <td style=min-width:50px>Siege Benchmark Haproxy</td>
    </tr>
    <tr>
        <td style=min-width:50px></td>
        <td style=min-width:50px>Disponivilidad (%)</td>
        <td style=min-width:50px>Tiempo respuesta (s)</td>
        <td style=min-width:50px>Operaciones por segundo</td>
        <td style=min-width:50px>Operaciones fallidas</td>
        <td style=min-width:50px>Operación mas larga</td>
    </tr>
    <tr>
        <td style=min-width:50px>T1</td>
        <td style=min-width:50px>100</td>
        <td style=min-width:50px>0.34</td>
        <td style=min-width:50px>73.68</td>
        <td style=min-width:50px>0</td>
        <td style=min-width:50px>2.19</td>
    </tr>
    <tr>
        <td style=min-width:50px>T2</td>
        <td style=min-width:50px>100</td>
        <td style=min-width:50px>0.34</td>
        <td style=min-width:50px>73.38</td>
        <td style=min-width:50px>0</td>
        <td style=min-width:50px>1.69</td>
    </tr>
    <tr>
        <td style=min-width:50px>T3</td>
        <td style=min-width:50px>100</td>
        <td style=min-width:50px>0.34</td>
        <td style=min-width:50px>73.43</td>
        <td style=min-width:50px>0</td>
        <td style=min-width:50px>2.8</td>
    </tr>
    <tr>
        <td style=min-width:50px>T4</td>
        <td style=min-width:50px>100</td>
        <td style=min-width:50px>0.35</td>
        <td style=min-width:50px>71.98</td>
        <td style=min-width:50px>0</td>
        <td style=min-width:50px>2</td>
    </tr>
    <tr>
        <td style=min-width:50px>T5</td>
        <td style=min-width:50px>100</td>
        <td style=min-width:50px>0.33</td>
        <td style=min-width:50px>74.53</td>
        <td style=min-width:50px>0</td>
        <td style=min-width:50px>3.51</td>
    </tr>
    <tr>
        <td style=min-width:50px>T6</td>
        <td style=min-width:50px>100</td>
        <td style=min-width:50px>0.34</td>
        <td style=min-width:50px>72.66</td>
        <td style=min-width:50px>0</td>
        <td style=min-width:50px>1.74</td>
    </tr>
    <tr>
        <td style=min-width:50px>T7</td>
        <td style=min-width:50px>100</td>
        <td style=min-width:50px>0.35</td>
        <td style=min-width:50px>70.41</td>
        <td style=min-width:50px>0</td>
        <td style=min-width:50px>3.6</td>
    </tr>
    <tr>
        <td style=min-width:50px>T8</td>
        <td style=min-width:50px>100</td>
        <td style=min-width:50px>0.35</td>
        <td style=min-width:50px>72.84</td>
        <td style=min-width:50px>0</td>
        <td style=min-width:50px>3.43</td>
    </tr>
    <tr>
        <td style=min-width:50px>T9</td>
        <td style=min-width:50px>100</td>
        <td style=min-width:50px>0.35</td>
        <td style=min-width:50px>70.75</td>
        <td style=min-width:50px>0</td>
        <td style=min-width:50px>3.9</td>
    </tr>
    <tr>
        <td style=min-width:50px>T10</td>
        <td style=min-width:50px>100</td>
        <td style=min-width:50px>0.34</td>
        <td style=min-width:50px>74.09</td>
        <td style=min-width:50px>0</td>
        <td style=min-width:50px>2.22</td>
    </tr>
    <tr>
        <td style=min-width:50px>Media:</td>
        <td style=min-width:50px>100</td>
        <td style=min-width:50px>0.34293994214391255</td>
        <td style=min-width:50px>72.764405622944309</td>
        <td style=min-width:50px>0</td>
        <td style=min-width:50px>2.5890410797751571</td>
    </tr>
    <tr>
        <td style=min-width:50px>Desviacion</td>
        <td style=min-width:50px>0</td>
        <td style=min-width:50px>6.40312423743283E-3</td>
        <td style=min-width:50px>1.2942503621788195</td>
        <td style=min-width:50px>0</td>
        <td style=min-width:50px>0.79815787911916214</td>
    </tr>
    <tr>
        <td style=min-width:50px>Siege Benchmark</td>
    </tr>
    <tr>
        <td style=min-width:50px></td>
        <td style=min-width:50px>Disponivilidad (%)</td>
        <td style=min-width:50px>Tiempo respuesta (s)</td>
        <td style=min-width:50px>Operaciones por segundo</td>
        <td style=min-width:50px>Operaciones fallidas</td>
        <td style=min-width:50px>Operación mas larga</td>
    </tr>
    <tr>
        <td style=min-width:50px>T1</td>
        <td style=min-width:50px>100</td>
        <td style=min-width:50px>0.56</td>
        <td style=min-width:50px>43.36</td>
        <td style=min-width:50px>0</td>
        <td style=min-width:50px>4.33</td>
    </tr>
    <tr>
        <td style=min-width:50px>T2</td>
        <td style=min-width:50px>100</td>
        <td style=min-width:50px>0.56</td>
        <td style=min-width:50px>44.55</td>
        <td style=min-width:50px>0</td>
        <td style=min-width:50px>3.92</td>
    </tr>
    <tr>
        <td style=min-width:50px>T3</td>
        <td style=min-width:50px>100</td>
        <td style=min-width:50px>0.56</td>
        <td style=min-width:50px>44.65</td>
        <td style=min-width:50px>0</td>
        <td style=min-width:50px>4.55</td>
    </tr>
    <tr>
        <td style=min-width:50px>T4</td>
        <td style=min-width:50px>100</td>
        <td style=min-width:50px>0.56</td>
        <td style=min-width:50px>44.62</td>
        <td style=min-width:50px>0</td>
        <td style=min-width:50px>4.93</td>
    </tr>
    <tr>
        <td style=min-width:50px>T5</td>
        <td style=min-width:50px>100</td>
        <td style=min-width:50px>0.56</td>
        <td style=min-width:50px>44.21</td>
        <td style=min-width:50px>0</td>
        <td style=min-width:50px>4.54</td>
    </tr>
    <tr>
        <td style=min-width:50px>T6</td>
        <td style=min-width:50px>100</td>
        <td style=min-width:50px>0.56</td>
        <td style=min-width:50px>44.3</td>
        <td style=min-width:50px>0</td>
        <td style=min-width:50px>4.54</td>
    </tr>
    <tr>
        <td style=min-width:50px>T7</td>
        <td style=min-width:50px>100</td>
        <td style=min-width:50px>0.59</td>
        <td style=min-width:50px>41.95</td>
        <td style=min-width:50px>0</td>
        <td style=min-width:50px>8.44</td>
    </tr>
    <tr>
        <td style=min-width:50px>T8</td>
        <td style=min-width:50px>100</td>
        <td style=min-width:50px>0.56</td>
        <td style=min-width:50px>44.46</td>
        <td style=min-width:50px>0</td>
        <td style=min-width:50px>2.8</td>
    </tr>
    <tr>
        <td style=min-width:50px>T9</td>
        <td style=min-width:50px>100</td>
        <td style=min-width:50px>0.56</td>
        <td style=min-width:50px>44.14</td>
        <td style=min-width:50px>0</td>
        <td style=min-width:50px>3.67</td>
    </tr>
    <tr>
        <td style=min-width:50px>T10</td>
        <td style=min-width:50px>100</td>
        <td style=min-width:50px>0.56</td>
        <td style=min-width:50px>44.11</td>
        <td style=min-width:50px>0</td>
        <td style=min-width:50px>3.77</td>
    </tr>
    <tr>
        <td style=min-width:50px>Media:</td>
        <td style=min-width:50px>100</td>
        <td style=min-width:50px>0.56392728549340088</td>
        <td style=min-width:50px>44.027933945050712</td>
        <td style=min-width:50px>0</td>
        <td style=min-width:50px>4.3754279058664141</td>
    </tr>
    <tr>
        <td style=min-width:50px>Desviacion</td>
        <td style=min-width:50px>0</td>
        <td style=min-width:50px>9.1651513899116497E-3</td>
        <td style=min-width:50px>0.7801698533011886</td>
        <td style=min-width:50px>0</td>
        <td style=min-width:50px>1.4201197132636372</td>
    </tr>
</table>