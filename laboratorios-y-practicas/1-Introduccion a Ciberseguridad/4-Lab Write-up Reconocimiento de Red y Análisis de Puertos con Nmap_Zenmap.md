# Notas de Lab: Escaneo de Puertos y Reconocimiento de Red con Nmap / Zenmap

## ¿De qué trata este laboratorio?
En esta práctica aprendimos cómo funcionan los puertos en una red y cómo usar herramientas como Nmap o Zenmap para escanearlos. Esto sirve para ver qué servicios están activos en un equipo y si hay algún puerto expuesto que pueda ser un riesgo.

---

## Conceptos básicos que aprendí

* **Número de Puerto:** Es como un número de puerta en un edificio. Sirve para que la red sepa a qué aplicación específica debe entregar los datos.
* **Escaneo de Puertos:** Es revisar una computadora o servidor para ver qué puertos tiene abiertos. 
  * **Uso bueno:** Los administradores lo usan para revisar que la red esté segura.
  * **Uso malo:** Los atacantes lo usan para buscar qué servicios vulnerables pueden atacar.

---

## ¿Qué significan los estados de los puertos?

| Estado | ¿Qué significa en palabras sencillas? | ¿Es peligroso? |
| :--- | :--- | :--- |
| **Abierto (Open)** | Hay un programa escuchando y listo para recibir conexiones. | Puede ser peligroso si el programa o servicio tiene fallas de seguridad. |
| **Cerrado (Closed)** | El equipo responde, pero no hay ningún programa usando ese puerto. | No se puede atacar el servicio, pero se sabe que el equipo está encendido. |
| **Filtrado (Filtered)** | Un firewall o antivirus está bloqueando el paso y no deja ver. | Es bueno, significa que las defensas están bloqueando el acceso. |

---

## ¿Cómo se hace el escaneo?

### 1. Escaneo desde la red local (Intranet)
* **Herramienta:** Zenmap (la versión visual de Nmap).
* **Pasos:** Pongo la IP local de la computadora (ej. `192.168.1.X`) y ejecuto un escaneo rápido o intenso.
* **Resultado:** Muestra si hay puertos comunes abiertos en mi red, como el `80` (servidor web) o el `22` (SSH).

### 2. Escaneo desde Internet (IP Pública)
* **Pasos:** Buscar mi IP pública en Google y usar un escáner de puertos en línea para probar esa IP.
* **Puertos importantes a revisar:**
  * `21` (FTP), `22` (SSH), `80` (HTTP), `443` (HTTPS), `3389` (Escritorio remoto / RDP).
* **Mi nota:** Si un puerto de estos sale abierto en mi IP pública sin que yo lo haya configurado a propósito, significa que mi router está dejando pasar conexiones desde todo Internet a mi red privada.

---

## ¿Cómo proteger la red?

1. **Cerrar lo que no se use:** Apagar o deshabilitar servicios que no necesite en la computadora.
2. **Configurar el Firewall:** Dejar activo el firewall para que bloquee conexiones no autorizadas (y los puertos salgan como *filtrados*).
3. **No dejar accesos abiertos:** No abrir puertos como el 3389 (RDP) directamente a Internet; es mejor usar una VPN para conectarse de forma segura.