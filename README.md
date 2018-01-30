ansible-vps
===========

This is a set of ansible roles to deploy my own services I use on VPS, like
blog or mail server. To use it, you need to have an ansible (tested on version
2.4) tooling setted up.

This repo is organized next way:


```
.
|-- group_vars
|-- host_vars
|-- inventory
|-- roles
`-- vars
```

*group_vars* contains variables which are common for specific group types, like
~all~ or ~docker~

*host_vars* contains variables for hosts, such as user name and hostname and IP

*inventory* lists all the inventory files. As this repo is used for different
projects but the same roles are used, separate inventory files are needed

*roles* lists all available ansible roles

*vars* contains variables for different OS types or for separate playbooks


Main playbooks there are:

* letsencrypt.yml - Issue a LetsEncrypt certificate for given host, using
  either official certbot or dehydrated script. Tested on Ubuntu 16.04 LTS.


To apply any of there all you need is just


```
$ ansible-playbook -i hosts <playbook_name.yml> -b [--vault-password-file ~/.vault_pass.txt]
```
