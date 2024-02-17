# Windows

A single/split view of open panes occupying the screen.

| **COMMAND**              | **DESCRIPTION**                                                                    |
| ------------------------ | ---------------------------------------------------------------------------------- |
| `tmux new -s s1 -n w2`   | Create new session `s1` and window `w2`                                            |
| `Ctrl + B` -> `c`        | Create new window                                                                  |
| `Ctrl + B` -> `,`        | Rename active window                                                               |
| `Ctrl + B` -> `&`        | Kill / Close active window (Tmux may prompt you to confirm your action with `y/n`) |
| `Ctrl + B` -> `p`        | Navigate to previous window                                                        |
| `Ctrl + B` -> `n`        | Navigate to next window                                                            |
| `Ctrl + B` -> `w`        | List windows (which you may select and expand / collapse with arrow keys)          |
| `Ctrl + B` -> `0`....`9` | Select window by number                                                            |
| `Ctrl + B` -> `'`        | Select window by name / index                                                      |
| `Ctrl + B` -> `.`        | Change window number                                                               |
| `Ctrl + B` -> `F`        | Search windows                                                                     |
| `:swap-window -s 0 -t 2` | Swap windows 0 and 2                                                               |
| `:swap-window -t -1`     | Move active window to the left by one position                                     |
