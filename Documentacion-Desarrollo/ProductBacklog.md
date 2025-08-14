# **Product Backlog – Confidant**

---

# Historias de Usuario:

## **HU1 – Agregar archivo con metadatos**

**Historia de Usuario:**
Como usuario, quiero agregar archivos de configuración a la base de datos con metadatos (nombre, fecha, descripción, ubicación, tipo) para poder gestionarlos de manera organizada.

**Criterios de aceptación:**

* Se puede agregar un archivo seleccionando su ruta.
* Se capturan metadatos: nombre, tipo, fecha y descripción.
* Se almacena en la base de datos SQLite.

**Tareas técnicas:**

* Implementar formulario Swing para agregar archivo y metadatos.
* Validar existencia del archivo y formato del nombre.
* Crear entidad `ArchivoConfig` en JPA.

---

## **HU2 – Cifrado de archivos**

**Historia de Usuario:**
Como usuario, quiero que los archivos se guarden cifrados para proteger información sensible.

**Criterios de aceptación:**

* Archivos se guardan como BLOB cifrado con AES.
* Se descifran solo al exportar o visualizar según permisos.

**Tareas técnicas:**

* Implementar clase `CifradoUtils` para cifrado/descifrado.
* Integrar cifrado en el método de guardado de `BaseDatosConfig`.
* Pruebas unitarias de cifrado y descifrado.

---

## **HU3 – Buscar y filtrar archivos**

**Historia de Usuario:**
Como usuario, quiero buscar y filtrar archivos por nombre, tipo o fecha para encontrar rápidamente lo que necesito.

**Criterios de aceptación:**

* Soporta búsqueda parcial por nombre.
* Filtrado por tipo de archivo y rango de fechas.
* Resultados se muestran en JTable de Swing.

**Tareas técnicas:**

* Crear métodos de búsqueda en `BaseDatosConfig`.
* Integrar filtros en la interfaz Swing.
* Pruebas unitarias de consultas.

---

## **HU4 – Eliminar archivo de manera segura**

**Historia de Usuario:**
Como usuario, quiero eliminar archivos de la base de datos de manera segura para mantener organizada la información.

**Criterios de aceptación:**

* Confirmación antes de eliminar.
* Se borra el registro y el BLOB asociado.
* Actualización de la vista en tiempo real.

**Tareas técnicas:**

* Implementar método `eliminarArchivo(id)` en `BaseDatosConfig`.
* Confirmaciones en Swing.
* Pruebas de eliminación y consistencia de BD.

---

## **HU5 – Exportar base de datos cifrada**

**Historia de Usuario:**
Como usuario, quiero exportar la base de datos completa cifrada para usarla en otra computadora.

**Criterios de aceptación:**

* Genera archivo `.db` cifrado con todos los archivos y metadatos.
* Incluye confirmación de éxito.
* Maneja errores de disco o permisos.

**Tareas técnicas:**

* Implementar método `exportarBD(path)` en `BaseDatosConfig`.
* Barra de progreso en Swing.
* Pruebas de integridad tras exportación/importación.

---

## **HU6 – Importar base de datos cifrada**

**Historia de Usuario:**
Como usuario, quiero importar una base de datos cifrada para restaurar archivos y metadatos.

**Criterios de aceptación:**

* Se verifica integridad y compatibilidad.
* Se actualiza la vista con los archivos importados.
* Mensajes de error claros en caso de fallo.

**Tareas técnicas:**

* Implementar método `importarBD(path)` en `BaseDatosConfig`.
* Barra de progreso y feedback visual en Swing.
* Pruebas de restauración con distintos escenarios.

---

## **HU7 – Pruebas unitarias**

**Historia de Usuario:**
Como desarrollador, quiero tener pruebas unitarias para garantizar que la persistencia y el cifrado funcionan correctamente.

**Criterios de aceptación:**

* Pruebas para CRUD completo de archivos.
* Pruebas de cifrado y descifrado.
* Integración en workflow CI/CD.

**Tareas técnicas:**

* Configurar JUnit 5 para pruebas.
* Crear dataset de prueba con distintos tipos de archivo.
* Integrar tests en Maven/Gradle.

---

## **HU8 – Feedback visual en interfaz**

**Historia de Usuario:**
Como usuario, quiero ver confirmaciones y progreso en la interfaz gráfica al añadir, cifrar, exportar o importar archivos.

**Criterios de aceptación:**

* Mensajes de confirmación y error visibles.
* Barra de progreso en operaciones de cifrado/descifrado y export/import.
* Actualización inmediata de JTable tras cambios.

**Tareas técnicas:**

* Implementar barra de progreso Swing.
* Mensajes visuales usando `JOptionPane` o panel de logs.
* Pruebas de UI y consistencia visual.

---

## **HU9 – Documentación inicial**

**Historia de Usuario:**
Como usuario, quiero contar con una guía rápida para usar Confidant.

**Criterios de aceptación:**

* README con instrucciones de instalación y uso.
* Ejemplos de agregar, eliminar, exportar e importar archivos.
* Capturas de pantalla de la interfaz.

**Tareas técnicas:**

* Escribir README.md.
* Crear carpeta `/examples` con archivos de prueba.
* Documentar clases principales y flujo de la aplicación.

---

### Tabla resumida

```
Título,Descripción,Etiqueta,Prioridad
HU1 – Agregar archivo con metadatos,"Como usuario, quiero agregar archivos de configuración a la base de datos con metadatos (nombre, fecha, descripción, ubicación, tipo).",Sprint 1,Alta
HU2 – Cifrado de archivos,"Como usuario, quiero que los archivos se guarden cifrados para proteger información sensible.",Sprint 2,Alta
HU3 – Buscar y filtrar archivos,"Como usuario, quiero buscar y filtrar archivos por nombre, tipo o fecha para encontrar rápidamente lo que necesito.",Sprint 1,Media
HU4 – Eliminar archivo de manera segura,"Como usuario, quiero eliminar archivos de la base de datos de manera segura para mantener organizada la información.",Sprint 1,Media
HU5 – Exportar base de datos cifrada,"Como usuario, quiero exportar la base de datos completa cifrada para usarla en otra computadora.",Sprint 2,Alta
HU6 – Importar base de datos cifrada,"Como usuario, quiero importar una base de datos cifrada para restaurar archivos y metadatos.",Sprint 2,Alta
HU7 – Pruebas unitarias,"Como desarrollador, quiero tener pruebas unitarias para garantizar que la persistencia y el cifrado funcionan correctamente.",Sprint 1,Alta
HU8 – Feedback visual en interfaz,"Como usuario, quiero ver confirmaciones y progreso en la interfaz gráfica al añadir, cifrar, exportar o importar archivos.",Sprint 2,Media
HU9 – Documentación inicial,"Como usuario, quiero contar con una guía rápida para usar Confidant.",Sprint 3,Media
```

---

# Historias Épicas

## **E1 – Funcionalidad**

Como usuario, quiero una herramienta completa de gestión de archivos de configuración que permita agregar, cifrar, buscar, eliminar, exportar e importar archivos fácilmente.

**HU involucradas:** HU1 – HU6

## **E2 – Experiencia y seguridad**

Como usuario y desarrollador, quiero una interfaz clara con feedback visual, barra de progreso, pruebas unitarias y documentación completa, garantizando seguridad y facilidad de uso.

**HU involucradas:** HU7 – HU9

