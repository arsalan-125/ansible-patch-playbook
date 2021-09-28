# Ansible-Patch-Playbook
This will help you to run different command from ansible playbook

# To Run the playbook, open your terminal

Type the following command
```shell
ansible-playbook -i hosts pb.yml
```
# SSH to multiple host
If you want to add more servers go to hosts file and paste server ip
#### Note:
Following parameters should be changed base on config

`ansible_ssh_private_key_file`: The path of the ssh private key

`ansible_user`: remote machine user name


```shell
[my-ec2-1]
15.207.222.223 ansible_user=root ansible_ssh_private_key_file=/Users/arsalan/.ssh/id_rsa ansible_port=22
[my-ec2-2]
15.207.222.224 ansible_user=root ansible_ssh_private_key_file=/Users/arsalan/.ssh/id_rsa ansible_port=22
```
# Add more task

If you want to add more tasks simply add your task in pb.yml file e.g
```shell
- name: verify container
  shell:  systemctl docker ps
  register: out
- debug: var=out.stdout_lines
```
