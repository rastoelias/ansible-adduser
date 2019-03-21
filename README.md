# Ansible playbook: Add user
An Ansible playbook to create a sudo user with SSH key-based authentication on the Ubuntu server.

## Requirements
* SSH Keys on the local machine.
* Ansible 2.7+ on your local machine.
* Mkpassword on your local machine.
* Remote machine. Tested on:
    * Ubuntu 18.04
* `root` access with SSH key-based authentication on the remote machine.

## Usage
1. Clone this repository.
    ```
    git clone https://github.com/rastoelias/ansible-adduser.git ansible-adduser
    ```
2. Copy `hosts.example` to `hosts`.
    ```
    cp hosts.example hosts
    ```
3. Open the `hosts` file, make desired changes and save the file.
    ```
    [server]
    111.111.111.111 ansible_user=root ansible_port=22
    ```
4. Copy `config.example.yml` to `config.yml`.
    ```
    cp config.example.yml config.yml
    ```
5. Open the `config.yml` file, make desired changes and save changes.
6. Test the connection.
    ```
    ansible all -m ping
    ```
6. Run playbook
    ```
    ansible-playbook provision.yml
    ```
7. Test the connection
    ```
    ssh NEW-USERNAME@IP-ADDRESS
    ```