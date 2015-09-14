Vagrantfile
===========

The included Ansible provisioner helps deploy the Froide system to an Ubuntu
Trusty image.

This playbook installs and configures the following dependencies:

* nginx
* uwsgi
* supervisor
* rabbitmq
* postgres

Install
-------

Make sure the Vagrantfile points to the following:

`ansible.playbook = "provisioning/froide.yml"`

Run the following command:

`FROIDE_DIR=/path/to/froide/github/clone vagrant halt && vagrant destroy --force && vagrant up`

Once the machine is running:

`FROIDE_DIR=/path/to/froide/github/clone vagrant provision`
