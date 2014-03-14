# Ansible Meatspace Chat

This is an [Ansible](http://www.ansible.com/) role for
[Meatspace Chat](https://github.com/meatspaces/meatspace-chat), the fantastic
web chat with animated .GIF goodness and so much more.

## Requirements

This Meatspace Chat role requires a Debian based Linux host and has been tested to
function on Ubuntu with the following specific software versions:

* Ansible: 1.5.3
* Meatspace Chat: GitHub Master
* Node.js: 0.10.26
* Ubuntu: 13.10, 13.04, 12.10, 12.04

## Role Variables

All variables are specified in `defaults/main.yml` and `vars/main.yml`.

### Defaults

| Name           | Default Value | Description                        |
| -------------- | ------------- | -----------------------------------|
| meatspace-chat_domain  | http://127.0.0.1 | URL for Meatspace Chat app |
| meatspace-chat_port | 3000 | TCP port for Meatspace Chat app |
| meatspace-chat_secret | "" | Meatspace Chat session secret |
| meatspace-chat_node_version | 0.10.26 | Preferred Node.js version |
| meatspace-chat_node_packages | list | List of Node.js dependency packages to install |
| meatspace-chat_os_packages | list | List of OS dependency packages to install |
| meatspace-chat_repo | github.com/meatspaces/meatspace-chat.git | Meatspace Chat GitHub repository |
| meatspace-chat_nvm_repo | github.com/creationix/nvm.git | Node Version Manager Github repository |
| meatspace-chat_zeromq_pkg | zeromq-4.0.4.tar.gz | ØMQ source package URL |

The following Node.js dependency packages are defined in
`meatspace-chat_global_node_packages` and installed globally into the Node.js
environment:

* bower
* nodemon

The following OS dependency packages are defined in
`meatspace-chat_os_packages` and installed by default:

* build-essential
* curl
* git-core
* libssl-dev
* redis-server
* uuid-dev
* uuid
* zsh

Most of these packages are required with the exception of `curl` and `zsh`.

### Variables

| Name           | Default Value | Description                        |
| -------------- | ------------- | -----------------------------------|
| meatspace-chat_admin    | vagrant       | OS user account of Meatspace Chat owner
| meatspace-chat_nvm_dir  | /home/{{ meatspace-chat_admin }}/nvm | Directory for Node Version Manager (nvm) installation |
| meatspace-chat_node_dir | {{ meatspace-chat_nvm_dir }}/v{{ meatspace-chat_node_version }}/bin | Directory for Node.js installation
| meatspace-chat_dir | /home/{{ meatspace-chat_admin }}/meatspace-chat | The Meatspace Chat root directory

## Configuration

At a minimum, modify the variables defined in the following files as
necessary:

* `defaults/main.yml`
* `vars/main.yml`

Copy `hosts.example` to `hosts` and edit it to update the values for your
Meatspace Chat host. Be sure to change the following values:

* `0.0.0.0`
* `ubuntu`
* `~/.ssh/meatspace-chat_id`

## Example Playbook

After configuration a basic Meatspace Chat installation and activation is possible
using the included `site.yml` playbook:

```
ansible-playbook -i hosts site.yml
```

## Vagrant

See the README_VAGRANT.md for instructions on using this role with Mac OS X
and Vagrant or just:

```
vagrant up
```

from within the role.

## Dependencies

None

## License

Apache 2

## Author Information

[Brian Shumate](http://brianshumate.com)

