# Tmux \(persistent sessions\)
Tmux allows you to host multiple persistent terminal sessions on a single connection.


## Setup and tutorial
- Connect to the workstation, and create a new session by typing:
  ```sh
  tmux
  ```
- Add a new tab (called "window" within tmux): <kbd>ctrl</kbd> + <kbd>B</kbd>, <kbd>C</kbd>
- Move to previous or next tab: <kbd>ctrl</kbd> + <kbd>B</kbd>, <kbd>P</kbd> and <kbd>ctrl</kbd> + <kbd>B</kbd>, <kbd>N</kbd>
- Quit (detach) tmux session: <kbd>ctrl</kbd> + <kbd>B</kbd>, <kbd>D</kbd>
- Once you re-connect to the workstation, you can attach to the existing session by typing:
  ```sh
  tmux a
  ```

For more information, consult the manual by typing `man tmux` or this [cheatsheet](https://gist.github.com/MohamedAlaa/2961058).


## iTerm2 integration
If you use iTerm2 on OS X, you can navigate all of your tmux tabs using native interface and shortcuts.
Connect to the workstation by typing:

```sh
ssh ml_workstation -t 'tmux -CC a -t 0'
```

For more information, refer to [iTerm2 docs](https://www.iterm2.com/documentation-tmux-integration.html).
