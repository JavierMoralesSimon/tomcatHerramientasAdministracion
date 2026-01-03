# Ficha descriptiva de varias funciones de Manager y Host Manager

## Despliegue de aplicaciones
  * Interfaz: Manager App.
  * Labor: Cargar una aplicación web (WAR o directorio) y ponerla en ejecución.
  * Métodos disponibles:
    * Interfaz gráfica.
    * URL (script).
    * Copia directa en "webapps/".
  * Ventajas:
    * No requiere reiniciar Tomcat.
    * Compatible con automatización.
  * Riesgo: Despliegues incorrectos pueden generar errores de contexto.
  * Ejemplo del proceso:
    * Accedemos a la aplicación Manager e iniciamos sesión.
      ![Acceso a la aplicación Manager e inicio de sesión](https://github.com/JavierMoralesSimon/tomcatHerramientasAdministracion/blob/main/Capturas/1.1.png)
      ![Aplicación Manager](https://github.com/JavierMoralesSimon/tomcatHerramientasAdministracion/blob/main/Capturas/1.2.png)
    * En la sección "Desplegar" tenemos 2 posibilidades. O hacerlo subiendo un archivo war o escribiendo el directorio donde se ubica este en nuestro equipo.
      ![Sección "Desplegar"](https://github.com/JavierMoralesSimon/tomcatHerramientasAdministracion/blob/main/Capturas/1.3.png)
    * Una vez desplegado, en el directorio mostrado podemos ver como se nos ha creado una carpeta.
      ![Creación de una carpeta tras el despliegue](https://github.com/JavierMoralesSimon/tomcatHerramientasAdministracion/blob/main/Capturas/1.5.png)
    * Si accedemos al enlace podremos ver nuestra página.
      ![Acceso exitoso a la página a través de su enlace](https://github.com/JavierMoralesSimon/tomcatHerramientasAdministracion/blob/main/Capturas/1.4.png)

## Recarga de aplicaciones
  * Interfaz: Manager App.
  * Labor: Refrescar una aplicación sin detener el servidor mediante el reinicio del ClassLoader y volver a leer la configuración de la app.
  * Uso típico:
    * Cambios en configuración.
    * Actualización de clases.
  * Ventajas:
    * Sin downtime del servidor.
    * Rápido.
  * Riesgo: Puede causar fugas de memoria si la app no está bien diseñada.

## Parada de aplicaciones
  * Interfaz: Manager App.
  * Labor: Detener una aplicación concreta por medio de que la misma deje de atender peticiones HTTP.
  * Casos de uso:
    * Mantenimiento.
    * Fallos críticos.
    * Seguridad.
  * Ventaja: Control granular por aplicación.
  * Limitación: No libera completamente memoria hasta un undeploy.
  * Ejemplo del proceso:
    * Accedemos a la aplicación Manager e iniciamos sesión si no lo hemos hecho ya y pulsamos en el botón "Parar" de nuestra aplicación.
      ![Aplicación Manager](https://github.com/JavierMoralesSimon/tomcatHerramientasAdministracion/blob/main/Capturas/2.1.png)
      ![Estado tras dar a "Parar" en la aplicación](https://github.com/JavierMoralesSimon/tomcatHerramientasAdministracion/blob/main/Capturas/2.2.png)
    * Si accedemos al enlace de nuestra página podemos observar que no funciona.
      ![Acceso fallido a la página a través de su enlace](https://github.com/JavierMoralesSimon/tomcatHerramientasAdministracion/blob/main/Capturas/2.3.png)
    * Si damos al botón "Arrancar" y recargamos el enlace de nuestra página, esta volverá a funcionar.
      ![Estado tras dar a "Apagar" en la aplicación](https://github.com/JavierMoralesSimon/tomcatHerramientasAdministracion/blob/main/Capturas/2.4.png)
      ![Acceso exitoso a la página a través de su enlace](https://github.com/JavierMoralesSimon/tomcatHerramientasAdministracion/blob/main/Capturas/2.5.png)

## Creación de Hosts Virtuales
  * Interfaz: Host Manager App.
  * Labor: Gestionar múltiples dominios en un mismo Tomcat.
  * Ventajas:
    * Separación lógica de aplicaciones.
    * Escalabilidad.
  * Requisitos adicionales:
    * DNS configurado.
    * Conectores HTTP adecuados.
  * Ejemplo del proceso:
    * Accedemos a la aplicación Host Manager e iniciamos sesión.
      ![Acceso a la aplicación Host Manager e inicio de sesión](https://github.com/JavierMoralesSimon/tomcatHerramientasAdministracion/blob/main/Capturas/3.1.png)
    * Rellenamos el formulario de la sección "Añadir Máquina Virtual" y damos al botón "Añadir".
      ![Relleno del formulario de la sección "Añadir Máquina Virtual"](https://github.com/JavierMoralesSimon/tomcatHerramientasAdministracion/blob/main/Capturas/3.2.png)
    * En la carpeta "Catalina" se nos crea una para nuestra máquina.
      ![En la carpeta "Catalina" se nos crea una para nuestra máquina](https://github.com/JavierMoralesSimon/tomcatHerramientasAdministracion/blob/main/Capturas/3.3.png)
