# Guía Oficial de Usuario y Funcionamiento: SaaS "FlowPulse"

**Versión del Sistema:** 2.4  
**Última actualización:** Agosto 2026  
**Categoría:** Plataforma de Automatización de Flujos y Métrica de Procesos

---

## 1. Introducción a FlowPulse

FlowPulse es una plataforma SaaS diseñada para centralizar, monitorear y optimizar la ejecución de flujos de trabajo en empresas digitales. Permite conectar distintas herramientas operativas para medir cuellos de botella en tiempo real y reducir tareas repetitivas mediante reglas automatizadas.

### 1.1 Requisitos del Sistema
* Navegador web moderno (Google Chrome 110+, Mozilla Firefox 115+, Safari 16+).
* Conexión a internet estable con un ancho de banda mínimo de 5 Mbps.
* Cuenta activa con rol de **Administrador** o **Editor** para crear flujos.

---

## 2. Gestión de Usuarios y Permisos

Para mantener la seguridad de la información organizativa, FlowPulse estructura los accesos mediante un sistema de Roles Basados en Permisos (RBAC).

### 2.1 Roles Disponibles
* **Owner (Propietario):** Acceso total a la facturación, integración de pasarelas de pago y eliminación de la organización.
* **Admin (Administrador):** Puede invitar miembros, modificar permisos, crear y eliminar flujos de trabajo, y gestionar llaves de API.
* **Editor:** Puede crear, modificar y ejecutar flujos de trabajo, pero no tiene acceso a la configuración global de la cuenta.
* **Viewer (Observador):** Solo lectura. Puede ver métricas y paneles de control sin modificar ninguna automatización.

### 2.2 Cómo Invitar un Nuevo Usuario
1. Dirígete al menú lateral izquierdo y haz clic en **Ajustes de Organización**.
2. Selecciona la pestaña **Miembros y Equipo**.
3. Haz clic en el botón azul **Invitar Miembro**.
4. Ingresa el correo electrónico del usuario y asigna el rol correspondiente.
5. Haz clic en **Enviar Invitación**. El usuario recibirá un enlace con validez de 72 horas.

---

## 3. Configuración de Integraciones y Webhooks

FlowPulse permite conectar aplicaciones externas para recibir y enviar datos mediante Webhooks y llaves de API de forma segura.

### 3.1 Crear una Llave de API (API Key)
1. Ve a **Ajustes > Integraciones > API Keys**.
2. Presiona el botón **Generar Nueva Clave**.
3. Asigna un nombre descriptivo (ejemplo: *Integración CRM Producción*).
4. Copia la clave generada inmediatamente. **Nota:** Por motivos de seguridad, la clave solo se mostrará una vez.

### 3.2 Configuración de Webhooks Entrantes
Los Webhooks permiten que sistemas externos ejecuten disparadores dentro de FlowPulse en tiempo real.

1. Dentro de tu panel, navega a **Automatizaciones > Webhooks Entrantes**.
2. Haz clic en **Crear Webhook**.
3. Asigna un nombre al Webhook y selecciona el evento que escuchará (ejemplo: `order.created` o `user.signup`).
4. Copia la **URL de destino** proporcionada por FlowPulse y pégala en la configuración del servicio externo.
5. Haz clic en **Guardar y Probar**.

---

## 4. Facturación, Planes y Cancelación

FlowPulse ofrece distintos planes adaptados al volumen de tareas ejecutadas al mes.

### 4.1 Cambiar de Plan o Añadir Tareas Extra
* **Plan Starter:** Incluye hasta 10,000 tareas mensuales y 3 usuarios.
* **Plan Pro:** Incluye hasta 100,000 tareas mensuales, usuarios ilimitados y soporte prioritario.
* **Plan Enterprise:** Tareas ilimitadas, servidor dedicado y SLA garantizado del 99.9%.

Para cambiar tu plan, ve a **Ajustes > Facturación > Cambiar Plan**, selecciona el plan deseado y confirma los datos de tu tarjeta de crédito o débito.

### 4.2 Proceso de Cancelación de Suscripción
Si deseas cancelar el servicio, la solicitud debe realizarse antes de la fecha de corte mensual:

1. Ve al apartado **Ajustes > Facturación**.
2. Desplázate hasta la parte inferior y selecciona **Cancelar Suscripción**.
3. Selecciona el motivo de tu salida y presiona **Confirmar Cancelación**.
4. Tu cuenta permanecerá activa hasta el final del periodo de facturación vigente, tras lo cual pasará a modo *Solo Lectura* durante 30 días antes de la depuración final de datos.

---

## 5. Preguntas Frecuentes y Solución de Problemas

### 5.1 ¿Qué ocurre si excedo el límite de tareas de mi plan?
Si superas el límite asignado en tu ciclo mensual, las automatizaciones no se detendrán. El sistema aplicará una tarifa de sobrecosto automáticamente de $0.002 USD por cada tarea adicional ejecutada y se reflejará en tu siguiente factura.

### 5.2 Error 401 Unauthorized en Webhooks
Este error ocurre cuando la llamada HTTP no incluye el encabezado de autenticación correcto. Asegúrate de enviar la cabecera `Authorization: Bearer TU_API_KEY` en cada petición HTTP hacia la API de FlowPulse.
