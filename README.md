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
PR review tasks:

