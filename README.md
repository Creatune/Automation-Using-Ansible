# Automation-Using-Ansible

This is my Google Codein task - to test any fedora release. Here is the playbook :-<br><br><br>


---<br>
- hosts: 127.0.0.1<br>
  connection: local<br>
  become: yes<br>
  tasks:<br>
  - name: check-status<br>
    command: systemctl status bluetooth.service<br>
  - name: stop-service<br>
    command: systemctl stop bluetooth.service<br>
  - name: restart-service<br>
    command: systemctl restart bluetooth.service<br>
    <br>
    <br>
<br>
Here is the asciinema recording :-
https://asciinema.org/a/NCPFBI39cQb4c9XcDEYNohrlS
<br>
Here I tested the bluetooth.service using systemctl (as you can see in the playbook)
<br>    
Hope you like it :)
