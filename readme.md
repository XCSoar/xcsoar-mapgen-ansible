Mapgen Server for XCSoar
========================

This Playbook installs http://xcsoar.org/ Map generator. 

Requirements: 
-------------
* Currently Supported Target is Debian 9 
* The machine needs an unpartitioned second disk for data storage > 25G. 
* The role installes under /opt/mapgen 

Installation: 
-------------
# Setup Debian 9 Machine
# Add second disk to installed machine
# Install python minimal on target machine
 - 'apt install python-minimal' 
# Install ansible on your machine
# checkout this git repo
# edit group_vars/mapgen
 - Set mount point
 - Set vg-name
 - Set second disk device
# edit hosts and replace mapgen.xcsoar.org with your fqdn or ip
# Apply this playbook to the target machine: 
 - `ansible-playbook -i hosts site.yml -l mapgen -b --become-method su --ask-su-pass $YOURHOST` 
# You should now be able to visit the website under http://yourmachine/
