# To or from the Internet
This section illustrates some of the most common ways of retrieving data (e.g. datasets) from websites or repositories.

## Wget
Wget is a simple command for downloading content from direct URLs.
In order to download a file from `<URL>` and call it `<FILENAME>`, just type:
```sh
wget -O <FILENAME> <URL>
```

## Rclone
Rclone is a file manager and synchronization tool for a variety of cloud storage and file sharing platforms (e.g. Dropbox, Google Drive, Microsoft OneDrive, Amazon S3).
You can start by adding a platform with typing:
```sh
rclone config
```

The interactive instruction will guide you through the setup process.
Refer to their [documentation](https://rclone.org/) for specific guidance with a given platform.


## Remote browser (X forwarding)
In some cases the only way of downloading content is from a browser. 
In these instances it may be possible to use [X forwarding](/connection/x-forwarding-running-software-with-gui.md) to open a browser running remotely, on your local screen.
