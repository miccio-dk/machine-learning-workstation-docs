# Managing users

This page covers common user management tasks. For more information, please refer to the follwing [tutorial](https://www.computerhope.com/unix/adduser.htm).

## List all users

The following command can be used to list all existing users:

```bash
less /etc/passwd
```

The first column of the output represent the users. Please note that this list also contains special users which are used by system services and processes.

## List connected users

To list all currently connected users:

```bash
w
```

This will show the user names along with their IP address, login time, and other information.

## Create user

The following command can be used to create a user named `<USER>`:

```bash
sudo adduser <USER>
```

Upon executing the command, you will be prompted to enter a few informations:

* User password \(this is only going to be temporary\)
* User full name
* Other information \(Room number, phones, etc\)

  Except for the password, all other fields are optional.

Once the user has been added, you can check its presence by trying and logging as them:

```bash
sudo su <USER>
```

This should cause your command prompt to change into `<USER>@mlworkstation...` . You can log out of the new user by pressing ctrl+D or typing `exit`.

It is not advisable that the users keep adopting the temporary password specified above. In order to force a user to set a new password \(for instance, before their first login\), issue the following command:

```bash
sudo passwd --expire <USER>
```

## Grant administrative rights

Administrative \(sudo\) rights in Linux are necessary to install new software, update the system, edit system directories, and handling some of the internal services.

In order for existing users to be granted these priviledges, they must be part of the `sudo` group, which can be done by:

```text
sudo usermod -a -G sudo <USER>
```

The changes will take place starting from their following login. From there on, they can run commands with admin rights by prepending the command with `sudo`.

