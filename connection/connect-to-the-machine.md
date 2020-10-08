# Connect to the machine

The workstation can be accessed remotely through SSH. In order to do so, you have to first connect to an AAU Gateway machine, and then connect to the workstation. The following steps will help you set up an automatic shortcut.

## Setup connection configuration

Navigate in the `.ssh` directory in your local machine:

```bash
cd ~/.ssh
```

Inside the directoty, edit or create a file called `config`, and add the following content:

```text
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

```bash
ssh ml_workstation
```

After running the command, you will be prompted to type in your AAU password.
Afterwards, you will have to confirm your login attempt using the Microsoft Authenticator app, by clicking "Approve" on the app notification. 
You can set it up by following [these instructions](https://www.en.its.aau.dk/instructions/Username+and+password/Azure+MFA/).

Once you authorize using the app, another password prompt will appear, asking you for the password received by email when setting up your account.
If no default password was sent to you, this prompt will allow you to create one.
The next section will help you set up SSH keys to avoid typing this last password all the time.

Refer to [persistent sessions](../usage/tmux-persistent-sessions.md) for multiple persisten terminals on a single session. 

