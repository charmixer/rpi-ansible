# Ansible setup for rpi cluster

Running ansible:

```
# ping nodes
ansible cluster -m ping

# getting temp
ansible cluster -m shell -a '/usr/bin/vcgencmd measure_temp'
```
