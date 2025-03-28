# Simulacro-Examen-Parcial-1-2024_2025

# Ejercicio 7 resuelto en cisco paquet tracer

# 🔹 Paso a Paso: Configuración en Cisco Packet Tracer

## **Paso 1: Configurar el entorno en Cisco Packet Tracer**
### **1.1 Abrir Cisco Packet Tracer**
- Inicia **Cisco Packet Tracer** en tu computadora.  
- Crea un **nuevo proyecto** (Archivo > Nuevo).  

### **1.2 Agregar dispositivos**
- Arrastra dos dispositivos al área de trabajo. Puedes elegir entre:  
  - **Dos PC** (PC0 y PC1).  
  - **Dos routers** (Router0 y Router1).  

### **1.3 Conectar los dispositivos**
Selecciona el cable adecuado según el tipo de conexión:  
- **Si conectas dos PCs directamente:** Usa un **cable cruzado**.  
- **Si conectas un PC a un switch:** Usa un **cable directo**.  
- **Si conectas dos routers:** Usa un **cable serial** o un **cable directo** en puertos FastEthernet/GigabitEthernet.  

Para conectar los dispositivos:  
1. Haz clic en el **icono de conexión** (el rayo amarillo).  
2. Selecciona el tipo de cable adecuado.  
3. Haz clic en el primer dispositivo y elige su puerto de red.  
4. Luego, haz clic en el segundo dispositivo y selecciona su puerto de red.  

---

## **Paso 2: Configurar el enlace**
### **2.1 Ajustar el ancho de banda**
- Haz clic en el **cable** que conecta los dispositivos.  
- Ve a la pestaña **Config o Physical** según el dispositivo.  
- Busca la opción **Bandwidth** o **Velocidad de Enlace**.  
- Establece el ancho de banda en **500 Mbps (500 × 10⁶ Hz)** para simular los 500 MHz.  

### **2.2 Simular ruido en el enlace**
Según el tipo de enlace:  
- **Si usas un enlace inalámbrico:**  
  1. Agrega un **Access Point** y conecta los dispositivos de forma inalámbrica.  
  2. Ajusta la **potencia de transmisión** o **aumenta la distancia** entre los dispositivos para simular ruido.  
- **Si usas un enlace cableado:**  
  - Introduce errores en el enlace modificando **los parámetros de calidad** del cable.  

---

## **Paso 3: Calcular la tasa de transmisión máxima**
La **fórmula de Shannon** es:  
\[
C = B \cdot \log_2(1 + SNR)
\]
Donde:  
- **B = 500 MHz = 500 × 10⁶ Hz** (ancho de banda).  
- **SNR = 20 dB → en escala lineal: 100**  
  \[
  SNR_{lineal} = 10^{\frac{SNR_{dB}}{10}} = 10^{\frac{20}{10}} = 10^2 = 100
  \]
- Calculamos **log₂(101)** ≈ **6.6582**  
  \[
  C = (500 \times 10^6) \cdot 6.6582
  \]
  \[
  C \approx 3.3291 \times 10^9 \text{ bps} = 3.33 \text{ Gbps}
  \]
- **Resultado final:**  
  La **tasa de transmisión máxima** es **≈ 3.33 Gbps**.  

---

## **Paso 4: Verificar el rendimiento en Cisco Packet Tracer**
### **4.1 Configurar direcciones IP**
1. **Haz clic en PC0** > **Config** > **Settings** > **FastEthernet0**  
   - **IP Address:** `192.168.1.1`  
   - **Subnet Mask:** `255.255.255.0`  
2. **Haz clic en PC1** > **Config** > **Settings** > **FastEthernet0**  
   - **IP Address:** `192.168.1.2`  
   - **Subnet Mask:** `255.255.255.0`  

### **4.2 Probar conectividad con Ping**
1. **Abre la Terminal** en PC0.  
2. Escribe:  
   ```bash
   ping 192.168.1.2
