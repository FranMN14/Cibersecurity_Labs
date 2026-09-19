# Lab Write-up: Análisis de Brechas de Seguridad y Medidas Mitigadoras

##  Objetivo
Analizar escenarios reales de filtración de datos para identificar el vector de ataque, los activos comprometidos y las medidas preventivas necesarias para mitigar estos riesgos en un entorno corporativo.

---

##  Escenarios de Estudio

### 1. Brecha de Datos en Cadena Hotelera
* **Vector de ataque:** Robo/uso no autorizado de credenciales de un empleado.
* **Impacto:** Exposición de datos personales (nombres, correos, teléfonos) de más de 3 millones de clientes.
* **Análisis de riesgo:** La falta de autenticación robusta permitió que el acceso a una sola cuenta de empleado comprometiera la base de datos central de clientes.

### 2. Exposición de Datos en Plataforma de eLearning
* **Vector de ataque:** Mala configuración de almacenamiento en la nube (base de datos expuesta públicamente a Internet).
* **Impacto:** Datos de estudiantes al descubierto, facilitando futuros ataques de *Phishing* o *Social Engineering*.
* **Análisis de riesgo:** Inexistencia de controles de acceso restrictivos y segmentación de red adecuada para recursos en la nube.

---

##  Medidas de Mitigación y Buenas Prácticas

Para prevenir incidentes similares, las organizaciones deben implementar controles de seguridad en múltiples capas (Defense in Depth):

1. **Gestión de Identidades y Accesos (IAM):**
   * Implementar **Autenticación de Doble Factor (2FA/MFA)** obligatoria para todas las cuentas de empleados.
   * Aplicar el principio de **menor privilegio** (Least Privilege).

2. **Seguridad en la Nube y Redes:**
   * **Segmentación de red:** Aislar las bases de datos en subredes privadas sin acceso directo a la Internet pública.
   * Restringir el acceso administrativo únicamente mediante conexiones **VPN** seguras.

3. **Protección de Datos y Monitoreo:**
   * **Cifrado de datos:** Proteger datos en reposo y en tránsito (utilizando algoritmos de Hashing robustos con *salting* para credenciales).
   * **Monitoreo continuo:** Revisión activa de *logs* e implementación de un SIEM/HIDS para detectar anomalías en el comportamiento de los usuarios.
   * **Concientización:** Capacitación constante al personal en detección de *Phishing* e ingeniería social.

---

##  Conclusión
Las brechas de seguridad suelen originarse por errores de configuración en la infraestructura o credenciales comprometidas. La implementación de controles de acceso estrictos, el monitoreo constante y la correcta configuración de servicios en la nube son fundamentales para garantizar la confidencialidad de la información.
