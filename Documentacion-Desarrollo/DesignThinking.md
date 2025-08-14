# **Design Thinking aplicado a Confidant**

## **1. Descubrimiento / Empatía / Investigación (Divergencia)**

* **Contexto detectado**: Muchos usuarios manejan archivos de configuración críticos (.json, .txt, .aes, etc.) de diferentes aplicaciones (MEGA, Duplicati, etc.):

  * Se almacenan de forma dispersa en múltiples carpetas y dispositivos.
  * Su gestión manual es propensa a errores y pérdidas de información.
  * No hay una herramienta ligera que permita centralizar, organizar y proteger estos archivos de forma segura.

* **Necesidades de los usuarios**:

  * Guardar y organizar archivos de configuración de múltiples aplicaciones.
  * Registrar metadatos importantes: nombre, fecha, descripción, ubicación, tipo de archivo.
  * Exportar e importar la base de datos para usarla en otras computadoras.
  * Mantener los archivos y datos **encriptados** para proteger información sensible.

* **Hallazgos clave**:

  * Escasez de soluciones open source, multiplataforma, y fáciles de usar para la gestión segura de configuraciones.
  * Demanda de un software que combine interfaz gráfica (Swing) y backend sólido (JPA + SQLite).

---

## **2. Definición / Síntesis (Divergencia)**

* **Problema a resolver**:
  *"Actualmente no existe una aplicación ligera, segura y fácil de usar que centralice, gestione y proteja archivos de configuración críticos, permitiendo también su exportación e importación entre dispositivos."*

* **Oportunidad de mercado**:

  * Crear una solución **minimalista pero segura**, que permita a usuarios individuales o profesionales gestionar archivos de configuración sin depender de múltiples herramientas.
  * Facilitar la migración de configuraciones entre dispositivos mediante exportación/importación de bases de datos cifradas.
  * Crecer modularmente: agregar encriptación avanzada, etiquetas, filtros y compatibilidad con más tipos de archivo.

---

## **3. Ideación (Divergencia y Convergencia)**

* **Lluvia de ideas de funciones iniciales**:

  * Almacenamiento seguro de archivos de configuración (.txt, .json, .aes, .mp4, .pdf, etc.).
  * Registro de metadatos: nombre, fecha, descripción, ubicación, tipo de archivo.
  * Búsqueda rápida por nombre, tipo o fecha.
  * Exportación e importación de la base de datos completa, cifrada con AES.
  * Interfaz gráfica sencilla en Swing y arquitectura MVC para mantenimiento y escalabilidad.
  * Integración de SQLite con JPA para persistencia robusta.

* **Selección para primera versión**:

  * Interfaz gráfica básica con lista de archivos y botones de añadir, eliminar, exportar e importar.
  * Guardado de archivos pequeños y medianos en BLOBs cifrados.
  * Registro de metadatos en SQLite.
  * Exportación/importación de base de datos cifrada.

---

## **4. Implementación / Construcción (Divergencia y Convergencia)**

* **Primera iteración (v0.1)**:

  * Diseño del modelo MVC:

    * **Modelo:** Clases `ArchivoConfig` y `BaseDatosConfig` con JPA para persistencia.
    * **Vista:** Swing con JTable para mostrar archivos y formularios de metadatos.
    * **Controlador:** Gestión de eventos y operaciones CRUD.
  * Implementación de lectura/escritura de archivos en BLOBs cifrados (AES).
  * Exportación/importación de base de datos SQLite completa con cifrado.

* **Pruebas y feedback**:

  * Compartir prototipo con usuarios que manejan configuraciones críticas (MEGA, Duplicati, otros).
  * Ajustar interfaz, flujos de exportación/importación y encriptación según comentarios.

* **Iteraciones siguientes**:

  * Agregar soporte para filtros avanzados y etiquetas.
  * Optimización de rendimiento al manejar archivos grandes (estrategia BLOB vs ruta cifrada).
  * Funcionalidades de backup automático y recuperación de archivos.
