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

## Meatspace Chat Acclimate!

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

### Meatspace Chat Configurate!

At a minimum, visit the variables defined in the following files:

* `defaults/main.yml`
* `vars/main.yml`

There is more information in the main project
[README](README.md) about these variables.

Then, copy `templates/meatspace-chat.env.j2` to `templates/_meatspace-chat.env.j2` and update as
necessary with the particular environment variables you need for your Meatspace Chat.

Finally, update the `site.yml` playbook if you plan to use it and set
`meatspace-chat_identity` to the short username of your bot.

### Meatspace Chat Activate!

After configuring your Meatspace Chat's environment variables, you should be able to
bootstrap the bot using a virtualenv with commands like following:

```
mkvirtualenv ansible
pip install ansible
vagrant up
```

