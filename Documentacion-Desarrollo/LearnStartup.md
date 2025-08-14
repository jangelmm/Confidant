# **Lean Startup aplicado a Confidant** 

## **1. Hipótesis**

* **Hipótesis de problema**:
  Usuarios individuales y profesionales manejan archivos de configuración críticos (MEGA, Duplicati, .json, .aes, .txt, .pdf, .mp4) dispersos en múltiples ubicaciones, sin una herramienta centralizada y segura que permita gestionarlos fácilmente y migrarlos entre dispositivos.

* **Hipótesis de solución**:
  Una aplicación **Java** open source con **MVC, Swing, JPA y SQLite**, que permita almacenar, organizar y cifrar estos archivos con metadatos, y exportar/importar la base de datos completa de manera segura, será adoptada rápidamente por usuarios que valoren la simplicidad, seguridad y portabilidad.

---

## **2. Producto Mínimo Viable (MVP)**

* **Funcionalidad mínima**:

  1. Añadir archivos de configuración a la base de datos con metadatos: nombre, fecha, descripción, ubicación, tipo de archivo.
  2. Guardar los archivos como BLOBs cifrados (AES).
  3. Listar y buscar archivos por nombre, fecha o tipo.
  4. Exportar e importar la base de datos SQLite cifrada.

* **Experiencia mínima**:

  * Interfaz gráfica en Swing con tabla de archivos y botones para:

    * Añadir
    * Eliminar
    * Exportar
    * Importar
  * Feedback visual simple: confirmaciones, barras de progreso en operaciones de cifrado/descifrado y exportación.

---

## **3. Métricas de Éxito (MVP)**

* **Cuantitativas**:

  * Número de descargas o repositorios clonados.
  * Cantidad de archivos gestionados por usuario (medido internamente en la aplicación).
  * Tiempo promedio de uso por sesión y frecuencia de exportación/importación.

* **Cualitativas**:

  * Feedback positivo de usuarios sobre la facilidad de uso y seguridad.
  * Solicitudes de nuevas funcionalidades, como soporte para tipos de archivos adicionales, etiquetas o filtros avanzados.

---

## **4. Ciclo de Validación**

1. **Construir** → Crear la versión mínima con:

   * Interfaz básica en Swing
   * Gestión de archivos cifrados
   * Metadatos y búsqueda básica
   * Exportación/importación de la base de datos

2. **Medir** → Compartir con usuarios que gestionen configuraciones críticas, foros de software open source y comunidades de IT.

3. **Aprender** → Ajustar la aplicación según feedback:

   * Mejorar interfaz y experiencia de usuario
   * Optimizar almacenamiento y rendimiento
   * Agregar funcionalidades solicitadas (etiquetas, filtros, backups automáticos)


