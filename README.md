# Automation-Using-Ansible

This is my Google Codein task - to test any fedora release. Here is the playbook :-


<b>---
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
</b>

Here is the asciinema recording :-
https://asciinema.org/a/C2WgruQ3JSSL0byTuZroTtcik

Here I tested the bluetooth.service using systemctl (as you can see in the playbook)
    
Hope you like it :)
