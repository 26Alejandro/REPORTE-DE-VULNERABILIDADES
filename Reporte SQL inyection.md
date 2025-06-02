# Vulneración mediante el servicio SQL

No podemos iniciar a trabajar sin saber que tenemos alcance, por eso realizaremos un análisis de sus puertos y de los servicios que están disponibles.  
Para esto nos apoyaremos de la herramienta `nmap` con el siguiente comando:

```bash
nmap -sV 192.168.222.131 
```

![Escaneo de puertos con Nmap](https://github.com/user-attachments/assets/08d5d404-3bf6-40b6-aaba-69b70e00629e)

Se visualiza que el puerto 3306 presenta un servicio SQL que podemos aprovechar.  
Usaremos la IP de la máquina objetivo para detectar alguna página disponible.

![Detección de servicios web](https://github.com/user-attachments/assets/efb7d2b9-bd6c-4591-833c-6eca5b25a817)

Usaremos la opción de **DVWA**, esta nos brindará una página con un apartado de ingreso de usuario y contraseña.  
Verificamos si podemos hacer algo a gran escala con la herramienta **SQLMAP**, obviando la contraseña por defecto que nos brinda (usuario = admin y password = password).  
Para esto ingresaremos el siguiente comando:

```bash
sqlmap -u "http://192.168.222.131/dvwa/vulnerabilities/sqli/?id=1&Submit=Submit" --dbs
```

![Uso de SQLMap](https://github.com/user-attachments/assets/18370ff9-5b22-4bc0-832d-7539ad8f3ec3)  
![Resultado de SQLMap](https://github.com/user-attachments/assets/e915762f-9519-4def-87cc-5dd7a94fe6a0)

Se puede verificar que por el momento la página tiene un nivel de seguridad alto (referente a una inyección SQL).

![Seguridad alta en DVWA](https://github.com/user-attachments/assets/846124b9-c38a-4efd-abfe-bdf39b769be6)

Configuraremos su parámetro de **"DVWA Security"**, esta vulnerabilidad nos permite configurar con facilidad el nivel de seguridad.

![Cambio de nivel de seguridad](https://github.com/user-attachments/assets/ce2d7c53-f174-4687-8b03-0ffad2a3b8f7)

Nos dirigimos al apartado de SQL injection, e ingresaremos el siguiente comando:

```
%' or '0'='0
```

Esto nos retornará de forma enlistada los usuarios con su contraseña correspondiente.  
Se debe tener en cuenta que esta función solo la deberían tener los administradores.

![Inyección SQL exitosa](https://github.com/user-attachments/assets/8ebdc8d4-b58e-46ab-974c-92dd6bc97baf)

A su vez, podemos ayudarnos de la herramienta **Hydra** para hacer un ataque de diccionario en la sección de logeo, con el comando:

```bash
hydra -l admin -P /usr/share/wordlists/rockyou.txt 192.168.222.131 http-post-form "/dvwa/login.php:username=^USER^&password=^PASS^&Login=Login:Login failed"
```

![Ataque con Hydra](https://github.com/user-attachments/assets/ab88b3fa-ca55-4275-9028-290171503895)
