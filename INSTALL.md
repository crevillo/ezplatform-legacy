# Installation instructions

## Terms for future reference:
  * `/<root-dir>/`: The filesystem path where eZ Platform is installed in.
    Examples: `/home/myuser/www/` or `/var/sites/<project-name>/`
  * cli: command line interface. For *Linux/BSD/OS X* specific commands, use of `bash` or similar is assumed.

## Prerequisite

  These instructions assume you have technical knowledge and have already installed PHP, web server &
  *a database server* needed for this software. For further information on requirements [see online doc](https://doc.ez.no/display/TECHDOC/Requirements)

  **Before you start**:
  - Create Database: Installation will ask you for credentials/details for which database to use, example with mysql:
    `CREATE DATABASE <database> CHARACTER SET utf8;` *Note: Right now installer only supports MySQL and MariaDB, Postgres
    support will be (re)added in one of the upcoming releases.*
  - Set php.ini memory_limit=256M before running commands below
  - *Optional:* You can also setup Solr to be used by eZ Platform and take note of the url it is accessible on

## Install

1. **Install/Extract eZ Platform**<a name="install-1-extract"></a>:

    **Install via Composer**

     You can get eZ Platform with Legacy using composer with the following commands:

     *Note: composer will take its time to download all libraries and when done you will be asked to fill in some settings, including database settings.*

       ```bash
       $ curl -sS https://getcomposer.org/installer | php
       $ php -d memory_limit=-1 composer.phar create-project --no-dev crevillo/ezplatform-legacy <directory> [<version>]
       $ cd /<directory>/
       ```

2. *Only for *NIX users* **Setup folder rights**<a name="install-2-folder-rights"></a>:

    Follow one of the options given in the [eZ Platform install instructions](https://github.com/ezsystems/ezplatform/blob/master/INSTALL.md)


3. **Run installation command**<a name="install-4-db-setup"></a>:

    You may now complete the eZ Platform installation with ezplatform:install command, example of use:

    ```bash
    $ php -d memory_limit=-1 app/console ezplatform:install --env prod legacy_clean
    ```

    **Note**: Password for the generated `admin` user is `publish`, this name and password is needed when you would like to login to backend Platform UI. Future versions will prompt you for a unique password during installation.


4. **Configure a VirtualHost**<a name="install-3-vhost"></a>:

    #### Recommended use
    Configure virtual host by either taking examples from [Nginx](doc/nginx) or [Apache2](doc/apache2) documentation,
    or by using provided script to generate from templates, for help see `./bin/vhost.sh -h`, example:
    ```bash
    ./bin/vhost.sh --basedir=/var/www/ezplatform \\
      --template-file=doc/apache2/vhost.template \\
      --host-name=ezplatform \\
      | sudo tee /etc/apache2/sites-enabled/ezplatform.conf > /dev/null
    ```
    Check and adapt the generated vhost config, and then restart Apache or Nginx.

    #### Testing use
    For just local testing without installing a full web-server, while slow you can also run PHP's built-in
    web server using the following command:
    ```bash
    $ php app/console server:run
    ```

    *Note: While far from meant for production use, you can run the command above with `--env=prod` to disable debug.*


You can now point your browser to the installation and browse the site. To access the Platform UI backend, use the `/ez` URL.
To access the old legacy admin, use the `/site_admin` url.
