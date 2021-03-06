# Changelog

All notable changes to `whatsapp-notification-channel` will be documented in this file

## 1.0.1 - 2022-01-03
-WhatsappAuth: 
1. Drop WhatsAppAuth.php

    [DEPRECATED] available methods:
    - `->action($action)` : (string) selection between [login]|[logout]|[info]
    - `->do()`: Running this action

   usages:
    ```php
        \NotificationChannels\WhatsApp\WhatsAppAuth::create()
        ->action('info') // info/login/logout
        ->do();
    ```
2. Move all to blade ui component
   available: 
    - `account.blade.php`
    
    usages: 
    ```blade
   <x-whatsapp-account></x-whatsapp-account>
   ```
  
## 1.0.0 - 2021-10-24

- initial release
- WhatsAppAuth
    
    available methods:
    - `->action($action)` : (string) selection between [login]|[logout]|[info]
    - `->do()`: Running this action

    usages:
    ```php
        \NotificationChannels\WhatsApp\WhatsAppAuth::create()
        ->action('info') // info/login/logout
        ->do();
    ```
  
- WhatsAppMessage

    available methods:
    - `->to($msisdn)`: (string) Recipient's Destination number
    - `->content('')`: (string) Notification message.
    - `->options([])`: (array) Allows you to add additional or override sendMessage payload.

- Helpers
    
    available methods:
    - `extract_message($message, $needle): object` (object) Will extract response message or something
