# **Instrucciones**

<div align="center">
   <img src="../img/manual.gif" alt="Cover" width="300">
</div>

## **Instrucciones de instalación**

Para el uso de nuestra aplicación, es fundamental tener instalados en nuestro sistema Python 3 o versiones superiores, así como también Pip, un gestor de paquetes y librerías para Python. Para cumplir esto, bastaría con ejecutar:

```sh
apt-get install python3 python3-pip
```

También es necesario el paquete `Just`, un paquete de software que permite correr comandos complejos en formas acortadas llamadas "recetas" para así hacer uso de aquellas creadas por el docente que faciliten y agilicen la instalación de nuestra aplicación. Para ello, instalamos con:

```sh
apt-get install rust-just
```

Y una vez tenemos instalados dicho paquete, podemos instalar la aplicación y sus dependencias con los siguientes pasos:

- Creamos el entorno virtual
```sh
just create-venv
```

- Activamos el entorno virtual
```sh
source .venv/bin/activate
```

- Instalamos las dependencias
```sh
just install-reqs
```

## **Instrucciones de uso**

Una vez instaladas las dependencias en un entorno virtual activado, podemos iniciar nuestra aplicación con:

```sh
just 
```

E ingresamos a la url de **[localhost:8000](localhost:8000)**, o si tienes privilegios de administrador puedes ingresar directamente a la interfaz administrativa con [localhost:8000/admin](localhost:8000/admin) e iniciar sesión con las credenciales.