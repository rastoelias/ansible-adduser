# Ansible playbook: Add user
An Ansible playbook to create a sudo user with SSH key-based authentication on the Ubuntu server.

## Requirements
* SSH Keys on the local machine.
* Ansible 2.7+ on your local machine.
* Mkpassword on your local machine.
* Remote machine with the [Ubuntu server](http://cdimage.ubuntu.com/releases/18.04.2/release/) installed.
* Root/sudo access with SSH key-based authentication on the remote machine.

## Usage
1. Clone this repository.
    ```
    git clone https://github.com/rastoelias/ansible-adduser.git ansible-adduser
    ```
2. Copy `hosts.example` to `hosts`.
    ```
    cp hosts.example hosts
    ```
3. Open the `hosts` file and replace `SERVER-IP-ADDRESS` with the public IP address of your server.
    ```
    [server]
    111.111.111.111
    222.222.222.222
    ```
4. Copy `config.example.yml` to `config.yml`.
    ```
    cp config.example.yml config.yml
    ```
5. Open the `config.yml` file, make desired changes and save changes.
6. Test the connection.
    ```
    ansible all -m ping -u USER -b -e ansible_port=PORT
    ```
6. Run playbook
    ```
    ansible-playbook provision.yml -u USER -b -e ansible_port=PORT
    ```