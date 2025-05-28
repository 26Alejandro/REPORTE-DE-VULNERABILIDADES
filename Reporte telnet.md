**Vulneracion mediante explotacion del servicio telnet**

Para esto nos apoyaremos de la herramienta  nmap con el siguiente comando:

nmap -sV 192.168.222.131 

![image](https://github.com/user-attachments/assets/59ee4216-3d88-4314-afa5-7a80d7068fd5)

nos apoyaremos de la  herramienta metasploit, ingresando el siguiente comando para su  ejecucion:

msfconsole

En ella buscaremos algun script que sea compatible con nuestro servicio disponible y con nuestro objetivo que es ingresar a la maquina
![image](https://github.com/user-attachments/assets/e2fa8497-b3ed-4024-a874-dacaac890875)

seleccionamos el esta herramienta con el comando:

 use 5

![image](https://github.com/user-attachments/assets/ed01761f-4cfe-4b31-b800-5a97a968675f)

visualizamos las opciones que tiene este script ya preparado, con el comando:

show options
![image](https://github.com/user-attachments/assets/3cb108e2-3f92-4dd1-ad27-b25aa6d0ede6)

como se puede llegar a identificar nos faltaria completar el campo de RHOST que seria la ip nuestro objetivo.

En mi caso la ip fue de 192.168.222.131 esta se ingresa con el comando:

set RHOST 192.168.222.131
![image](https://github.com/user-attachments/assets/41820f44-3ac5-4db8-9e6d-cd8e3cd07951)



