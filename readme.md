## WebService de Envío de Correos
### Descripción
Este script en PHP actúa como un WebService que permite enviar correos electrónicos al webmaster a través de una solicitud POST. Los datos se envían en formato JSON y se valida antes de enviar el correo.

### Instalación
No se requiere instalación especial. Solo asegúrate de configurar la dirección de correo electrónico del webmaster en la variable $webmaster_email.

### Uso
#### Endpoint
El endpoint para enviar correos es /send-email.php.

### Parámetros
Los parámetros requeridos en el cuerpo de la solicitud POST son:

name: Nombre del remitente.
email: Dirección de correo electrónico del remitente.
message: Mensaje a enviar.

### Ejemplo de Solicitud
Puedes realizar una solicitud POST utilizando herramientas como cURL, Postman o incluso desde un formulario HTML. Aquí tienes un ejemplo utilizando cURL:

curl -X POST http://tu-servidor/send-email.php \
-H "Content-Type: application/json" \
-d '{"name": "John Doe", "email": "johndoe@example.com", "message": "Este es un mensaje de prueba."}'