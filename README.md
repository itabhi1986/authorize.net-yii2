Authorize.net Payment Methods
=============================
Authorize.net Payment Extension on Yii2

Installation
------------

The preferred way to install this extension is through [composer](http://getcomposer.org/download/).

Either run

```
php composer.phar require --prefer-dist abhishek/authorize.net-yii2 "*"
```

or add

```
"abhishek/authorize.net-yii2": "*"
```

to the require section of your `composer.json` file.


Usage
-----

Once the extension is installed, simply use it in your code by calling default classes :

You just have to include any of the class. Rest all functions will work same as authorizenet PHP SDK.

use AuthorizeNetAIM; use AuthorizeNetARB; use AuthorizeNetCIM; use AuthorizeNetCP; use AuthorizeNetDPM; use AuthorizeNetSIM; use AuthorizeNetSOAP; use AuthorizeNetTD;

Usage Examples

use AuthorizeNetAIM;
define("AUTHORIZENET_API_LOGIN_ID", "YOURLOGIN");
define("AUTHORIZENET_TRANSACTION_KEY", "YOURKEY");
define("AUTHORIZENET_SANDBOX", true);

$sale = new AuthorizeNetAIM;
$sale->amount = "1.99";
$sale->card_num = '4111111111111111';
$sale->exp_date = '0418';
$response = $sale->authorizeAndCapture();
if ($response->approved) {
    echo "Success! Transaction ID:" . $response->transaction_id;
} else {
    echo "ERROR:" . $response->error_message;
}   

For more examples visit https://github.com/AuthorizeNet/sdk-php
