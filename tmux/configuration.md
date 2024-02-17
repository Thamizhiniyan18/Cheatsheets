# Configuration

## Tmux Configuration

You can configure Tmux via the `~/.tmux.conf` file. If it doesn’t exist, create it:

`$ touch ~/.tmux.conf`

To reload Tmux with the new settings:

`$ tmux source-file ~/.tmux.conf`

## Custom Keystrokes

Add these commands to `~/.tmux.conf` to modify Tmux function keys. Each command spans two lines. The unbind command deactivates the default key combination.

| **COMMAND**                                                           | **DESCRIPTION**                                                                                                            |
| --------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------- |
| <p><code>unbind '"'</code><br><code>bind - split-window -v</code></p> | Change key combination to split window into two horizontal panes: Replace default **Ctrl+b** " with **Ctrl+b** – (hyphen)  |
| <p><code>unbind %</code><br><code>bind | split-window -h</code></p>   | Change key combination to split window into two vertical panes: Replace default **Ctrl+b** % with **Ctrl+b** `\|` (pipe)   |
| <p><code>unbind C-b</code><br><code>set -g prefix C-a</code></p>      | Replace trigger key combination **Ctrl+b** with **Ctrl+a**                                                                 |

## Making Tmux Copy Mode to default to vi keys

| **COMMAND**            | **DESCRIPTION**           |
| ---------------------- | ------------------------- |
| `setw -g mode-keys vi` | Use vi keys in the buffer |

## Customization

The following commands are for customizing the status bar at the bottom of a Tmux window:

| **COMMAND**                                                                                               | **DESCRIPTION**                                                                                                                                                                                   |
| --------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `set -g status-justify [left\|centre\|right]`                                                             | Aligns the names of Tmux windows left/center/right                                                                                                                                                |
| `set -g status-left '...'`                                                                                | Replaces name of current session with ‘...’  in status bar                                                                                                                                        |
| <p><code>setw -g</code><br><code>window-status-format</code><br><code>`#[fg=white,bg=black]#I`</code></p> | <p>Formats the window names as follows:<br><br>Default window formatting:<br><br>Variables:<br><code>#I</code>: window index<br><code>#S</code>: session name<br><code>#W</code>: window name</p> |
