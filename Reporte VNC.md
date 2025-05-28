Vulneracion mediante el servicio VNC

No podemos iniciar a trabajar sin saber que tenemos alcance por eso realizaremos una analisis de sus puertos y de los servicios que estan disponibles.
Para esto nos apoyaremos de la herramienta `nmap` con el siguiente comando:

```bash
nmap -sV 192.168.222.131 
```
![image](https://github.com/user-attachments/assets/08d5d404-3bf6-40b6-aaba-69b70e00629e)

Se visualiza el puerto 5900 ofrece un servicio de VNC para esto, realizamos una búsqueda pero filtrada ya que si solo usamos “search vnc ”obtendremos miles de resultados, ya que nuestro objetivo principal es poder ingresar a la maquina filtraremos por la palabra “login”.

![image](https://github.com/user-attachments/assets/07d8569e-aa57-42dd-aada-f7509bf6835e)

usaremos el primer resultado que nos aparece ya que es compatible con nuestra maquina, haciendo uso del comando:

use 0

![image](https://github.com/user-attachments/assets/7cfb3923-102d-47ad-a092-e818c4955765)

para poder visualizar las opciones que y requerimientos que necesita este script usaremos:

show options

![image](https://github.com/user-attachments/assets/0b12282f-5e9e-455c-8033-b63aded4dff2)

denotamos que nos hace falta la direccion ip de la maquina objetivo, en mi caso seria la ip 192.168.222.131, el comando para añadirlo seria:

set RHOST 192.168.222.131

![image](https://github.com/user-attachments/assets/e4606faf-6cd2-4540-96b6-086e6b4a09bf)

con esto pasamos a ejecutar nuestro exploit con el comando run o exploit

![image](https://github.com/user-attachments/assets/24d6f244-f295-42a3-a6dd-62ff458f0b43)

Con esto el explot no indica que la contraseña para realizar un log mediante el puerto 5900 seria password

