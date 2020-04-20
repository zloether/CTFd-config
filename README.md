# CTFd-config
Configures CTFd to run with Nginx front-end using Ansible


## Configuration Decisions
 - Uses MySQL backend


## Pre-requisites
 - MySQL server must be available. See this project for help: [https://github.com/zloether/MySQL-config](https://github.com/zloether/MySQL-config)
 - Ansible must be installed on your control host (probably your computer).
    Ubuntu or Mint:
    ```
    sudo apt install -y ansible
    ```
 - SSH server must be installed and running on the remote host (the computer you want to configure).
    Ubuntu or Mint:
    ```
    sudo apt install -y openssh-server
    ```
 - Python must be installed on the remote host (installed by default on most *nix machines)
    

## How to run
 - Update the `inventory` file with your remote host address
 - Run this command:
    ```
    ansible-playbook -i inventory --ask-pass --ask-become-pass ansible-playbook_<OS>.yml
    ```

## Manage CTFd daemon
Check status
```
systemctl status ctfd
```

Restart daemon
```
sudo systemctl restart ctfd
```

Stop daemon
```
sudo systemctl stop ctfd
```

Start daemon
```
sudo systemctl start ctfd
```