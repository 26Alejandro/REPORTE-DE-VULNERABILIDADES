**Vulneracion mediante explotacion del servicio telnet**

Para esto nos apoyaremos de la herramienta  nmap con el siguiente comando:

nmap -sV 192.168.222.131 

![image](https://github.com/user-attachments/assets/59ee4216-3d88-4314-afa5-7a80d7068fd5)

nos apoyaremos de la  herramienta metasploit, ingresando el siguiente comando para su  ejecucion:

msfconsole

En ella buscaremos algun script que sea compatible con nuestro servicio disponible y con nuestro objetivo que es ingresar a la maquina
![image](https://github.com/user-attachments/assets/b1406250-e7d4-4116-b29a-573e1a07b68a)


seleccionamos el esta herramienta con el comando:

 use 3

![image](https://github.com/user-attachments/assets/36c2102b-0255-44ca-a1a7-b5d4929bb07a)


visualizamos las opciones que tiene este script ya preparado, con el comando:

show options
![image](https://github.com/user-attachments/assets/33dd83f4-d1f3-4b29-a0b3-6b6d49f4af0c)


como se puede llegar a identificar nos faltaria completar el campo de RHOST que seria la ip nuestro objetivo.

En mi caso la ip fue de 192.168.222.131 esta se ingresa con el comando:

set RHOST 192.168.222.131

![image](https://github.com/user-attachments/assets/d02e1177-0d88-49c9-8774-37dee759692d)

Llegado a este punto se ejecunta con el comando run u exploit

![image](https://github.com/user-attachments/assets/cf8d7462-b4e1-4d3e-804f-cf8bf549b948)

como se puede visualizar el gracias a este escript se pudo obtener las credenciales de acceso a la maquina }.

Procedemos a realizar la conexion telnnet colocando la ip y el puerto del objetivo, mediante el siguiente comando:
telnet 192.168.22.131 23



