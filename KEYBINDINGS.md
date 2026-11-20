# tmux-duk key bindings

These are the bindings tmux-duk changes or adds compared to stock tmux.
Everything not listed here keeps its stock tmux binding (see `prefix /` for
the full list, or `man tmux-duk`).

The **prefix is `Ctrl-Space`** (stock: `Ctrl-b`).

## Prefix key

| Key      | tmux-duk                     | Stock tmux           |
|----------|------------------------------|----------------------|
| `prefix` | `Ctrl-Space`                 | `Ctrl-b`             |
| `C-Space`| send the prefix to the app (`prefix C-Space`) | `C-b` did this |

## After the prefix

| Key       | tmux-duk                                          | Stock tmux                                  |
|-----------|---------------------------------------------------|---------------------------------------------|
| `?`       | cheatsheet popup, closes after 4.5 s or any key   | list all key bindings                       |
| `/`       | list all key bindings                             | describe a single key                       |
| `\|`      | split side by side, in the current directory      | unbound (stock used `%`)                    |
| `\`       | split side by side, in the current directory      | unbound                                     |
| `-`       | split top/bottom, in the current directory        | delete the most recent paste buffer         |
| `_`       | split top/bottom, in the current directory        | unbound (stock used `"`)                    |
| `c`       | new window, in the current directory              | new window (in the session's start directory) |
| `h`       | select the pane to the left                       | unbound                                     |
| `j`       | select the pane below                             | unbound                                     |
| `k`       | select the pane above                             | unbound                                     |
| `l`       | select the pane to the right                      | select the previously current window        |
| `H`       | resize the pane left by 5 (repeatable)            | unbound                                     |
| `J`       | resize the pane down by 5 (repeatable)            | unbound                                     |
| `K`       | resize the pane up by 5 (repeatable)              | unbound                                     |
| `L`       | resize the pane right by 5 (repeatable)           | switch to the last client                   |
| `X`       | kill the current window (asks first)              | unbound (stock used `&`)                    |
| `Tab`     | next window                                       | floating "switch to a window" picker        |
| `BTab` (Shift-Tab) | previous window                          | floating "switch to a session" picker       |
| `v`       | enter copy mode                                   | unbound (stock used `[`)                    |
| `r`       | reload `~/.config/tmux-duk/tmux.conf`             | redraw the client                           |

The stock keys these replaced as "the obvious way" still work: `%` and `"`
split, `&` kills a window, `[` enters copy mode, `w` and `s` open the window
and session trees.

## Without the prefix

All of these are new; stock tmux leaves them unbound.

| Key            | tmux-duk                         |
|----------------|----------------------------------|
| `Alt-h`        | select the pane to the left      |
| `Alt-j`        | select the pane below            |
| `Alt-k`        | select the pane above            |
| `Alt-l`        | select the pane to the right     |
| `Alt-1` … `Alt-9` | select window 1 … 9           |

## Copy mode (vi keys)

tmux-duk turns on vi keys (`mode-keys vi`, `status-keys vi`); stock tmux uses
emacs keys unless `EDITOR`/`VISUAL` contains `vi`.

| Key   | tmux-duk                       | Stock tmux (vi)        |
|-------|--------------------------------|------------------------|
| `v`   | begin a selection              | toggle rectangle mode  |
| `y`   | copy the selection and exit    | unbound                |
| `C-v` | toggle rectangle mode          | same (unchanged)       |

## Defaults that change how keys behave

| Option            | tmux-duk   | Stock tmux |
|-------------------|------------|------------|
| `mouse`           | on         | on in tmux portable builds (off on OpenBSD) |
| `base-index`      | 1          | 0          |
| `pane-base-index` | 1          | 0          |
| `renumber-windows`| on         | off        |

Because windows start at 1, the stock `prefix 0` … `prefix 9` keys line up
with the window numbers: `prefix 1` is the first window.
