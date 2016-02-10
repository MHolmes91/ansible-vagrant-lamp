Ansible Vagrant LAMP Stack
==========================

This is a basic LAMP stack built for a single site which uses Ubuntu, Apache (of course), MySQL (of course), and PHP-FPM. It will automatically install composer dependencies and import databases if given the proper files. The deployment process uses Ansible. Pre and post setup hooks are provided for easy customization.

This tool was written as a simpler, more focused, alternative to [puphpet](https://puphpet.com). Its main use case is for setting up a vagrant dev environment for a single PHP site.

## Features
* Automation using Ansible for easy customization
* Parameterization of website host name and database attributes
* Automatic import of a database dump file to the database
* Automatic installation of website dependencies via composer
* PHP-FPM
* Other commonly used tools installed automatically
* **Future:** Wordpress, Drupal, and Symfony command line tools support out of the box

## Versions
* Ubuntu - 14.04
* Apache - 2.4
* MySQL - 5.6
* PHP-FPM - 5.6
* Composer - Latest

## How To Use
1. Put your PHP site in the /src folder
2. Put your database dump in the /db folder.
3. In the playbook.yml file, edit the 'vars' section to match your desired settings
4. Add any pre-deployment or post-deployment tasks in the /tasks/pre-tasks.yml or /tasks/post-tasks.yml files
4. `vagrant up` to create your site on the vagrant machine
5. Edit your /etc/hosts file or use `vagrant share` to view your site