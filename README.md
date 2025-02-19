Instrucciones para instalar Odoo v18

Preparar el entorno: Antes de instalar Odoo v18, asegúrate de que tu sistema cumple con los requisitos necesarios. Esto incluye tener un servidor con Ubuntu 20.04 o superior, y acceso a una terminal.

Actualizar el sistema: Es recomendable actualizar los paquetes del sistema antes de comenzar la instalación.

Instalar dependencias: Odoo v18 requiere varias dependencias para funcionar correctamente. Asegúrate de instalar todas las bibliotecas y herramientas necesarias.

Crear un usuario para Odoo: Por razones de seguridad, es recomendable crear un usuario específico para ejecutar Odoo. Este usuario debe tener permisos limitados para evitar riesgos de seguridad.

Instalar PostgreSQL: Odoo utiliza PostgreSQL como base de datos predeterminada. Asegúrate de instalar y configurar PostgreSQL correctamente antes de proceder con la instalación de Odoo.

Descargar Odoo v18: Puedes descargar Odoo v18 directamente desde el repositorio oficial de GitHub o utilizando un instalador. Asegúrate de descargar la versión correcta.

Configurar Odoo: Una vez descargado, es necesario configurar Odoo para que funcione correctamente en tu entorno. Esto incluye ajustar los archivos de configuración y establecer los permisos adecuados.

Iniciar el servicio de Odoo: Después de completar la configuración, puedes iniciar el servicio de Odoo. Verifica que el servicio se esté ejecutando correctamente y que no haya errores en los registros.

Acceder a Odoo: Una vez que el servicio esté en funcionamiento, puedes acceder a Odoo a través de tu navegador web. Ingresa la dirección IP o el dominio de tu servidor seguido del puerto correspondiente.

Completar la instalación: Sigue las instrucciones en pantalla para completar la instalación de Odoo. Esto incluye configurar la base de datos y crear un usuario administrador.

Verificar la instalación: Finalmente, verifica que todo esté funcionando correctamente. Asegúrate de que todos los módulos y funcionalidades estén disponibles y que no haya errores en el sistema.

Script de instalación para Odoo Open Source
Este script también te permitirá definir un xmlrpc_port en el archivo .conf que se genera en /etc/.
Este script puede usarse de manera segura en un servidor con múltiples bases de código de Odoo, ya que el puerto predeterminado de Odoo se cambia ANTES de que Odoo se inicie.

Instalación de Nginx
Si configuras el parámetro INSTALL_NGINX como True, también deberás configurar los workers. Sin workers, es probable que tengas problemas de pérdida de conexión. Consulta la guía de despliegue de Odoo para saber cómo configurar los workers.

Procedimiento de instalación
1. Descarga el script:
Copy
wget https://raw.githubusercontent.com/billingmorris/odoo/18.0/install_odoo_ubuntu.sh
2. Modifica los parámetros según tus necesidades.
Hay varias cosas que puedes configurar, esta es la lista más utilizada:

OE_USER será el nombre de usuario para el usuario del sistema.

GENERATE_RANDOM_PASSWORD si este parámetro se establece como True, el script generará una contraseña aleatoria; si se establece como False, se usará la contraseña configurada en OE_SUPERADMIN. Por defecto, el valor es True y el script generará una contraseña aleatoria y segura.

OE_PORT es el puerto en el que Odoo debería ejecutarse, por ejemplo, 8069.

OE_VERSION es la versión de Odoo que se instalará, por ejemplo, 14.0 para Odoo V14.

IS_ENTERPRISE instalará la versión Enterprise sobre 18.0 si lo configuras como True; configúralo como False si deseas la versión comunitaria de Odoo 16.

OE_SUPERADMIN es la contraseña maestra para esta instalación de Odoo.

INSTALL_NGINX está configurado como True por defecto. Configúralo como False si no deseas instalar Nginx.

WEBSITE_NAME Establece el nombre del sitio web aquí para la configuración de nginx.

ENABLE_SSL Configura esto como True para instalar certbot y configurar nginx con https usando un certificado gratuito de Let's Encrypt.

ADMIN_EMAIL Se necesita un correo electrónico para registrarse en Let's Encrypt. Reemplaza el marcador de posición predeterminado con un correo electrónico de tu organización.

INSTALL_NGINX y ENABLE_SSL deben estar configurados como True, y el marcador de posición en ADMIN_EMAIL debe ser reemplazado con una dirección de correo electrónico válida para la instalación de certbot.

Al habilitar SSL a través de Let's Encrypt, aceptas las siguientes políticas.

3. Haz que el script sea ejecutable:
Copy
sudo chmod +x install_odoo_ubuntu.sh
4. Ejecuta el script:
Copy
sudo ./install_odoo_ubuntu.sh
La instalación debería tomar aproximadamente 10 minutos en completarse, y luego podrás acceder a Odoo desde cualquier parte del mundo ingresando su dirección IP.
