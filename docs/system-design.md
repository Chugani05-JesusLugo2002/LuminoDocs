---
hide:
  - navigation
---


# **Diseño del sistema**

<div align="center">
   <img src="./img/design.gif" alt="Cover">
</div>

## **Modelo de datos**

**Modelo entidad-relación:** utilizado para representar de manera gráfica y conceptual la estructura de una base de datos, definiendo las entidades, atributos y relaciones entre ellas.

<div align=center>
    <img src="../diagrams/ER-model.drawio.png" alt="ER model" width="70%">
</div>

**Modelo relacional:** sirve para organizar la información en tablas, como una hoja de cálculo, donde cada fila es un dato específico y cada columna describe sus características.

<div align=center>
    <img src="../diagrams/RM-model.drawio.png" alt="RM model" width="80%">
</div>

## **Decisiones de diseño**

### Justificación de Tecnologías

- **Django:** Elegido por ser un framework robusto y escalable que facilita el desarrollo rápido de aplicaciones web seguras gracias a su arquitectura basada en el patrón MTV (Modelo-Template-Vista) y su enfoque en DRY (Don’t Repeat Yourself).
- **Pillow:** Permite manipular imágenes de manera eficiente, lo cual es fundamental para funcionalidades como redimensionamiento, conversión de formatos, o generación de imágenes dinámicas.
- **IPython:** Herramienta interactiva ideal para depuración y pruebas rápidas de funciones Python durante el desarrollo.
- **crispy-bootstrap5:** Facilita la integración de Bootstrap 5 en formularios de Django, mejorando la estética y la accesibilidad sin necesidad de escribir manualmente HTML extenso para formularios estilizados.
- **django-browser-reload:** Aumenta la productividad durante el desarrollo mediante la recarga automática del navegador cuando se realizan cambios en el código o en los archivos estáticos.
- **django-markdownify:** Permite convertir contenido en formato Markdown a HTML, lo cual resulta útil para mostrar textos ricos (artículos, comentarios) sin perder flexibilidad ni seguridad.
- **sorl-thumbnail:** Ofrece una solución eficiente para generar y gestionar miniaturas de imágenes, optimizando el rendimiento del sitio web.
- **WeasyPrint:** Genera documentos PDF a partir de HTML y CSS, ideal para funcionalidades como reportes descargables o facturación.
- **django-rq:** Gestiona tareas en segundo plano mediante Redis Queue, lo cual permite mejorar la eficiencia del sistema al delegar operaciones costosas como el procesamiento de imágenes o el envío masivo de correos electrónicos.
- **prettyconf:** Simplifica la gestión de configuraciones en el entorno de desarrollo, pruebas y producción, garantizando un código más limpio y seguro al mantener variables de configuración separadas del código fuente.

### Justificación de Enfoques y Patrones

- **Arquitectura basada en componentes:** Modularizar la aplicación en distintas apps dentro del proyecto Django permite un desarrollo más mantenible y escalable.
- **Tareas en segundo plano:** Desvincular operaciones intensivas del flujo principal mejora la experiencia del usuario y reduce tiempos de respuesta.
- **Diseño responsive:** La elección de Bootstrap 5 garantiza una interfaz atractiva y adaptable a múltiples dispositivos.
- **Optimización de imágenes:** El uso de sorl-thumbnail y Pillow reduce la carga en el frontend al mostrar imágenes comprimidas y miniaturas.
