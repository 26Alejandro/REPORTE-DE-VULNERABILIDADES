# Vulneración mediante el servicio SQL

No podemos iniciar a trabajar sin saber que tenemos alcance, por eso realizaremos un análisis de sus puertos y de los servicios que están disponibles.  
Para esto nos apoyaremos de la herramienta `nmap` con el siguiente comando:

```bash
nmap -sV 192.168.222.131 
```

![image](https://github.com/user-attachments/assets/08d5d404-3bf6-40b6-aaba-69b70e00629e)

se visualiza que el puerto 3306 presenta un servicio sql que podemos aprovechar.
usaremos la ip de la maquina objetivo para detectar alguna pagina disponible.

![image](https://github.com/user-attachments/assets/efb7d2b9-bd6c-4591-833c-6eca5b25a817)

usaremos la opcion de DVWA, esta nos brindara una pagina con con un aparte de ingreso de usuario y contraseña.
verificamos si podemos  hacerlo algo gran escala con la herramienta SQLMAP, obiando la contraseña por defecto que nos brinda (usuario= admin y password= password).
![image](https://github.com/user-attachments/assets/18370ff9-5b22-4bc0-832d-7539ad8f3ec3)
![image](https://github.com/user-attachments/assets/e915762f-9519-4def-87cc-5dd7a94fe6a0)



![image](https://github.com/user-attachments/assets/846124b9-c38a-4efd-abfe-bdf39b769be6)

configuraremos su parametro de "DVWA Security", esta vulnerabilidad nos permite configurar con facilidad el nivel de seguridad.

![image](https://github.com/user-attachments/assets/ce2d7c53-f174-4687-8b03-0ffad2a3b8f7)




