# wpkit - 0.0.3

* Source: [github.com/akuda/wpkit](http://github.com/akuda/wpkit)
* Author: [Phil Lennon](http://akuda.co.uk)
* Twitter: [@PJL101](http://twitter.com/pjl101)

-

Easy Wordpress Setup with Vagrant, Ansible, mySQL, Nginx & PHP 5.5

NOTE: phpmyadmin is needed to import databases, auto import is not available yet.

NOTE: This is a development tool only. Do not use this for a production server. Production server support will be looked into in the future.

NOTE: This has not been tested with Windows, Parallels or VirtualBox at this time.

## First time install

* Install Vagrant 1.7.2,
* In terminal, run `vagrant plugin install vagrant-hostsupdater`,
* Then run `vagrant plugin install vagrant-cachier`,
* Then `vagrant plugin install vagrant-triggers`,
* Then `sudo easy_install pip`,
* Finally, `sudo pip install ansible`.

On first run, the virtual machine and packages need to download so the first build will take longer. The files are cached after this.

## Default web addresses

* http://wpkit.dev
* http://wpkit.dev/phpmyadmin

## Credit

* https://github.com/Varying-Vagrant-Vagrants/VVV
* https://github.com/ansible/ansible-examples
* https://github.com/jalefkowit/vagrant-ansible-wordpress
* https://github.com/Servers-for-Hackers/ansible-nginx
* https://github.com/debops/ansible-phpmyadmin
