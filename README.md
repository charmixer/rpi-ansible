# Initial setup

You must add your public ssh key to the hosts:

use `ssh-copy-id <ip>` to copy directly from your ssh-agent (`ssh-add -L`)

Next you'll need avahi-daemon to be running on the server you're trying to reach (if using the hostname to connect through mDNS)

You can use the playbook for this:
```
ansible-playbook -i <ip>, playbooks/init.yml -K
```

*Note: Comma is needed after <ip>*
*Note: "all" must be defined in the hosts file*

# Ansible setup for rpi cluster

Running ansible:

```
# ping nodes
ansible all -m ping
ansible cluster_worker -m ping

# getting temp
ansible cluster -m shell -a '/usr/bin/vcgencmd measure_temp'
```
