# Tarea 1: Decisiones y Calidad

**Proyecto:** FinTech & Micro-Préstamos.

**Atributo:** Seguridad (Responsabilidad / Accountability).

**Justificación:** Al gestionar créditos rápidos y transacciones financieras, el sistema maneja datos altamente sensibles. Es imperativo garantizar el "No Repudio", asegurando que exista un registro auditable e inmutable de quién hizo qué en el sistema para cumplir con las normativas financieras, prevenir fraudes y facilitar futuras auditorías forenses.

**Escenario de Calidad:**
* **Fuente:** Un usuario interno autenticado (ej. administrador o analista de crédito).
* **Estímulo:** Intenta modificar, eliminar o alterar el historial de una transacción de micro-préstamo que ya ha sido aprobada y registrada en la base de datos.
* **Respuesta:** El sistema bloquea automáticamente la acción de modificación directa (manteniendo la inmutabilidad del registro), deniega el acceso y genera una alerta crítica registrando el evento en un log de auditoría seguro.
* **Métrica:** El 100% de los intentos de alteración de transacciones deben quedar registrados exitosamente en el log de auditoría con su respectivo ID de usuario, marca de tiempo (timestamp) y detalles de la acción, respondiendo en menos de 1 segundo sin afectar el rendimiento general del sistema.