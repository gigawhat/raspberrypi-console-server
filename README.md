Summary
-------

Setup a raspberry pi as a serial console server with ansible.
The setup is based on this [article](https://www.packet6.com/configuring-your-raspberry-pi-as-a-console-server/).


Setup
-----
* Clone this repo.

    ```
    git clone https://github.com/gigawhat/raspberrypi-console-server.git
    cd raspberrypi-console-server
    ```

* Update the hosts file with the dns name or ip address of your raspberry pi and user if needed.
* Update the var/main.yaml. All of the serial to network proxy ports are defined in the var/main.yml file. 
  * This playbook assumes you want to use telnet instead of raw, the serial parameters 8N1 (Data 8, Parity none, and Stopbit 1) and 5 minute timeout
  * Ser2net is used as the serial to network proxy. See their man page for more info.

Running
-------
Run ansible
```
ansible-playbook setup.yml
```
Note: you may need to add -k, etc depending on if your ssh key is setup on the pi, sudo is setup, etc.
