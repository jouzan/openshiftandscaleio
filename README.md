Install RedHat OpenShift Origin on your CentOS 7 box.

## Installation

1. Use a CentOS7 Linux host [I suggest you install=> CentOS-7-x86_64-DVD-1611.iso]

2. Do the following   yum update -y      reboot       yum install -y git docker vim docker
   
3. Create a ssh key and copy it using the folllowing commands    ssh-keygen     ssh-copy-id root@CentOS-IP

4. Install Ansible        yum install -y ansible 

5. Clone the repository        git clone  https://github.com/jouzan/openshiftandscaleio.git
   
# 6. Define mandatory variables for the installation process
```
# Domain name to access the cluster
$ export DOMAIN=yourdomain.local 

# User created after installation [I used root, for my tests]
$ export USERNAME=TheUserUAreLoggedInWith      

# Password for the user
$ export PASSWORD=password
```

