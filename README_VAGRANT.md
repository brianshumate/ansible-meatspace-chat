# Ansible Meatspace Chat with Vagrant

This is an [Ansible](http://www.ansible.com/) role for
[Meatspace Chat](https://github.com/meatspaces/meatspace-chat), the fantastic
web chat with animated .GIF goodness and so much more.

## Requirements

This Meatspace Chat role requires a Debian based Linux host and has been tested to
function on Ubuntu with the following specific software versions:

* Ansible: 1.5.2
* VirtualBox: 4.3.8
* Vagrant: 1.5.0
* Meatspace Chat: GitHub Master
* Node.js: 0.10.26
* Ubuntu: 13.10, 13.04, 12.10, 12.04

## Meatspace Chat Developer Instance

Follow these directions for a Meatspace Chat development deployment on Mac OS X
to an Ubuntu virtual machine on VirtualBox with Vagrant.

Install the following on the Mac that will be used for Hub development,
testing, or trying to take over the world:

* [VirtualBox](https://www.virtualbox.org/)
* [Vagrant](http://www.vagrantup.com/)
* [Ansible](http://www.ansibleworks.com/docs/intro_installation.html)

These tools are optional, but highly recommended:

* [Virtualenv](http://www.virtualenv.org/)
* [Virtualenv Wrapper](https://bitbucket.org/dhellmann/virtualenvwrapper/)

### Meatspace Chat Configuration

At a minimum, visit the variables defined in the following files:

* `defaults/main.yml`
* `vars/main.yml`

There is more information in the main project
[README](README.md) about these variables.

Finally, copymeatspace-chatl.example` playbook to `meatspace-chatyou plan to
use it and configure the following variables as appropriate:

* `hosts`
* `meatspacechat_twitter_key`
* `meatspacechat_twitter_secret`

### Activate Meatspace Chat

Aftemeatspace-chat your Meatspace Chat's environment variables, you can fire
up a Vagrant based instance by issuing the following command from the
`ansible-meatspace-chat` role directory:

```
vagrant up
```

