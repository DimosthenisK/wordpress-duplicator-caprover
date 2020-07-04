# Caprover - Wordpress Installation from Duplicator

### App Creation

Create a new App on Caprover with persistent data enabled, enable HTTPS but don't enforce it yet. 

### App Config

Create a persistent directory with specific host path, that points to `/var/www/html` in app and any directory you like on your host machine.
Make sure that the directory you chose exists, and then upload the installer.php and the duplicator archive inside it.

### App Deployment

Deploy the Dockerfile displayed above. You may change the PHP Version on the first line by replacing the base image.

### Duplicator Install

Install via the duplicator just as you would in any other case.

### HTTPS/Redirects

You may now enable HTTPS Enforcing. In case you face ``TOO_MANY_REDIRECTS`` error when trying to access your site, add this line on wp-config.php:
``if ($_SERVER['HTTP_X_FORWARDED_PROTO'] == 'https') $_SERVER['HTTPS'] = 'on';``
