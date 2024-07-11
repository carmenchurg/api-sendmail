## API de Envío de Correos
Este es un script en PHP que actúa como una API para enviar correos electrónicos a través de una solicitud POST. El script está diseñado para recibir datos en formato JSON y enviar un correo al webmaster con la información proporcionada.

## Configuración
Antes de utilizar este script, asegúrate de configurar la dirección de correo electrónico del webmaster en la variable $webmaster_email. Esto garantizará que los correos se envíen correctamente al destinatario deseado.

<!-- $webmaster_email = 'tandem.fiscer@gmail.com'; -->

Además, el script está configurado para permitir solicitudes desde cualquier origen (*) y solo acepta métodos POST. También especifica los encabezados permitidos para la solicitud.

header('Content-Type: application/json');
header("Access-Control-Allow-Origin: *");
header("Access-Control-Allow-Methods: POST");
header("Access-Control-Allow-Headers: Authorization, Content-Type");

## Uso
Para utilizar esta API, realiza una solicitud POST con los datos en formato JSON. Asegúrate de incluir las claves name, email y message en el cuerpo de la solicitud.

## Ejemplo de solicitud:

{
    "name": "John Doe",
    "email": "johndoe@example.com",
    "message": "Este es un mensaje de prueba."
}

El script validará los datos recibidos y enviará un correo al webmaster con la información proporcionada. Si la operación es exitosa, devolverá una respuesta JSON con estado success. En caso de error, devolverá una respuesta JSON con estado error.

## Respuestas
Éxito: Si el correo se envía correctamente, la respuesta será:
{
    "status": "success",
    "message": "Correo enviado correctamente."
}

Error: Si hay algún problema al enviar el correo, la respuesta será:
{
    "status": "error",
    "message": "Error al enviar el correo."
