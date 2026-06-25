# testrepo


git reset:

git reset --soft HEAD~1
(2 - is for last 2 commits)
git commit -m "Message"
git push -f BRANCH

--------

git log --graph --decorate


---------

WSL restart:

 Get-Service vmcompute | Restart-Service

read cloud errors"

magento-cloud ssh -e CLOUD_ID "grep -r 'Exception occurred during quote sending' /var/log/"

PHP CS coding standers:

composer require squizlabs/php_codesniffer:^3.4
composer require magento/magento-coding-standard
vendor/bin/phpcs -i
vendor/bin/phpcs --config-set installed_paths ../../magento/magento-coding-standard/
vendor/bin/phpcs --standard=Magento2 app/code/XYZ/Extension
---------

vendor/bin/phpcs --standard=Magento2 --error-severity=10 --report=json
../magento-coding-standard/vendor/bin/phpcs --standard=Magento2 --error-severity=7 --ignore-annotations "$@" ./app/code/ --report-file=IRM-phpcs28-04-26.csv

------------

XDEBUG_MODE=coverage ./vendor/bin/phpunit -c dev/tests/unit/phpunit.xml app/code/Module_name --coverage-html Coverage

-----------

Composer installation:

sudo apt-get remove composer
sudo apt-get update
sudo apt-get install curl
sudo curl -s https://getcomposer.org/installer | php
sudo mv composer.phar /usr/local/bin/composer


----------
general Core review Guide:

- Check module XML and sequence (dependence modules are listed) , check class for dependency of other modules
- Composer JSON also has modules which are dependent
- Read-me file should include configuration details, features, area, mapping if any and etc
- Any form, configuration, etc input field has correct validations
- Translators are properly used
- Check dependency of every class should be interface
- Check if any parent class has that object but in derive class it called again
- Performance impacts from databases
- Unnecessary looping check and remove looping
- less database calls
- Caching the data so that no need to fire the SQL query for same data
- Check if there is unnecessary parser used same
- Check for translation 
- naming conventions

----------

setup xdebug: custom wsl


--------------------------------

/etc/php/8.2/fpm/conf.d/20-xdebug.ini                                                                                    

zend_extension=xdebug.so
xdebug.mode=debug
;xdebug.client_host=127.0.0.1
xdebug.client_host=172.19.80.1
xdebug.client_port=9003
xdebug.idekey=PHPSTORM
xdebug.start_with_request=yes
xdebug.log_level=0


--------------------------------

run :   cat /etc/resolv.conf | grep nameserver
O/P
nameserver 8.8.8.8
nameserver 8.8.4.4

as it is returning the google ip so run 

ip route | grep default
default via 172.19.80.1 dev eth0 proto kernel

-------------

extra suggestion

[xdebug]
zend_extension=xdebug.so ; or the full path to your xdebug.dll on Windows
xdebug.mode = debug
xdebug.start_with_request = yes
xdebug.client_host = 127.0.0.1
xdebug.client_port = 9003 ; You can change this port if needed
xdebug.log = /tmp/xdebug.log ; Optional: for logging Xdebug activity

