# Blueprint Maestro de Arquitectura de Software (MVP)
> **Proyecto:** FinTech & Micro-Préstamos

## Sección 1: Estrategia y Alcance

### 1.1 Contexto del Negocio
Actualmente existe una creciente necesidad de soluciones financieras digitales que permitan a los usuarios acceder a préstamos de forma rápida y sencilla. Los procesos tradicionales suelen requerir múltiples trámites y tiempos de espera prolongados.

Como respuesta a esta necesidad, se propone el desarrollo de una plataforma **FinTech** orientada a la gestión de micro-préstamos. El sistema buscará facilitar la solicitud, administración y seguimiento de créditos mediante una plataforma digital accesible y segura.

### 1.2 Objetivo General
Diseñar la arquitectura de un sistema de micro-préstamos que permita administrar solicitudes de crédito, préstamos aprobados, pagos y registros de auditoría, garantizando seguridad, trazabilidad y facilidad de mantenimiento.

### 1.3 Objetivos Específicos
* Gestionar el registro y autenticación de usuarios.
* Permitir la solicitud y evaluación de préstamos.
* Administrar préstamos activos.
* Registrar pagos realizados por los usuarios.
* Mantener registros de auditoría para operaciones críticas.
* Generar notificaciones relacionadas con el estado de los préstamos.

### 1.4 Alcance del MVP
El Producto Mínimo Viable contemplará únicamente las funcionalidades esenciales para demostrar la viabilidad del proyecto.

**Incluye:**
* Gestión de usuarios.
* Solicitudes de préstamo.
* Administración de préstamos.
* Registro de pagos.
* Notificaciones.
* Auditoría.

*No incluye funcionalidades avanzadas como inteligencia artificial, aplicaciones móviles nativas o integraciones bancarias automáticas.*

### 1.5 Expectativas del Usuario
Se espera que la plataforma ofrezca una experiencia sencilla, segura y eficiente para la gestión de micro-préstamos, permitiendo consultar solicitudes, préstamos y pagos de forma rápida y confiable.

---

## Sección 2: Requerimientos del Sistema

### 2.1 Requerimientos Funcionales (RF)
* **RF-01:** Registro de usuarios.
* **RF-02:** Inicio de sesión.
* **RF-03:** Solicitud de préstamos.
* **RF-04:** Evaluación y aprobación de solicitudes.
* **RF-05:** Administración de préstamos.
* **RF-06:** Registro de pagos.
* **RF-07:** Envío de notificaciones.
* **RF-08:** Registro de auditoría.

### 2.2 Requerimientos No Funcionales (RNF)
* **RNF-01:** Seguridad de la información.
* **RNF-02:** Disponibilidad del servicio.
* **RNF-03:** Buen rendimiento del sistema.
* **RNF-04:** Facilidad de mantenimiento.
* **RNF-05:** Escalabilidad para futuras mejoras.

---

## Sección 3: Atributos de Calidad Prioritarios

### 3.1 Seguridad
La **seguridad** es el atributo de calidad más importante dentro del proyecto FinTech, debido a que el sistema administrará información personal y financiera de los usuarios. Es fundamental garantizar que los datos se encuentren protegidos contra accesos no autorizados, modificaciones indebidas y posibles intentos de fraude.

Para lograrlo, se propone implementar mecanismos de autenticación de usuarios, control de acceso basado en roles y registros de auditoría que permitan conocer quién realizó cada acción dentro del sistema. 

### 3.2 Disponibilidad
La **disponibilidad** busca garantizar que los usuarios puedan acceder al sistema cuando necesiten consultar información, solicitar préstamos o registrar pagos. 

Ante posibles fallos de infraestructura o problemas temporales de conectividad *(estrategia ante la Caja Rota)*, el sistema deberá responder mediante mensajes claros y controlados, evitando mostrar errores técnicos (Stacktrace) que puedan confundir al usuario o representar un riesgo de seguridad.

### 3.3 Mantenibilidad
La **mantenibilidad** permitirá que el sistema pueda evolucionar conforme aumenten las necesidades del negocio. Por ello, la arquitectura propuesta busca mantener una separación clara entre la interfaz, la lógica de negocio y la base de datos, facilitando futuras modificaciones sin afectar el funcionamiento general del sistema.

### 3.4 Interoperabilidad
La **interoperabilidad** permitirá que el sistema pueda comunicarse con servicios externos en futuras versiones del proyecto (plataformas de notificaciones, validación de información, APIs de terceros). La arquitectura seleccionada permitirá incorporar nuevas integraciones mediante adaptadores especializados.

---

## Sección 4: Propuesta Arquitectónica

### 4.1 Arquitectura Cliente-Servidor
Para el desarrollo del sistema se propone utilizar una **Arquitectura Cliente-Servidor**. Este modelo divide la aplicación en dos partes principales:

* **Cliente (Frontend):** Representa la interfaz con la que interactúan los usuarios para capturar solicitudes, mostrar formularios y presentar resultados.
* **Servidor (Backend):** Responsable de procesar las solicitudes recibidas, aplicar las reglas de negocio, validar la información y gestionar el acceso a la base de datos.

### 4.2 Arquitectura Hexagonal
Además, se propone utilizar una **Arquitectura Hexagonal** (Puertos y Adaptadores) para aislar la lógica principal de los componentes externos.

* **Núcleo (Core):** Alojará los procesos relacionados con la gestión de usuarios, préstamos, pagos y auditoría. Mantener estas reglas separadas permite modificar componentes sin afectar el sistema central.
* **Adaptadores:** Permitirán la comunicación con la base de datos (PostgreSQL), servicios de notificaciones y futuras integraciones.

### 4.3 Justificación y Conclusión
La combinación de ambas arquitecturas facilita la organización mediante la separación de responsabilidades, mientras que protege la lógica del negocio. Mediante la definición de estos requerimientos y atributos de calidad, se garantiza un sistema seguro, mantenible y preparado para el crecimiento de la plataforma FinTech.