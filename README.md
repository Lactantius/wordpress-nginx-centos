## WordPress+Nginx+PHP-FPM+MariaDB Deployment

- Requires Ansible 1.2 or newer
- Expects CentOS/RHEL 7.x host/s

RHEL7 version reflects changes in Red Hat Enterprise Linux and CentOS 7:
1. Network device naming scheme has changed
2. iptables is replaced with firewalld
3. MySQL is replaced with MariaDB

These playbooks deploy a simple all-in-one configuration of the
popular WordPress blogging platform and CMS, frontend by the Nginx web
server and the PHP-FPM process manager. To use, run `vagrant up`.

The ansible playbooks will configure MariaDB, WordPress, Nginx, and
PHP-FPM. When the run is complete, you can run `vagrant ssh` to login,
or `vagrant ssh-config` to find the IP address.

### Ideas for Improvement

Here are some ideas for ways that these playbooks could be extended:

- Parameterize the WordPress deployment to handle multi-site configurations.
- Separate the components (PHP-FPM, MySQL, Nginx) onto separate hosts and 
handle the configuration appropriately.
- Handle WordPress upgrades automatically.

We would love to see contributions and improvements, so please fork this
repository on GitHub and send us your changes via pull requests.
