Install RedHat OpenShift Origin on your CentOS 7 box.

## Installation

1. Use a CentOS7 Linux host [I suggest you install minimum => CentOS-7-x86_64-DVD-1611.iso]

2. Do the following
```
   $ yum update -y      
   $ reboot       
   $ yum install -y git docker vim docker ansible
```
   
3. Create a ssh key and copy it using the folllowing commands
```
   $ ssh-keygen    
   $ ssh-copy-id root@CentOS-IP
```

4. Clone the repository 
```
   $ git clone  https://github.com/jouzan/openshiftandscaleio.git
```

# 5. Define mandatory variables for the installation process
```
# Domain name to access the cluster
$ export DOMAIN=yourdomain.local 

# User created after installation [I used root, for my tests]
$ export USERNAME=TheUserUAreLoggedInWith      

# Password for the user
$ export PASSWORD=password
```

# 6. Install ScaleIO SDC and register with the ScaleIO Storage systen and check that you can provision a volume
```
   $ cd openshiftandscaleio
   $ MDM_IP=MDM1IP,MDM2IP rpm -ivh EMC-ScaleIO-sdc-2.5-0.254.el7.x86_64.rpm
```

# 7. Run the installation script, will take 20+ minutes to finish
```
   $ cd openshiftandscaleio 
   $ install-openshift.sh
```

