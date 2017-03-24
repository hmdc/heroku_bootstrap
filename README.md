# HMDC Heroku Bootstrap

This repository provides a file structure for bootstrapping a PHP web app in Heroku.

## Getting Started

No changes to the configuration files are necessary if you only need to run a basic PHP website.

1. Clone this repo to your local computer.
2. Remove the "index.php" file from the "www" directory (or repurpose it).
3. Copy your website files into the "www" directory.
4. Commit the entire structure to your GitHub account.
5. Create a Heroku app if you haven't already.
6. Under the "Deploy" tab, connect your GitHub account.
7. Enable automatic deploys from a branch (optional).
8. Deploy your desired branch.
9. Check the "Activity" tab to ensure your site built successfully.
10. Click "Open app" to view your website.

### Adding A Domain

By default Heroku uses your app name to provide a working domain name. HMDC can supply a *.hmdc.harvard.edu or *.iq.harvard.edu domain for your project. Please email support@help.hmdc.harvard.edu to request a domain name; you must provide us with the Heroku Domain of your app under the "Settings" tab.

Once we've created the domain name for you, and configured DNS to point to your Heroku project, you must add the domain name using the "Add domain" option.

## Heroku Configuration Files

### Procfile

This file sets the web server of your choice: nginx (default) or Apache. It also points to the relevent config files for both servers, and PHP-FPM. The final argument is the docroot (where the website files live).

### Server Configs

You can use nginx\_app.conf and apache2_app.conf to add additional directives to either web server, such as default index files, or URL rewritting.

### Composer

With `composer.json`, you can set a specific PHP runtime, and add PHP modules. See [PHP runtimes](https://devcenter.heroku.com/articles/php-support#php-runtimes) and [PHP extensions](https://devcenter.heroku.com/articles/php-support#extensions).

### PHP Directives

You can override php.ini variables in the file `www/.user.ini`. See [PHP settings](https://devcenter.heroku.com/articles/custom-php-settings#php-runtime-settings) and (http://php.net/manual/en/ini.list.php).

### FPM

To make changes to the FastCGI Process Manager, use the `fpm.conf` file. See [PHP-FPM configuration](https://devcenter.heroku.com/articles/custom-php-settings#php-fpm-configuration-include).
