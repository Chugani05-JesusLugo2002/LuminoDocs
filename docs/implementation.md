# **Implementación**

<div align="center">
   <img src="../img/computer.gif" alt="Cover">
</div>

## **Estructura del código**

Nuestro código está organizado de la forma convencional proporcionado por Django y su estructura de aplicaciones. Dichas aplicaciones son:

1. **Shared**: La aplicación que contiene elementos de uso común entre el resto de aplicaciones.
2. **Accounts**: La aplicación que gestiona la autenticación y creación de perfiles.
3. **Subjects**: Gestiona el sistema de asignaturas, sus modelos, vistas y funciones relacionadas.
4. **Users**: Gestiona los perfiles, las acciones que pueden realizar y los atributos que estos contienen.

En cada aplicación hay presentes ficheros **modelos, vistas, plantillas, decoradores y utilidades necesarias** que permiten el funcionamiento de nuestra aplicación web.

## **Tecnologías y Herramientas**

**Lenguajes:** Como lenguajes tenemos Python, CSS, HTML y algo de Javascript.

**Frameworks:** Los frameworks utilizados fueron Django para el funcionamiento general, Bootstrap para el estilo y Pytest para el *testeo* del proyecto y sus elementos.

**Libraries:** Algunas de las librerías principales son *Crispy Forms*, que permite la creación y utización de formularios estilizados con Bootstrap de forma sencilla; *Sorl Thumbnail*, que permite la utilización y manejo de imagenes de forma controlada y *RQ worker*, que permite la ejecución de tareas en segundo plano para realizar acciones como el envío de correos electrónicos.

**Entornos de desarrollo y herramientas:**  

- **Visual Studio Code** como editor principal con extensiones como Django, Prettier, Error Lens y snippets personalizados que nos facilitaron el trabajo otorgándonos eficiencia.  
- **Git** para el control de versiones.  
- **SQLite** como sistema de gestión de bases de datos, utilizado por defecto por el framework de Django.