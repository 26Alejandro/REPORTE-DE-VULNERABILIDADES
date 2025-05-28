Vulneracion mediante el servicio VNC

No podemos iniciar a trabajar sin saber que tenemos alcance por eso realizaremos una analisis de sus puertos y de los servicios que estan disponibles.
Para esto nos apoyaremos de la herramienta `nmap` con el siguiente comando:

```bash
nmap -sV 192.168.222.131 
```



Se visualiza el puerto 5900 ofrece un servicio de VNC para esto, realizamos una búsqueda pero filtrada ya que si solo usamos “search vnc ”obtendremos miles de resultados, ya que nuestro objetivo principal es poder ingresar a la maquina filtraremos por la palabra “login”.
