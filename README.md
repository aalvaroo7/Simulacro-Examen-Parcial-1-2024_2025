# Simulacro-Examen-Parcial-1-2024_2025

# Ejercicio 7 resuelto en cisco paquet tracer

# 🔹 Paso a Paso: Configuración en Cisco Packet Tracer

## Dispositivos

Colocar 2 routers, uno DCE y otro DTE 

conectarlos con un cable DCE

Colocar dos AP-PT-AC, conectarlos a ambos routers, colocar un laptop que se conectará de forma inalambrica

## Configuraciones

En ambos routers introducimos 

enable
configure terminal
interface GigabitEthernet0/0  # (Cambia esto según tu interfaz)
bandwidth 500000  # (500 Mbps en Kbps)
exit
exit
write memory (guarda la configuración del router)

Con esto habremos limitado el ancho de banda a 500Mbps

### si introducimos el comando show interfaces "Nombre de la interfaz" nos mostrara los detalles de esta interfaz 

y podremos observar una línea que muestra lo siguiente 

Router#show interfaces gig0/1/0
GigabitEthernet0/1/0 is up, line protocol is up (connected)
  Hardware is CN Gigabit Ethernet, address is 00d0.bc82.4d6d (bia 00d0.bc82.4d6d)
  MTU 1500 bytes, BW 5000000 Kbit, DLY 10 usec,
  
  ----------(Resto de las especificaciones)--------------------------


  Ahora configuraremos lo relativo al Access Point (AP) 

Activaremos en el apartado de configuración el WPA2-PSK Asignaremos en el apartado de configuración una SSID especifica para la red inalámbrica y una contraseña 
En el laptop que coloquemos pondremos un módulo de red inalámbrica y configuraremos este módulo.

Ahora en los CLI de los routers configuraremos las IP de cada puerto en la pestaña de config, a cada interfaz le asignaremos una ip de la red

A la interfaz serial la asignaremos otra red con sus respectivas ip (192.168.2.0 es la que he definido yo)

Añadimos las rutas para que se puedan conectar de una red a otra 

**Configuración de Rutas Estáticas en Routers (Packet Tracer)**

**Router1:**

1.  **Acceder a la Configuración de Router1:**

    * Abre la consola de `Router1` en Packet Tracer.
    * Entra al modo de configuración privilegiado:

        ```plaintext
        enable
        ```

    * Entra al modo de configuración global:

        ```plaintext
        configure terminal
        ```

2.  **Configurar la Ruta Estática:**

    * Asegúrate de que la dirección IP del siguiente salto sea correcta (192.168.3.2).

        ```plaintext
        ip route 192.168.1.0 255.255.255.0 192.168.3.2
        ```

3.  **Guardar la Configuración:**

    * Guarda la configuración:

        ```plaintext
        exit
        write memory
        ```

**Router0:**

1.  **Acceder a la Configuración de Router0:**

    * Abre la consola de `Router0` en Packet Tracer.
    * Entra al modo de configuración privilegiado:

        ```plaintext
        enable
        ```

    * Entra al modo de configuración global:

        ```plaintext
        configure terminal
        ```

2.  **Configurar la Ruta Estática:**

    * Asegúrate de que la dirección IP del siguiente salto sea correcta (192.168.3.1).

        ```plaintext
        ip route 192.168.2.0 255.255.255.0 192.168.3.1
        ```

3.  **Guardar la Configuración:**

    * Guarda la configuración:

        ```plaintext
        exit
        write memory
        ```

**Verificación:**

* Después de configurar las rutas estáticas, verifica la conectividad haciendo ping desde los laptops a las diferentes redes.

    * **Desde Laptop-PT (192.168.2.2) a Laptop-PT (192.168.1.2):**

        ```plaintext
        C:\> ping 192.168.1.2
        ```

    * **Desde Laptop-PT (192.168.1.2) a Laptop-PT (192.168.2.2):**

        ```plaintext
        C:\> ping 192.168.2.2
        ```

    * Si los pings son exitosos, la configuración de las rutas estáticas es correcta y la comunicación entre las redes estará funcionando.

