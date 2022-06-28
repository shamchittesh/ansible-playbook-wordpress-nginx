# WordPress + Nginx Ansible Playbook
Ansible playbook and roles for installing WordPress + Nginx + PHP + Postfix server

### Requirements
- Ansible 2.0.0 or newer
- Ubuntu 20.04 (installed on your web server or virtual machine)

### Instructions:


### 1. Clone the repository

```
$ git clone https://github.com/shamchittesh/ansible-wordpress-nginx-playbook.git
$ cd /wordpress-nginx
```
## a. change env variables
1.Edit wp_db_name/user/password variables 
2.edit your desired wordpress version install
3.change server_hostname to your desired domain name

```
$ vi group_vars/all
```

### 2. Set the web server IP address

Create a hosts file to set your web server's IP or move `hosts.example` to `hosts` if you're using vagrant:

```
mv hosts.example hosts
```

Change `192.168.100.10` to your server's URL or the IP address of your virtual machine:

```
[web-server]
xxx.xxx.xxx.xxx
```

### 3. Run the playbook

```
$ ansible-playbook playbook.yml -i hosts -u YOUR_REMOTE_USER_ID
```

This tells ansible to use the inventory file we've called "hosts". If you're using vagrant you can run the same command as above but exclude the username and sudo prompt:

```
$ ansible-playbook playbook.yml -i hosts
```

### 5. Finish the install

Open your web browser and navigate to your webserver's IP (http://) to finish the WordPress installation.


