# Copy Mode

| **COMMAND**                            | **DESCRIPTION**                                                        |
| -------------------------------------- | ---------------------------------------------------------------------- |
| `Ctrl + B` ->  :`setw -g mode-keys vi` | Use vi keys in the buffer (vi: vim editor)                             |
| `Ctrl + B` ->  `[`                     | Enter copy mode                                                        |
| `↑`                                    | Scroll up                                                              |
| `↓`                                    | Scroll down                                                            |
| **q**                                  | Quit copy mode                                                         |
| **0**                                  | Go to beginning of line                                                |
| **$**                                  | Go to end of line                                                      |
| **g**                                  | Go to first line                                                       |
| **G**                                  | Go to last line                                                        |
| **h**                                  | Move cursor left                                                       |
| **j**                                  | Move cursor down                                                       |
| **k**                                  | Move cursor up                                                         |
| **l**                                  | Move cursor right                                                      |
| **b**                                  | Traverse text content backward, cursor on first character of each word |
| **e**                                  | Traverse text content forward, cursor on last character of each word   |
| **w**                                  | Traverse text content one word at a time                               |
| **/**                                  | Search forward                                                         |
| **?**                                  | Search backward                                                        |
| **n**                                  | Next keyword occurrence                                                |
| **N**                                  | Previous keyword occurrence                                            |
| **\[Spacebar]**                        | Begin selection                                                        |
| **\[Enter]**                           | Copy selection                                                         |
| **ESC**                                | Clear selection                                                        |
| `Ctrl + B` ->  `]`                     | Paste selection                                                        |
| `Ctrl + B` ->  :`show-buffer`          | Display buffer\_0 contents                                             |
| `Ctrl + B` ->  :`capture-pane`         | Copy whole visible contents of the pane to a buffer                    |
| `Ctrl + B` ->  :`list-buffers`         | Show all buffers                                                       |
| `Ctrl + B` ->  :`choose-buffer`        | Show all buffers and paste selected                                    |
| `Ctrl + B` ->  :`save-buffer buf.txt`  | Save buffer contents to `buf.txt`                                      |
| `Ctrl + B` ->  :`delete-buffer -b 1`   | Delete `buffer_1`                                                      |
