Mail_ZF2
========

Módulo de ZF2 para el envío de correos

Modo de uso en controladores
----------------------------
$mail_service = $this->getServiceLocator()->get('mail_service');

$mail_service->sendMail(to_mail@mail.com, 'aquí va el encabezado', 'aquí va el mensaje');
