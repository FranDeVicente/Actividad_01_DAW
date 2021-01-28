![Portada](imagenes/portada.png)

![Enunciado](imagenes/enunciado01.png)

# 01.- ¿Cómo sabemos si tenemos acceso a internet? 

Para saber si tenemos acceso a internet, lo primero que debemos conocer es nuestra dirección IP. Para ello, vamos a abrir la consola de nuestro Sistema Operativo que en mi caso, al utilizar un S.O. Windows7, abriré la **consola de comandos powerShell.** Una vez abierta, empezamos a trabajar con ella. 

**¿Cómo se usa?** Lo usaremos escribimos el comando **"ipconfig"** para conocer nuestra dirección IP. 

**¿Qué hace el comando?** Observamos que nos aparece un listado con los datos de nuestra conexión red. En dicho listado, debemos localizar la tarjeta de red que estamos utilizando y nos fijaremos en la entrada **IPv4**, que será la que nos indique la dirección IP asignada a nuestro equipo.

![comando1](imagenes/comando1.png)


Ahora que ya conocemos nuestra dirección IP, vamos a comprobar si tenemos acceso a internet. Podemos comprobar nuestra conexión, utilizando el comando **ping**. Para ello, vamos a escribir **ping nuestraDirecciónIp**.

![comando2](imagenes/comando2.png)

**¿Por qué responde a la pregunta?** Si nos fijamos, vemos que nos indica el número de paquetes que envía, el tamaño en bytes que ocupa cada uno de ellos y el tiempo que tarda en enviarlo. Después, nos manda la estadística del **comando ping** para nuestra dirección IP y nos informa de los paquetes que ha enviado, recibido y perdido. 

**¿Cómo se interpreta la salida?** Si recibimos el mensaje de que no se ha perdido ningún paquete "<0% perdidos>", significará que nuestra conexión a internet es correcta. Por el contrario, nos saldrá un mensaje diciendo "Tiempo de espera agotado para esta solicitud" lo que significará que habrá existido algún tipo de error de conexión, a causa del router por ejemplo, o lo que sea.

# 2.- ¿Cómo sabemos si nuestro servidor es accesible desde internet? 

Para saber si nuestro servidor es accesible desde internet, debemos ver los puertos abiertos en nuestro Sistema Operativo. 

**¿Qué hace el comando?** Al utilizar un S.O. Windows, necesitaremos el comando **netstat** ("**ufw**" para Linux).

Ahora bien, nos surge la duda de **¿Cómo se usa o qué hace éste comando?** para ello, podemos pedir ayuda a nuestra consola, escribiendo **netstat /?** que nos mostrará un menú de opciones como muestro en la siguiente imagen:

![comando3](imagenes/comando3.png)

**¿Por qué responde a la pregunta?** Observamos que el comando **netstat -a** lo que hace es mostrar las estadísticas del protocolo y conexiones TCP/IP actuales. Como lo que queremos es saber si nuestro servidor es accesible desde internet, vamos a buscar nuestro servidor y ver qué ocurre. 

En mi caso concreto, estoy usando un servidor *Apache Tomcat* que está utilizando el puerto **8083**
![comando4](imagenes/comando4.png)

A continuación, utilizando *netstat -a* vemos que nuestro servidor sí que está escuchando aunque, no es accesible desde internet (remota) sino que "escucha" de manera local.

![comando5](imagenes/comando5.png)



 



