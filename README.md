Install RedHat OpenShift Origin on your CentOS 7 box.

## Installation

1. Use a CentOS7 Linux host [I suggest you install=> CentOS-7-x86_64-DVD-1611.iso]

2. Do the following 
   # yum update -y
   # reboot
   # yum install -y git docker vim 
   
3. Clone the repository 
   # 
3. Define mandatory variables for the installation process

```
# Domain name to access the cluster
$ export DOMAIN=yourdomain.local 

# User created after installation [I used root, for my tests]
$ export USERNAME=TheUserUAreLoggedInWith      

# Password for the user
$ export PASSWORD=password
```

