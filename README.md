# jenkins-instance

## Challenge:

- The challenge was to create a Jenkins Instance with ansible. 
    - Setup/ configure a jenkins instance on AWS.
    - Had to make a playbook for jenkins.
    - To configure a jenkins instance on AWS by providing IP address.
    - Run playbook and show jenkins running.

## Process:

- Had two EC2 instances running `Ansible-huma-agent` and `ansible-huma-jenkinshost`
- ssh into the agent ip address and made a new `jenkins.yml` file and `inventory.txt` file. 
- Added the code block in inventory.txt file
```
[jenkins]
10.0.1.63 ansible_ssh_private_key_file=~humashaikh-awskey.pem
```
- Made a playbook in jenkins.yml
     - Added the required steps to setup jenkins. Can find the code in [`jenkins.yml`](https://github.com/humashaikhc/jenkins-instance/blob/main/jenkins.yml) file.
- Used the code above in agent ssh environment to run the ansible playbook. 
```
ansible playbook -v jenkins.yml -i inventory.txt
```
- Once the ansible playbook is run the jenkins is setup in the jenkinshost.
### Demo
Shows the ansible playbook successful and the jenkins dashboard showing when the public ip address of the jenkinshost EC2 instance is used in the url

>jenkinshosturl:8080. 
