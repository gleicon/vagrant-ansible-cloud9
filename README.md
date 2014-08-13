# Vagrant file and ansible provisioning to run Cloud9 locally.

That's it. You can also use this ansible setup to create your docker image or provision to a remote VM.
Vagrant layout and organization inspired by https://github.com/DandyDev/graphite-statsd-ansible-vagrant. 

# Requirements

    - Vagrant
    - Ansible installed locally
    - Internet connection

# Usage
## Locally with Vagrant

$ vagrant up 
$ open http://192.168.33.21 on your browser

## Remotely with your cloud of preference
    
    - Add your hostname to ansible hosts file (/etc/ansible/hosts or any other location, you can change that)
        [cloud9]
        host1 ansible_ssh_host=192.168.1.1

    - Make sure you can ssh into it using keys
        ssh root@192.168.1.1

    - Run 
        ansible-playbook -l host cloud9.yml

    - Send me a pull request in case it doesn't works.

# Note on authentication

As this VM is for pesonal use, I've added the basic auth module option from Cloud9. 
You can mess around with doing it through NGINX (good) and/or messing around with other methods than basic auth (better)
_Do not forget_ to change the username and password into cloud9.yml file (webuser and webpassword). It's there, in the open.
