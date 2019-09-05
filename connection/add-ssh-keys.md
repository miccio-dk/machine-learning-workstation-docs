# Add SSH Keys

This guide will help you set up SSH keys, which will be used to authenticate you into the machine instead password. Note that you will still be required to type your AAU email password.

## Look for SSH keys

Type the following on a terminal:

```bash
ls -al ~/.ssh
```

The command will list the content of your `.ssh` directory; if you see a file called `id_rsa.pub`, it means you already created an SSH key and you can skip the next step.

## Create SSH key

On your local machine, type the following on a terminal:

```bash
ssh-keygen -t rsa -b 4096 -C "<AAU FULL EMAIL>"
```

Make sure to replace `<AAU FULL EMAIL>` with your AAU email address. In the following prompts, you can just keep the default settings, although it is recommended to set up a passphrase.

## Upload the key

Once you have an SSH key pair, you must upload the public one to the workstation. From a terminal, type:

```bash
ssh-copy-id ml_workstation
```

Follow the directions of the prompts, and verify that the procedure was successful by typing:

```bash
ssh ml_workstation
```

If everything worked, you will only have to type your AAU email password.

For more information on how to upload an SSH key, as well as alternative methods, please refer to [this guide](https://www.digitalocean.com/docs/droplets/how-to/add-ssh-keys/to-existing-droplet/).

