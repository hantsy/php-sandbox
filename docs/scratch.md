# Creating a Slim project from Scratch

## Initializing a PHP project

Create a new folder to hold the resources of the new created project.

```bash
mkdir slim-demo
```

Enter the project folder.

```bash
cd slim-demo
composer init
# following the steps to create initialze a PHP project which 
# deps is managed by Composer

# Install the following deps
composer require slim/slim slim/psr7
composer require-dev phpunit/phpunit
```

## Hello World

Create a *public* folder, and add a *index.php* file.

```php
<?php

use Psr\Http\Message\ResponseInterface as Response;
use Psr\Http\Message\ServerRequestInterface as Request;
use Slim\Factory\AppFactory;

require __DIR__ . '/../vendor/autoload.php';

$app = AppFactory::create();

$app->get('/', function (Request $request, Response $response, $args) {
    $response->getBody()->write("Hello world!");
    return $response;
});

$app->run();
```

Open *composer.json*, add the following scripts to start the project.

```json
{
  "scripts": {
    "start": [
      "php -S localhost:8080 -t public public/index.php"
    ]
  },  
  //...
}
```

Now start and run the project.

```bash
> run-script run-script start
[Sat Dec 26 11:42:52 2020] PHP 8.0.0 Development Server (http://localhost:8080) started
```

Open a browser and navigate to http://localhost:8080.

Or open a terminal, try to access the endpoints by `curl`.

```bash
> curl http://localhost:8080
Hello world!
```