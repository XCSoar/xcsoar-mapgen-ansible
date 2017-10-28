Mapgen Server for XCSoar
========================

This Playbook installs [xcsoar's](http://xcsoar.org/) Map generator. 

Requirements: 
-------------
* Currently Supported Target is Debian 9 
* The machine needs an unpartitioned second disk for data storage > 25G. 
* The role installs the mapgen server under /opt/mapgen 

Installation: 
-------------
1. Setup Debian 9 Machine
2. Add second disk to installed machine
3. Install python minimal on target machine
 - 'apt install python-minimal' 
4. Install ansible on your machine
5. checkout this git repo
6. edit group_vars/mapgen
 - Set mount point
 - Set vg-name
 - Set second disk device
7. edit the hosts file and replace mapgen.xcsoar.org with your fqdn or ip address
8. Apply this playbook to the target machine: 
 - `ansible-playbook -i hosts site.yml -l mapgen -b --become-method su --ask-su-pass $YOURHOST` 
9. You should now be able to visit the website under http://yourmachine/ and start to submitt requests. 

Vagrant Testing: 
================
1. install vagrant
2. install vagrant-sshfs
3. `vagrant up` in this directory
