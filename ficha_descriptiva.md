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
      ![](https://github.com/JavierMoralesSimon/tomcatHerramientasAdministracion/blob/main/Capturas/1.1.png)
      ![](https://github.com/JavierMoralesSimon/tomcatHerramientasAdministracion/blob/main/Capturas/1.2.png)
    * En la sección "Desplegar" tenemos 2 posibilidades. O hacerlo subiendo un archivo war o escribiendo el directorio donde se ubica este en nuestro equipo.
      ![](https://github.com/JavierMoralesSimon/tomcatHerramientasAdministracion/blob/main/Capturas/1.3.png)
    * Una vez desplegado, en el directorio mostrado podemos ver como se nos ha creado una carpeta.
      ![](https://github.com/JavierMoralesSimon/tomcatHerramientasAdministracion/blob/main/Capturas/1.5.png)
    * Si accedemos al enlace podremos ver nuestra página.
      ![](https://github.com/JavierMoralesSimon/tomcatHerramientasAdministracion/blob/main/Capturas/1.4.png)
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

## Creación de Hosts Virtuales
  * Interfaz: Host Manager App.
  * Labor: Gestionar múltiples dominios en un mismo Tomcat.
  * Ventajas:
    * Separación lógica de aplicaciones.
    * Escalabilidad.
  * Requisitos adicionales:
    * DNS configurado.
    * Conectores HTTP adecuados.
