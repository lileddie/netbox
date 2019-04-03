# Standing up an SSL enabled version of netbox on Ubuntu 18.04

This is a quick deployment of netbox with webhooks enabled - passwords will need to be changed but should be synchronized for all nodes in your HA environment.

### Configuration Prereqs

Install [Ansible}(https://www.digitalocean.com/community/tutorials/how-to-install-and-configure-ansible-on-ubuntu-18-04) and add your SSH keys.  Add your new Ubuntu node to your /etc/ansible/hosts file (modify to your IP):
```
cat >> /etc/ansible/hosts
 [netbox]
 192.168.1.55
```
ctrl+c

## Install necessary roles

Install pre-baked ansible roles used by playbook

~~~
ansible-galaxy install geerlingguy.postgresql lae.netbox
~~~

### Build your stuff already

Run the ansible playbook to build the node

```
ansible-playbook -i 192.168.1.55, netbox/netboxPlaybook.yml
```
