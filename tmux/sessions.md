# Sessions

A single collection of pseudo-terminals under the management of Tmux. Once you kill the last session, Tmux exits. Each session is persistent and will survive accidental disconnection (such as SSH connection timeout) or intentional detaching by the user.In the example above, the session comprises panes 0:bash, 1:bash, and 2:bash. The current pane is 2:bash, marked by an asterisk \*. Here, the cursor is active, and you can type into the pane. The other pane in the same window is 1:bash, marked by a hyphen -.

## New Sessions

| **COMMAND**                                                                        | **DESCRIPTION**                             |
| ---------------------------------------------------------------------------------- | ------------------------------------------- |
| <p><code>tmux</code><br><code>tmux new</code><br><code>tmux new-session</code></p> | Create new session from CLI                 |
| **Ctrl+b** :`new`                                                                  | Create new session from inside Tmux         |
| `tmux new -s sess0`                                                                | Create new session named `sess0`            |
| **Ctrl+b** :`new sess0`                                                            | Create new session `sess0` from inside Tmux |

***

## List Sessions

| **COMMAND**                                                    | **DESCRIPTION**                    |
| -------------------------------------------------------------- | ---------------------------------- |
| <p><code>tmux ls</code><br><code>tmux list-sessions</code></p> | Show all sessions                  |
| **Ctrl+b** `s`                                                 | Show all sessions from inside Tmux |

***

## Attach Sessions

| **COMMAND**                                                                                                        | **DESCRIPTION**                             |
| ------------------------------------------------------------------------------------------------------------------ | ------------------------------------------- |
| <p><code>tmux a</code><br><code>tmux at</code><br><code>tmux attach</code><br><code>tmux attach-session</code></p> | Attach to the most recently created session |
| `tmux a -t s0`                                                                                                     | Attach to session `s0`                      |

***

## Terminate Sessions

| **COMMAND**                                                         | **DESCRIPTION**                          |
| ------------------------------------------------------------------- | ---------------------------------------- |
| <p><code>tmux kill-ses</code><br><code>tmux kill-session</code></p> | Kill last active session                 |
| `tmux kill-ses -t s0`                                               | Kill session named `s0`                  |
| `tmux kill-ses -a`                                                  | Kill all sessions except the current one |
| `tmux kill-ses -a -t s0`                                            | Kill all sessions except `s0`            |

***

## Operations

| Key Binding        | Description                |
| ------------------ | -------------------------- |
| `Ctrl + B` ->  `$` | Rename Session             |
| `Ctrl + B` -> `d`  | Detach from Session        |
| `Ctrl + B` -> `w`  | Session and Window Preview |
| `Ctrl + B` -> `(`  | Move to Previous Session   |
| `Ctrl + B` -> `)`  | Move to Next Session       |
