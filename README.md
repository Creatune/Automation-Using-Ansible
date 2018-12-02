# Automation-Using-Ansible

This is my Google Codein task - to test any fedora release. Here is the playbook :-


---
- hosts: 127.0.0.1
  connection: local
  become: yes
  tasks:

  - name: check-status
    command: systemctl status bluetooth.service

  - name: stop-service
    command: systemctl stop bluetooth.service

  - name: restart-service
    command: systemctl restart bluetooth.service
    
    

Here is the asciinema recording :-
https://asciinema.org/a/NCPFBI39cQb4c9XcDEYNohrlS

Here I tested the bluetooth.service using systemctl (as you can see in the playbook)
    
Hope you like it :)
