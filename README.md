# wpkit - 0.0.1

* Source: [github.com/akuda/wpkit](http://github.com/akuda/wpkit)
* Author: [Phil Lennon](http://akuda.co.uk)
* Twitter: [@PJL101](http://twitter.com/pjl101)

-

Easy Wordpress Setup with Vagrant, Ansible, MariaDB, Nginx & PHP 5.5

NOTE: This is a development tool only. Do not use this for a production server at this time.

NOTE: This has not been tested with Parallels or VirtualBox at this time.

## First time install

* Install Vagrant 1.7.2
* In terminal, run `vagrant plugin install vagrant-hostsupdater`
* Then run `vagrant plugin install vagrant-cachier`
* Then `sudo easy_install pip`
* Finally, `sudo pip install ansible`

On first run, the virtual machine and packages need to download so the first build will take longer. The files are cached after this.

## Credit

* VVV
* Tutorial
* https://github.com/ansible/ansible-examples
* https://github.com/jalefkowit/vagrant-ansible-wordpress
* https://github.com/Servers-for-Hackers/ansible-nginx
