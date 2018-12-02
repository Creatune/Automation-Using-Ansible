# Automation-Using-Ansible

This is my Google Codein task - to test any fedora release. Here is the playbook :-


---<br>
- hosts: 127.0.0.1<br>
  connection: local<br>
  become: yes<br>
  tasks:<br>
<br>
  - name: check-status<br>
    command: systemctl status bluetooth.service<br>
<br>
  - name: stop-service<br>
    command: systemctl stop bluetooth.service<br>
<br>
  - name: restart-service<br>
    command: systemctl restart bluetooth.service<br>
    
    

Here is the asciinema recording :-
https://asciinema.org/a/NCPFBI39cQb4c9XcDEYNohrlS

Here I tested the bluetooth.service using systemctl (as you can see in the playbook)
    
Hope you like it :)
