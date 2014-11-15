# Ansible Role: WordPress + Apache
[![Build Status](https://travis-ci.org/darthwade/ansible-role-wordpress-apache.png)](https://travis-ci.org/darthwade/ansible-role-wordpress-apache)
[![Gittip](http://img.shields.io/gittip/darthwade.svg)](https://www.gittip.com/darthwade/)
[![Flattr this git repo](http://api.flattr.com/button/flattr-badge-large.png)](https://flattr.com/submit/auto?user_id=darthwade&url=https://github.com/darthwade/ansible-role-wordpress-apache&title=Ansible Role: WordPress Apache&language=&tags=github&category=software) 

Ansible role that installs and configures WordPress on Apache.

Features include:
- Installation of any WordPress version to specified directory
- Configuration of wp-config.php
- Fetch random salts for wp-config.php (https://api.wordpress-apache.org/secret-key/1.1/salt/)
- Configuration of Apache virtual host

## Installation

Using `ansible-galaxy`:
```shell 
$ ansible-galaxy install darthwade.wordpress-apache
```

Using `arm` ([Ansible Role Manager](https://github.com/mirskytech/ansible-role-manager/)):
```shell 
$ arm install darthwade.wordpress-apache
```

Using `git`:
```shell 
$ git clone https://github.com/darthwade/ansible-role-wordpress-apache.git
```

## Requirements & Dependencies
- Ansible 1.4 or higher
- PHP (I recommend `geerlingguy.php` role)
- Apache 2.4 or higher (I recommend `geerlingguy.apache` role)
- darthwade.wordpress

## Variables
Here is a list of all the default variables for this role, which are also available in `defaults/main.yml`.

```yaml 
wp_version: 4.0
wp_db_name: 'database_name_here'
wp_db_user: 'username_here'
wp_db_password: 'password_here'
wp_db_host: 'localhost'

wp_apache_hostname: 'example.com'
wp_apache_alias: 'www.example.com cdn.example.com'
wp_apache_admin_email: 'admin@example.com'

wp_db_charset: 'utf8'
wp_db_collate: ''
wp_table_prefix: 'wp_'
wp_debug: false
```

## Example playbook
```yaml
- hosts: all
  vars:
    wp_version: 4.0
    wp_db_name: 'database_name_here'
    wp_db_user: 'username_here'
    wp_db_password: 'password_here'
    wp_db_host: 'localhost'

    wp_apache_hostname: 'localhost'
    wp_apache_alias: 'localhost'
    wp_apache_admin_email: 'admin@example.com'
  roles:
  - darthwade.wordpress-apache
```

## Testing
```shell 
$ git clone https://github.com/darthwade/ansible-role-wordpress-apache.git
$ cd ansible-role-wordpress-apache
$ vagrant up
```

## Contributing
In lieu of a formal styleguide, take care to maintain the existing coding style. Add unit tests and examples for any new or changed functionality.

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request

## License

Licensed under the MIT License. See the LICENSE file for details.

Copyright (c) 2014 [Vadym Petrychenko](http://petrychenko.com/)