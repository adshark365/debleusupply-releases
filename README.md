<div align="center">

# 🌸 Debleu Supply - Official Distribution Portal

[![Latest Release](https://img.shields.io/github/v/release/adshark365/debleusupply-releases?color=7c3aed&label=Versi%C3%B3n%20Oficial&logo=github)](https://github.com/adshark365/debleusupply-releases/releases/latest)
[![Version](https://img.shields.io/badge/Versi%C3%B3n%20Actual-v1.0.3-emerald)](https://github.com/adshark365/debleusupply-releases/releases/latest)
[![Platform](https://img.shields.io/badge/Plataforma-Windows%2010%20%7C%2011%20(64--bit)-0078D6?logo=windows)](https://github.com/adshark365/debleusupply-releases/releases/latest)
[![Auto-Updater](https://img.shields.io/badge/Auto--Updater-Multi--Espejo%20Activo-10B981?logo=electron)](https://github.com/adshark365/debleusupply-releases/releases/latest)

<p align="center">
  <b>Terminal de Operaciones, Sincronización Omnicanal de Inventario, Picking Móvil, Wi-Fi CRM y Gestión de Tienda</b>
</p>

[📥 Descargar Última Versión (v1.0.3)](https://github.com/adshark365/debleusupply-releases/releases/latest) •
[📋 Todas las Versiones](https://github.com/adshark365/debleusupply-releases/releases) •
[❓ Guía de Instalación](#-gu%C3%ADa-de-instalaci%C3%B3n-y-primer-uso)

---

</div>

## 📌 Acerca de este Repositorio
Este es el **Repositorio Espejo Oficial de Distribución y Actualizaciones** de **Debleu Supply**.  
Aquí se publican exclusivamente los paquetes ejecutables terminados, firmas de integridad y manifiestos de actualización automática en segundo plano para las terminales de operación autorizadas.

---

## 📦 Enlaces de Descarga Directa (Versión 1.0.3)

Seleccione el tipo de descarga según sus necesidades:

| Tipo | Archivo de Descarga Directa | Recomendado para |
| :--- | :--- | :--- |
| ⭐ **Instalador Oficial (Recomendado)** | [**`Debleu.Supply.Setup.1.0.3.exe`**](https://github.com/adshark365/debleusupply-releases/releases/latest/download/Debleu.Supply.Setup.1.0.3.exe) | **Instalación estándar en la PC Principal.** Instala el programa en el sistema y habilita el botón de **actualizaciones automáticas en segundo plano**. |
| 🛡️ **Paquete Comprimido (ZIP)** | [**`Debleu.Supply-1.0.3-win.zip`**](https://github.com/adshark365/debleusupply-releases/releases/latest/download/Debleu.Supply-1.0.3-win.zip) | Ideal para enviar por correo electrónico o WhatsApp. Descomprima y ejecute para evitar alertas de antivirus. |
| 🔌 **Ejecutable Portable** | [**`Debleu.Supply.Portable.1.0.3.exe`**](https://github.com/adshark365/debleusupply-releases/releases/latest/download/Debleu.Supply.Portable.1.0.3.exe) | Uso inmediato sin instalación previa. Ideal para memorias USB o terminales secundarias. |

> 👉 Para ver la página oficial de la versión con el changelog completo, visite [**Releases Oficiales v1.0.3**](https://github.com/adshark365/debleusupply-releases/releases/latest).

---

## 🚀 Novedades y Capacidades en la Versión 1.0.3

* 🛒 **Sincronización Bidireccional Activa con WooCommerce:**
  * Detección automática en tiempo real de nuevos pedidos web cada 20 segundos (sin requerir webhooks ni configuración de puertos).
  * Soporte completo para pedidos enviados por WhatsApp y Pago Contra Entrega (COD).
  * Al cambiar el estado de un pedido en el Kanban (Listo, Despachado, Cancelado, Devolución), el estado se actualiza automáticamente en la tienda online.
* 🗑️ **Descarte y Eliminación de Pedidos:** Botón para eliminar órdenes de prueba tanto localmente como en la papelera de WooCommerce, garantizando que nunca más vuelvan a importarse.
* 📶 **Portal Cautivo Wi-Fi con Captura de Leads:**
  * Formulario de registro con indicativo de **Islas Caimán (`🇰🇾 +1 345`)** por defecto y opciones internacionales.
  * Acceso temporal de cortesía por **1 minuto** mientras el cliente verifica su correo con un código PIN de 6 dígitos.
  * Al validar el código, se desbloquean los 30 min / 1 hora de conexión y se entrega el cupón promocional de tienda.
* 👥 **Módulo Wi-Fi CRM & Métricas de Clientes:**
  * Métricas en tiempo real: Total de clientes capturados, tasa de verificación, clientes locales vs. turistas.
  * Exportación de la base de datos de clientes a **Excel (CSV)**.
  * Botón directo de **WhatsApp** por cliente con plantilla promocional personalizada.
  * Aprobación rápida desde mostrador para clientes sin datos móviles.
* 🛡️ **Protección de Base de Datos:** Los clientes, pedidos e historial quedan almacenados de forma persistente y no se borran al actualizar la aplicación.

---

## 🛠️ Guía de Instalación y Primer Uso

### 1. Instalación Estándar (Recomendada)
1. Descargue el archivo [**`Debleu.Supply.Setup.1.0.3.exe`**](https://github.com/adshark365/debleusupply-releases/releases/latest/download/Debleu.Supply.Setup.1.0.3.exe).
2. Haga doble clic para iniciar el instalador.
3. El programa creará automáticamente el acceso directo en el Escritorio y en el Menú Inicio.

### 2. Aviso de Windows SmartScreen (Primera Ejecución)
Al ser una aplicación empresarial propietaria sin firma de certificado comercial público de Microsoft, es normal que Windows muestre una advertencia de protección:

```text
╔════════════════════════════════════════════════════════════════╗
║  Windows protegió su PC (SmartScreen)                          ║
║  Windows Defender evitó el inicio de una aplicación...         ║
╚════════════════════════════════════════════════════════════════╝
