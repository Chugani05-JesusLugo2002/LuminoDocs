# Implementación

## Estructura del código: Organización del repositorio y convenciones usadas.

## Tecnologías y Herramientas  

**Lenguajes:** Python, CSS  

**Frameworks:** Django, Bootstrap

**Libraries:** Crispy-forms, Sorl-thumbnail, RQ worker

**Entornos de desarrollo y herramientas:**  
- Visual Studio Code como editor principal  
- Git para el control de versiones  
- SQLite como sistema de gestión de bases de datos

## Instrucciones de configuración

1. **Instalación de extensiones:**  
   Es necesario contar con las extensiones requeridas, que en nuestro caso son Python y Django.  

2. **Configuración del entorno:**  
   El proyecto incluye un archivo `Justfile` que simplifica la configuración del entorno virtual y la instalación de dependencias.   

   - Para crear el entorno virtual, ejecuta:
  
     ```sh
     just create-venv
     ```  

   - Para instalar las dependencias, utiliza el siguiente comando:

     ```sh
     pip install -r requirements.txt
     ```  