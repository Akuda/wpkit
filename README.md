# wpkit - 0.0.7

* Author: [Phil Lennon](http://iampjl.co.uk)
* Source: [github.com/PJL101/wpkit](http://github.com/PJL101/wpkit)
* Twitter: [@PJL101](http://twitter.com/pjl101)
* Email: [enquiry@iampjl.co.uk](mailto:enquiry@iampjl.co.uk)

-

# NOTE: This project is super early alpha. I'd suggest waiting for the first released version.

Easy Wordpress Setup with Vagrant, Ansible, Ubuntu 14.04, mySQL, Nginx & PHP 5.5

NOTE: phpmyadmin is needed to import databases, auto import is not available yet.

NOTE: This is a development tool only. Do not use this for a production server. Production server support will be looked into in the future.

NOTE: This has not been tested with Windows, Parallels or VMware Fusion at this time.

## First time install

* Install Vagrant 1.7.4,
* In terminal, run: `vagrant plugin install vagrant-hostsupdater`,
* Then run: `vagrant plugin install vagrant-cachier`,
* Then: `vagrant plugin install vagrant-triggers`,
* Then: `vagrant plugin install vagrant-vbguest`,
* Then: `sudo easy_install pip`,
* Finally: `sudo pip install ansible`.

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
