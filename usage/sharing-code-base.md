# Sharing code base
This method allows you to deploy code changes performed locally into the workstation, and relies on `git`.

In order to create the repository inside the directory `<REPO_NAME>`, type from the workstation:
```sh
mkdir <REPO_NAME>
cd <REPO_NAME>
git init --bare
```

This command will create and empty repository.

Note: the directory `<REPO_NAME>` must end with `.git`

In order to store and update the code base, you'll have to set up a _hook_.
From inside the repo, type:
```sh
cd hooks
nano post-receive
```

From inside the text editor, type:
```sh
#!/bin/sh
git --work-tree=<CODEBASE_PATH> --git-dir=<REPO_PATH> checkout -f master
```

Note: remember to specify the entire repository path in `<REPO_PATH>`.

Exit the text editor and make the script executable:
```sh
chmod +x post-receive
```

In order to configure git to push code to the workstation, type from the local machine, within the local copy of the repository:
```sh
git remote add ml_workstation ssh://ml_workstation/<REPO_PATH>/
```

You can now push changes to the workstation by typing:
```sh
git push ml_workstation master
```

Note: this will override any manual changes on the remote files affected by the commits.
