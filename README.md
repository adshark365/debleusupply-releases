# 🌸 Debleu Supply - Operations Control, AI Studio & Dispatch Engine

> **Versión Oficial:** `v1.0.6`  
> **Plataforma:** Windows Desktop (Electron x64) + Web Apps Móviles  
> **Comercio:** Debleu Supply - Grand Cayman 🇰🇾  
> **Repositorio:** [github.com/adshark365/debleusupply](https://github.com/adshark365/debleusupply)

---

## 📋 Resumen Ejecutivo del Sistema

**Debleu Supply Operations** es la plataforma integral de control de inventario, alistamiento en bodega (picking), despacho de última milla con rastreo en vivo y estudio fotográfico cosmético impulsado por Inteligencia Artificial (Google Gemini).

El sistema opera bajo una arquitectura de **Computadora Madre (Servidor Central Express + SQLite)** y expone 5 portales especializados mediante túneles seguros de Cloudflare:

1. **`admin.debleusupply.ky`**: Panel Maestro de Operaciones (Kanban, RetailEdge POS sync, WooCommerce, gestión de choferes y cuotas).
2. **`picking.debleusupply.ky`**: Interfaz móvil táctil para bodegueros y alistamiento con escáner de código de barras.
3. **`studio.debleusupply.ky`**: Estudio fotográfico móvil (3 fotos: código, frontal e ingredientes) con Gemini Vision y respaldo en Google Drive.
4. **`delivery.debleusupply.ky`**: Portal para conductores con geolocalización GPS automática, vibración háptica y captura de firma digital.
5. **`tracking.debleusupply.ky`**: Seguimiento interactivo en vivo para el cliente final con mapa Leaflet + OpenStreetMap y protección por huella de dispositivo (HWID).

---

## 🚀 Novedades y Características de la Versión 1.0.6

### 1. 🛡️ Vinculación Silenciosa de Dispositivo (HWID Fingerprint)
- **Cero Fricción para el Cliente:** Al pulsar por primera vez el enlace de WhatsApp (`https://tracking.debleusupply.ky/order/1052`), el navegador del comprador calcula silenciosamente una huella digital única del hardware/navegador mediante `device_hwid.js`.
- **Barrera de Privacidad y Anti-Espionaje:** Si el enlace es reenviado a un tercero o abierto desde otro equipo no autorizado, el sistema responde con **HTTP 403 Forbidden** y bloquea la visualización de la dirección particular, teléfono, contenido de la compra y firma de entrega.
- **Control para el Administrador:** Desde el panel de la Computadora Madre, el operador puede ver el dispositivo emparejado (ej. `📱 iPhone • Safari`) y dispone del botón **`[🔓 Desvincular Dispositivo]`** para liberar la orden si el cliente cambió legítimamente de teléfono.

### 2. 🗺️ Rastreo en Vivo 100% Gratuito (Leaflet + OpenStreetMap)
- **Cero Facturación de Google Maps API:** Toda la cartografía opera con capas abiertas de OpenStreetMap y marcadores interactivos en Leaflet.
- **Ping Interactivo de Ubicación:**
  - El cliente cuenta con el botón *"¿Dónde viene mi pedido?"*, el cual hace vibrar el teléfono del repartidor y solicita actualización de GPS con una regla de enfriamiento (*cooldown*) de 10 minutos para no distraerlo en ruta.
  - El Administrador en bodega puede solicitar la ubicación al repartidor en cualquier momento sin límites de tiempo.

### 3. ☁️ Google Drive Multi-Comercio y Almacenamiento en Computadora Madre
- **Carpetas Dinámicas por Número de Negocio:** El Google Drive maestro organiza automáticamente los clientes en subcarpetas con su nombre y número (`/[Nombre]_[NumeroNegocio]/`), permitiendo que múltiples sucursales o clientes compartan la misma cuenta sin colisiones.
- **Persistencia en Computadora Madre:** Las 3 fotos crudas (`01_barcode.jpg`, `02_frontal.jpg`, `03_etiqueta.jpg`) se guardan permanentemente en el disco duro físico de la computadora madre antes de ser transmitidas a Google Drive.
- **Bloqueo Selectivo por Cuota:** La cuenta raíz de Google Drive nunca se desconecta ni se purga; únicamente se pausa la subida a la carpeta del comercio cuando su cuota contratada llega a 0 productos.

### 4. 💎 Planes Comerciales de Recarga y Alertas por Webhook
- **Paquetes Oficiales:**
  - **100 Fotos:** $80 USD
  - **200 Fotos:** $150 USD *(Ahorras $10 USD)*
  - **300 Fotos:** $200 USD *(Ahorras $40 USD)*
- **Notificación Directa al Creador:** Al agotarse la cuota o al solicitar un paquete desde el teléfono o el dashboard, se dispara un Webhook automático (correo/Discord/Formspree) con los datos del pedido para enviar la nueva API Key.
- **Pop-up Festivo de Activación:** Al ingresar la nueva clave, se despliega una ventana modal con animación de confeti y desglose de la nueva cuota.

### 5. 💬 Despacho Obligatorio por WhatsApp
- Para iniciar el alistamiento de una orden en bodega, el botón queda bloqueado con candado hasta que el operario pulse *"💬 Abrir WhatsApp Web con Link de Tracking"*, garantizando que todo comprador reciba su enlace de seguimiento en tiempo y forma.

### 6. 👑 Modo Administrador & Switch Operador (PIN Maestro `9999`)
- **Apertura Directa Sin Bloqueos Invasivos:** La aplicación arranca de inmediato en **Modo Operador** mostrando lo esencial para el equipo de tienda: tablero Kanban, alistamiento de pedidos, directorio de personal, domiciliarios, reportes y trazabilidad en vivo, sin pantallas que impidan la visualización.
- **Switch de Modo en Barra Superior:** Botón interactivo en la cabecera que permite alternar fácilmente entre `👤 Modo Operador` (operaciones diarias y lectura) y `👑 Modo Administrador` (control y edición total).
- **Acciones Protegidas por PIN:** Únicamente en Modo Administrador se permite agregar, editar o eliminar personal, agregar o eliminar domiciliarios, desvincular dispositivos HWID, descartar órdenes, crear roles, configurar módulos o cambiar credenciales de API.
- **PIN por Defecto:** El PIN inicial maestro de fábrica es **`9999`**.
- **Recuperación Segura por Correo:** Si el administrador olvida el PIN, cuenta con la opción *"¿Olvidaste tu PIN?"*, la cual envía un código OTP de seguridad de 6 dígitos al correo de recuperación registrado (`admin@debleusupply.ky` por defecto, personalizable) con vigencia de 15 minutos para restablecer el PIN de inmediato.
- **Gestión y Activación de Módulos:** Pestaña dedicada para encender o pausar módulos según la operativa (Picking, AI Studio, Despacho, Live Tracking, Portal WiFi, WooCommerce, RetailEdge POS).
- **Creador de Roles Dinámicos:** Permite crear nuevos perfiles de usuario con permisos personalizados (`can_add`, `can_edit`, `can_delete`, `can_config`), los cuales se reflejan automáticamente en el formulario de alta de personal.

---

## 📦 Archivos de Distribución (Compilados en `dist-release/` y `dist/`)

| Archivo | Tipo | Descripción |
| :--- | :--- | :--- |
| **`Debleu Supply Setup 1.0.6.exe`** | Instalador NSIS | Instalador ejecutable estándar para Windows 10/11 con auto-actualizador. |
| **`Debleu Supply Setup 1.0.6.exe.blockmap`** | Blockmap | Mapa de bloques binarios para descargas diferenciales ultrarrápidas de electron-updater. |
| **`Debleu Supply Portable 1.0.6.exe`** | Ejecutable Portable | Versión lista para usar sin necesidad de privilegios de administrador ni instalación. |
| **`Debleu Supply-1.0.6-win.zip`** | Archivo Comprimido | Binarios completos portables empaquetados en formato ZIP. |
| **`latest.yml`** | Manifiesto de Versión | Archivo de metadatos SHA-512 y tamaño para el canal de actualización oficial de instaladores. |
| **`version.json`** | Manifiesto Enriquecido | Metadatos para auto-actualización de versiones portables, notas de lanzamiento y respaldo multi-espejo. |

---

## 🛠️ Instrucciones de Ejecución y Desarrollo

### Requisitos Previos
- **Sistema Operativo:** Windows 10 o Windows 11 (64 bits)
- **Node.js:** Versión 18 o superior
- **Git** configurado

### Puesta en Marcha Local
```bash
# 1. Clonar el repositorio
git clone https://github.com/adshark365/debleusupply.git
cd debleusupply

# 2. Instalar dependencias
npm install

# 3. Iniciar la aplicación en modo desarrollo (Desktop Electron + Servidor Express)
npm start
