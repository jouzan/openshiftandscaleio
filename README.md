Install RedHat OpenShift 3.9 Origin on your CentOS 7 box.

## Installation

1. Use a CentOS7 Linux host [I suggest you install minimum => CentOS-7-x86_64-DVD-1611.iso]
   make sure to have the host name in dns, also create  A record named console pointing to the server IP 
   
2. Do the following
```
   $ yum update -y      
   $ reboot   
```
   
3. Download and install the kernel  3.10.0-693.21.1.el7 ---->so the SDC works
```
    $ yum install -y kernel-plus-3.10.0-693.21.1.el7.centos.plus.x86_64.rpm 
    $ reboot to the new kernel
    $ yum install -y git docker ansible vim wget

4. Create a ssh key and copy it using the folllowing commands
```
   $ ssh-keygen    
   $ ssh-copy-id root@CentOS-IP
```

5. Clone the repository 
```
   $ git clone  https://github.com/jouzan/openshiftandscaleio.git
```

## 6. Define mandatory variables for the installation process
```
# Domain name to access the cluster
$ export DOMAIN=yourdomain.local 

# User created after installation [I used root, for my tests]
$ export USERNAME=TheUserUAreLoggedInWith      

# Password for the user
$ export PASSWORD=password
```

## 7. Install ScaleIO SDC and register with the ScaleIO Storage systen and check that you can provision a volume
```
   $ cd openshiftandscaleio
   $ MDM_IP=MDM1IP,MDM2IP rpm -ivh EMC-ScaleIO-sdc-2.5-0.254.el7.x86_64.rpm
```

## 8. Run the installation script, will take 20+ minutes to finish
```
   $ cd openshiftandscaleio 
   $ install-openshift.sh
```

## 9. Login via CLI, you will be using the username password you provided in step 5
```
   $ oc login
```
## 10. Create the SECRETE STORAGECLASS AND SECRET 
```
   $ oc login
   $ oc create -f siosc.yaml
   $ oc create –f secret.yaml
   $ oc create -f siopvc.yaml
   $ oc get pvc
   $ oc describe pvc pvc-sio
```



   
   
