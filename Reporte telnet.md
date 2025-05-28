# Vulneración mediante explotación del servicio Telnet

Para esto nos apoyaremos de la herramienta `nmap` con el siguiente comando:

```bash
nmap -sV 192.168.222.131 
```

![nmap-scan](https://github.com/user-attachments/assets/59ee4216-3d88-4314-afa5-7a80d7068fd5)

---

Luego utilizamos la herramienta **Metasploit**, ingresando el siguiente comando para su ejecución:

```bash
msfconsole
```

En ella, buscaremos algún script que sea compatible con el servicio disponible y con nuestro objetivo: ingresar a la máquina.

![metasploit-search](https://github.com/user-attachments/assets/b1406250-e7d4-4116-b29a-573e1a07b68a)

Seleccionamos el módulo deseado con el comando:

```bash
use 3
```

![use-module](https://github.com/user-attachments/assets/36c2102b-0255-44ca-a1a7-b5d4929bb07a)

Visualizamos las opciones que tiene este script ya preparado, con el comando:

```bash
show options
```

![show-options](https://github.com/user-attachments/assets/33dd83f4-d1f3-4b29-a0b3-6b6d49f4af0c)

Como se puede identificar, nos falta completar el campo de `RHOST`, que sería la IP de nuestro objetivo.

En este caso, la IP es `192.168.222.131`, y se ingresa con el comando:

```bash
set RHOST 192.168.222.131
```

![set-rhost](https://github.com/user-attachments/assets/d02e1177-0d88-49c9-8774-37dee759692d)

Llegado a este punto, se ejecuta con el comando `run` o `exploit`:

```bash
run
```

![run-exploit](https://github.com/user-attachments/assets/cf8d7462-b4e1-4d3e-804f-cf8bf549b948)

Como se puede visualizar, gracias a este script se pudo obtener las credenciales de acceso a la máquina:

- **Usuario:** `msfadmin`  
- **Contraseña:** `msfadmin`

---

## Conexión mediante Telnet

Procedemos a realizar la conexión Telnet colocando la IP y el puerto del objetivo, mediante el siguiente comando:

```bash
telnet 192.168.222.131 23
```

Con esto se consagra la conexión con la máquina:

![telnet-access](https://github.com/user-attachments/assets/8a686e25-1fe0-48f5-8eec-09e79f8b7ce0)

---

Si bien es cierto, con la máquina objetivo en cuestión ya se muestran sus credenciales solo realizando una conexión mediante el servicio de Telnet, esta vulnerabilidad refleja malas prácticas de seguridad.

---

## Vulnerabilidades relacionadas

- **CVE-1999-0506** *(Telnet Daemon Authentication Bypass)*:  
  Esta es una CVE muy antigua y general para los demonios Telnet que podrían tener omisiones de autenticación o mecanismos de autenticación débiles. Aunque no es específica de Metasploitable2, el espíritu de esta vulnerabilidad (acceso fácil) es lo que Metasploitable2 pretende demostrar.

- **CVE-2001-0504** *(Telnet Daemon Remote Buffer Overflow)*:  
  Se refiere a desbordamientos de búfer en los demonios Telnet, que podrían conducir a la ejecución remota de código. Metasploitable2 está diseñado para tener este tipo de vulnerabilidades.

---

> ⚠️ **Importante:** Este laboratorio debe ser realizado únicamente en entornos controlados, como máquinas virtuales de prueba. Nunca ejecutes este tipo de acciones en sistemas sin autorización.
