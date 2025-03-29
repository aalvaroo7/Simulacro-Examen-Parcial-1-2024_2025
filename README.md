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
