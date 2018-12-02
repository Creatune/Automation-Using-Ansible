# Automation-Using-Ansible
<head>
div {
    width: 200px;
    word-wrap: break-word;
}
</head>
This is my Google Codein task - to test any fedora release. Here is the playbook :-<br><br><br>

---
- hosts: 192.168.122.83
  become: yes
  tasks:

  - name: stop-service cycle 1
    command: systemctl stop bluetooth.service


  - name: disable-service cycle 1
    command: systemctl disable bluetooth.service
    ignore_errors: yes

  - name: reboot host cycle 1
    shell: 'sleep 2 && shutdown -r now'
    async: 1
    poll: 0
    ignore_errors: yes


  - name: Waiting for server to come back after reboot 1
    become: false
    local_action: wait_for host=192.168.122.83  port=22  search_regex=OpenSSH  state=started  delay=20
  

  - name: Checking the status of the service cycle 2
    command: systemctl status bluetooth.service
    ignore_errors: yes


  - name: To check all the running services cycle 2
    command: ps aux | grep bluetooth
    ignore_errors: yes

  - name: To enable service cycle 2
    command: systemctl enable bluetooth.service


  - name: To start the service cycle 2
    command: systemctl start bluetooth.service


  - name: To check the status of the service cycle 2
    command: systemctl status bluetooth.service
    ignore_errors: yes


  - name: To again check all the running services cycle 2
    command: ps aux | grep bluetooth
    ignore_errors: yes

  - name: To stop the service cycle 2
    command: systemctl stop bluetooth.service
    ignore_errors: yes

  - name: To check status cycle 2
    command: systemctl status bluetooth.service
    ignore_errors: yes


  - name: To check all running services cycle 2
    command: ps aux | grep bluetooth
    ignore_errors: yes



  - name: reboot the host cycle 2
    shell: 'sleep 2 && shutdown -r now'
    async: 1
    poll: 0
    ignore_errors: yes


  - name: Waiting for the host to come back cycle 2
    become: false
    local_action: wait_for host=192.168.122.83  port=22  search_regex=OpenSSH  state=started  delay=20


  - name: To check the status of service cycle 3
    command: systemctl status bluetooth.service
    ignore_errors: yes

  - name: To check all the runnning services cycle 3
    command: ps aux | grep bluetooth
    ignore_errors: yes

  - name: To disable the service cycle 3
    command: systemctl disable bluetooth.service
    ignore_errors: yes

  - name: reboot the host again cycle 3
    shell: 'sleep 2 && shutdown -r now'
    async: 1
    poll: 0
    ignore_errors: yes

  - name: Waiting for the host to come back cycle 3
    become: false
    local_action: wait_for host=192.168.122.83  port=22  search_regex=OpenSSH  state=started  delay=20


  - name: To check status of the service cycle 4
    command: systemctl status bluetooth.service
    ignore_errors: yes


  - name: To check all the running services cycle 4
    command: ps aux | grep bluetooth
    ignore_errors: yes



  
Here is the asciinema recording :-
https://asciinema.org/a/ZtWkMjry5PRZdgOEFVBBkwXmE
<br>
Here I tested the bluetooth.service using systemctl (as you can see in the playbook)
<br>    
Hope you like it :)<br>
This testing can be done with other services too.
