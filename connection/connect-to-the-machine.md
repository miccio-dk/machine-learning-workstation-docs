# Connect to the machine
The workstation can be accessed remotely through SSH.
In order to do so, you have to first connect to an AAU Gateway machine, and then connect to the workstation. 
The following steps will help you set up shortcuts what will 

## Setup login configuration
Navigate in the `.ssh` directory in your local machine:
```sh
cd ~/.ssh
```

Inside the directoty, edit or create a file called `config`, and add the following content:
```ssh-config
Host aau_gateway
   HostName sshgw.aau.dk
   User <AAU FULL EMAIL>
   ServerAliveInterval 30
   ServerAliveCountMax 2

Host ml_workstation
   HostName 172.30.215.224
   User <AAU EMAIL USERNAME>
   IdentityFile ~/.ssh/id_rsa
   ProxyCommand ssh aau_gateway nc %h %p
   ServerAliveInterval 30
   ServerAliveCountMax 2
```
Be sure to replace the fields `<AAU FULL EMAIL>` and `<AAU EMAIL USERNAME>` with their respective informations.

## Connect
To verify the above steps and connect to the workstation, open a new terminal and type:
```sh
ssh ml_workstation
```

Please note: first, you will be prompted to type in your AAU email password; the second password prompt is the one you set up on the workstation. 
