<?php

namespace Mailmanage\Service;

use Zend\Mail\Message;
use Zend\Mail\Transport\Smtp as SmtpTransport;
use Zend\Mail\Transport\SmtpOptions;
use Zend\Mime\Message as MimeMessage;
use Zend\Mime\Part as MimePart;

/**
 * 
 * @author flavio
 */

class MailService {
    
    public function sendMail($toMail, $subject, $message) {
        
        $text = new MimePart($message);
        
        $text->type = "text/html";

        $body = new MimeMessage();
        $body->setParts(array($text));

        // prepar correo
        $message = new Message();
        $message->addFrom("tuemail@mail.com", "Mi Nombre")
                ->addTo($toMail)
                ->setSubject($subject);
        $message->setBody($body);
        $message->setEncoding("UTF-8");

        // Setup SMTP transport using LOGIN authentication
        $transport = new SmtpTransport();
        $options = new SmtpOptions(array(
            'name' => 'localhost',
            'host' => 'tuhost',
            'port' => 465,
            'connection_class' => 'login',
            'connection_config' => array(
                'username' => 'tu@usuario.com',
                'password' => '123456',
                'ssl' => 'ssl', // can use tls or ssl
            ),
        ));
        
        $transport->setOptions($options);
        $transport->send($message);
    }

}
