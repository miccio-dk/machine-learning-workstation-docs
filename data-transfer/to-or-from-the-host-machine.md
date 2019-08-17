# To or from the host machine
This section illustrates some of the most common ways of transferring data (e.g. datasets, trained models) to and from your local machine.

## Remote copy (`scp`)
Scp (secure copy) allows you to copy files or directories.

To copy a file located in `<LOCAL_FILEPATH>` from your machine to the workstation, type on a local terminal:
```sh
scp <LOCAL_FILEPATH> ml_workstation:<REMOTE_FILEPATH>
```

To copy a file located in `<REMOTE_FILEPATH>` from the workstation to your machine, type on a local terminal:
```sh
scp ml_workstation:<REMOTE_FILEPATH> <LOCAL_FILEPATH>
```

To copy entire folders, add the flag `-r` to either command.

Note: if `<REMOTE_FILEPATH>` begins with `/` it will start pointing from the workstation root directory, otherwise it will start pointing from the user home directory.


### Remote directory (`sshfs`)
This method allows you to mount a remote directory in your local filesystem and share its content between the two hosts.
When the folder is not mounted, the files will only reside on the workstation.

First, you'll need to create an empty directory on your local machine:
```sh
mkdir <DIR_NAME>
```

Then, from the same local terminal:
```sh
sudo sshfs -o allow_other workstation:<REMOTE_DIR_PATH> <DIR_PATH>
```
Please note how `<DIR_PATH>` is the full path to the previously created local directory, whereas `<REMOTE_DIR_PATH>` refers to the remote directory that you want to share.

On OS X, the command is slightly different:
```sh
sudo sshfs -o allow_other,defer_permissions workstation:<REMOTE_DIR_PATH> <DIR_PATH>
```

For more information, refer to this [tutorial](https://www.digitalocean.com/community/tutorials/how-to-use-sshfs-to-mount-remote-file-systems-over-ssh).


### Browser-based file manager (`caddy`+`filebrowser`)
It is also possible to remotely access the remote filesystem from a web interface.

First off, you'll have to download caddy, which is a lightweight HTTP server. From the  workstation type:
```sh
curl https://getcaddy.com | bash -s personal http.filemanager
```

Now, you can run the server with the filemanager service by simply typing:
```sh
caddy filemanager
```

In order to see it locally, you'll have to set up a port forwarding:
```sh
ssh -N -f -L localhost:2015:localhost:2015 ml_workstation
```

You can now access the content of the workstation remotely by pointing your browser to `https://localhost:2015`. 

For more information, please refer to [this tutorial](https://www.thechiefmeat.com/guides/caddy-file-browser.html).
