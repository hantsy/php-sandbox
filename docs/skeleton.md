# Creating a Slim project using Slim Skeleton

# Initializing the project skeleton

Run the following command to initialize a Slim project using the official Slim Skeleton project. 

```bash
composer create-project slim/slim-skeleton slim-sample
```
#  Start and run the application

PHP itself includes a built-in web server, in the development stage, 
it is a good option  to run the application quickly.

> In a production environment, a standalone Web Server such as 
> Nginx, Apache Http Server is required to deploy.

Switch to the project root folder.

```bash
cd slim-sample
```

Run the following command to run the application. 

```bash
composer start
```

> NOTE: The `start` is the scripts defined in the *composer.json* file. 

Or you can use `docker-compose` to run the app with `docker`, so you can run these commands:

```bash
cd slim-sample
docker-compose up -d
```

After that, open your browser and go to `http://localhost:8080`.

Or using `curl` to hint `http://localhost:8080`.

```bash
curl http://localhost:8080
```

To run the test suite, run this command in the project root folder.

```bash
composer test
```

That's it! Now go build something cool.
