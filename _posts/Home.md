##Setup Project


```
#!ssh 
*  clone project: git clone git@bitbucket.org:idcrm/antargaz_web.git
*  cd to project path run: composer install
*  copy .env.example and rename to .env then update to fit with your environment 
*  run: php artisan migrate
*  seup suppervisor to manage your queue jobs:  http://laravel.com/docs/5.1/queues#supervisor-configuration 
*  to restart queue job when deployment: php artisan queue:restart

```

1. [Get OfferID Api](https://bitbucket.org/idcrm/antargaz_web/wiki/GetOfferID)
2. [Sign Api](https://bitbucket.org/idcrm/antargaz_web/wiki/Sign%20Api)
3. [Login](https://bitbucket.org/idcrm/antargaz_web/wiki/Login%20to%20get%20access%20token)
4. Development Env: http://dev.idcrm.com/antar-dev/test_sign
5. Testing Env: dev.idcrm.com/antargaz-web-service/test_sign
6. API request to send email when client not sign: (method get) dev.idcrm.com/antargaz-web-service/send_verify_email/{uuid}