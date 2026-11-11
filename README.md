# Laboratorio8

**Subredes Clase A (10.0.0.0/8)**

**1. Cálculos de Subredes y Requerimientos**

* **Red base:** 10.0.0.0/8
* **Subredes requeridas:** 16 subredes ($2^4 = 16$, se toman prestados 4 bits del segundo octeto).
* **Prefijo CIDR:** /12 (8 bits base + 4 bits prestados).
* **Máscara de subred:** 255.240.0.0
* **Hosts por subred:** $2^{20} - 2 = 1,048,574$ hosts útiles por subred.
* **Salto de red (bloque):** 16 en el segundo octeto ($256 - 240 = 16$).

**2. Tabla de las Primeras 8 Subredes (Dirección de Red y Transmisión / Broadcast)**

| N.º Subred | Dirección de Red | Dirección de Broadcast |
|---|---|---|
| Subred 1 | 10.0.0.0 /12 | 10.15.255.255 |
| Subred 2 | 10.16.0.0 /12 | 10.31.255.255 |
| Subred 3 | 10.32.0.0 /12 | 10.47.255.255 |
| Subred 4 | 10.48.0.0 /12 | 10.63.255.255 |
| Subred 5 | 10.64.0.0 /12 | 10.79.255.255 |
| Subred 6 | 10.80.0.0 /12 | 10.95.255.255 |
| Subred 7 | 10.96.0.0 /12 | 10.111.255.255 |
| Subred 8 | 10.112.0.0 /12 | 10.127.255.255 |

**3. Rango de Hosts Útiles de las Primeras 4 Subredes**

| Subred | Rango de Hosts Útiles |
|---|---|
| Subred 1 | 10.0.0.1 - 10.15.255.254 |
| Subred 2 | 10.16.0.1 - 10.31.255.254 |
| Subred 3 | 10.32.0.1 - 10.47.255.254 |
| Subred 4 | 10.48.0.1 - 10.63.255.254 |


Entramos a lo que es Cisco, y vamos a crear un Router principal que va a estar conectado a 3 Switch donde estos respectivamente estan conectados a 3 PC donde haremos lo que son las 3 subclases


Después vamos a configurar del Router, se ingresó a la consola CLI del router para asignar la dirección IP 10.0.0.1 con máscara 255.240.0.0 (/12) a la interfaz GigabitEthernet0/0 como puerta de enlace predeterminada de la subred Clase A. Se habilitó el puerto mediante el comando no shutdown y se confirmó su estado activo (up/up).


Despues configuramos las IP de las PC0 y PC1, se asignaron direcciones IP pertenecientes a la primera subred (10.0.0.0/12) a las computadoras PC0 (10.0.0.10) y PC1 (10.0.0.11), utilizando la máscara 255.240.0.0 y la IP 10.0.0.1 como puerta de enlace predeterminada.


Por ultimo vamos a confirmar con los Ping de de las respectivas PC de la clase A, se realizaron pruebas de conectividad desde PC0 enviando paquetes ICMP hacia la puerta de enlace (10.0.0.1) y hacia PC1 (10.0.0.11). Todas las pruebas resultaron exitosas con un 0% de pérdida de paquetes.


**Subredes Clase B (172.20.0.0/16)**

**Calculos de Subredes y Requerimientos**

* **Red base:** 172.20.0.0/16
* **Subredes requeridas:** 32 subredes ($2^5 = 32$, se toman prestados 5 bits del tercer octeto).
* **Prefijo CIDR:** /21 (16 bits base + 5 bits prestados).
* **Máscara de subred:** 255.255.248.0
* **Hosts por subred:** $2^{11} - 2 = 2046$ hosts útiles por subred (11 bits restantes para host).
* **Salto de red (bloque):** 8 en el tercer octeto ($256 - 248 = 8$).

**Tabla de las Primeras 10 Subredes (Dirección de Red y Broadcast)**

| N.º Subred | Dirección de Red | Dirección de Broadcast |
|---|---|---|
| Subred 1 | 172.20.0.0 /21 | 172.20.7.255 |
| Subred 2 | 172.20.8.0 /21 | 172.20.15.255 |
| Subred 3 | 172.20.16.0 /21 | 172.20.23.255 |
| Subred 4 | 172.20.24.0 /21 | 172.20.31.255 |
| Subred 5 | 172.20.32.0 /21 | 172.20.39.255 |
| Subred 6 | 172.20.40.0 /21 | 172.20.47.255 |
| Subred 7 | 172.20.48.0 /21 | 172.20.55.255 |
| Subred 8 | 172.20.56.0 /21 | 172.20.63.255 |
| Subred 9 | 172.20.64.0 /21 | 172.20.71.255 |
| Subred 10 | 172.20.72.0 /21 | 172.20.79.255 |

**Rango de Hosts Útiles de las Primeras 5 Subredes**

| Subred | Rango de Hosts Útiles |
|---|---|
| Subred 1 | 172.20.0.1 - 172.20.7.254 |
| Subred 2 | 172.20.8.1 - 172.20.15.254 |
| Subred 3 | 172.20.16.1 - 172.20.23.254 |
| Subred 4 | 172.20.24.1 - 172.20.31.254 |
| Subred 5 | 172.20.32.1 - 172.20.39.254 |

De la misma manera vamos a configurar lo que es el router principal, se ingresó a la consola CLI del router para asignar la dirección IP 172.20.0.1 con máscara 255.255.248.0 (/21) a la interfaz GigabitEthernet0/1 como puerta de enlace predeterminada de la subred Clase B. Se habilitó la interfaz mediante el comando no shutdown y se verificó su estado activo (up/up).



De igual forma, configuramos lo que es la IP de cada computadora, se configuraron las direcciones IP fijas en las computadoras pertenecientes a la primera subred Clase B (172.20.0.0/21): PC2 con IP 172.20.0.10 y PC3 con IP 172.20.0.11, estableciendo la máscara de subred 255.255.248.0 y el gateway 172.20.0.1.



Por ultimo nuevamente vamos a probar los Ping, se verificó la conectividad de la subred Clase B desde PC2 realizando pruebas de ping exitosas hacia la puerta de enlace (172.20.0.1) y hacia el host adyacente PC3 (172.20.0.11) sin pérdida de paquetes.


**Subredes Clase C (192.168.50.0/24)**

**Cálculos de Subredes y Requerimientos**

* **Red base:** 192.168.50.0/24
* **Subredes requeridas:** 8 subredes ($2^3 = 8$, se toman prestados 3 bits del cuarto octeto).
* **Prefijo CIDR:** /27 (24 bits base + 3 bits prestados).
* **Máscara de subred:** 255.255.255.224
* **Hosts por subred:** $2^5 - 2 = 30$ hosts útiles por subred.
* **Salto de red (bloque):** 32 en el cuarto octeto ($256 - 224 = 32$).

**Tabla Completa de Subredes (Dirección de Red, Broadcast y Rango de Hosts)**

| N.º Subred | Dirección de Red | Dirección de Broadcast | Rango de Hosts Útiles |
|---|---|---|---|
| Subred 1 | 192.168.50.0 /27 | 192.168.50.31 | 192.168.50.1 - 192.168.50.30 |
| Subred 2 | 192.168.50.32 /27 | 192.168.50.63 | 192.168.50.33 - 192.168.50.62 |
| Subred 3 | 192.168.50.64 /27 | 192.168.50.95 | 192.168.50.65 - 192.168.50.94 |
| Subred 4 | 192.168.50.96 /27 | 192.168.50.127 | 192.168.50.97 - 192.168.50.126 |
| Subred 5 | 192.168.50.128 /27 | 192.168.50.159 | 192.168.50.129 - 192.168.50.158 |
| Subred 6 | 192.168.50.160 /27 | 192.168.50.191 | 192.168.50.161 - 192.168.50.190 |
| Subred 7 | 192.168.50.192 /27 | 192.168.50.223 | 192.168.50.193 - 192.168.50.222 |
| Subred 8 | 192.168.50.224 /27 | 192.168.50.255 | 192.168.50.225 - 192.168.50.254 |


De la misma manera vamos a configurar lo que es el router principal, se ingresó a la consola CLI del router para asignar la dirección IP 192.168.50.1 con máscara 255.255.255.224 (/27) a la interfaz GigabitEthernet0/2 como puerta de enlace predeterminada de la subred Clase C. Se habilitó el puerto mediante el comando no shutdown y se confirmó su estado activo (up/up).


De la misma manera vamos a configurar las respectivas IP, se asignaron direcciones IP estáticas pertenecientes a la primera subred (192.168.50.0/27) a los equipos PC4 (192.168.50.10) y PC5 (192.168.50.11), definiendo la máscara de subred 255.255.255.224 y el gateway 192.168.50.1.



Por ultimo vamos a probar con los ping respectivos, se realizaron las pruebas de conectividad ICMP desde PC4 respondiendo exitosamente la puerta de enlace (192.168.50.1) y el equipo adyacente PC5 (192.168.50.11) con un 0% de pérdida de paquetes.

