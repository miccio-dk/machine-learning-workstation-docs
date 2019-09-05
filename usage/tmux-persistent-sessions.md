# Tmux \(persistent sessions\)

Tmux allows you to host multiple persistent terminal sessions on a single connection.

## Setup and tutorial

* Connect to the workstation, and create a new session by typing:

  ```bash
  tmux
  ```

* Add a new tab \(called "window" within tmux\): ctrl + B, C
* Move to previous or next tab: ctrl + B, P and ctrl + B, N
* Quit \(detach\) tmux session: ctrl + B, D
* Once you re-connect to the workstation, you can attach to the existing session by typing:

  ```bash
  tmux a
  ```

For more information, consult the manual by typing `man tmux` or this [cheatsheet](https://gist.github.com/MohamedAlaa/2961058).

## iTerm2 integration

If you use iTerm2 on OS X, you can navigate all of your tmux tabs using native interface and shortcuts. Connect to the workstation by typing:

```bash
ssh ml_workstation -t 'tmux -CC a -t 0'
```

For more information, refer to [iTerm2 docs](https://www.iterm2.com/documentation-tmux-integration.html).

