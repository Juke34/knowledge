Screen Cheat Sheet
=================

From [http://aperiodic.net/screen/quick_reference](http://aperiodic.net/screen/quick_reference)

### Getting in
  
| Command | Description 
| ---  | ---
| screen -S \<name\> | start a new screen session with session \<name\>
| screen -ls | list running sessions/screens
| screen -x | attach to a running session
| screen -r <name> | attach to session \<name\>
| screen -dRR | the “ultimate attach”: Attaches to a screen session. If the session is attached elsewhere, detaches that other display. If no session exists, creates one. If multiple sessions exist, uses the first one.


### Getting out

| Command | Description 
| ---  | ---
| Ctrl-a d | detach
| Ctrl-a D D | detach and logout (quick exit)
| Ctrl-a \ | exit screen, Exit all of the programs in screen.
| Ctrl-a Ctrl-\ | force-exit screen
| exit | getting out of the screen session

### Window Management

| Command | Description 
| ---  | ---
| Ctrl-a c | create new window
| Ctrl-a Ctrl-a | change to last-visited active window
| Ctrl-a \<number\> | change to window by number
| Ctrl-a ' \<number or title\> | change to window by number or name
| Ctrl-a n | change to next window in list
| Ctrl-a \<space\> | rchange to next window in list
| Ctrl-a p | change to previous window in list
| Ctrl-a \<backspace\> | change to previous window in list
| Ctrl-a " | see window list
| Ctrl-a w | show window bar
| Ctrl-a k | kill current window
| Ctrl-a \ | kill all windows
| Ctrl-a A | rename current window
| _Close all applications in the current window (including shell)_ | close current window


### Split screen

| Command | Description 
| ---  | ---
| Ctrl-a S | split display horizontally
| Ctrl-a \| | split display vertically
| Ctrl-a V | split display vertically
| Ctrl-a tab | jump to next display region
| Ctrl-a X | remove current region
| Ctrl-a Q | remove all regions but the current one

### Clipboard and Navigation

| Command | Description 
| ---  | ---
| Ctrl-a \[ | freely navigate buffer
| Ctrl-a \<esc> | freely navigate buffer
| space | toggle selection to copy
| Ctrl-a ] | paste

See also [here](http://aperiodic.net/screen/commands:copy)

### Help

| Command | Description 
| ---  | ---
| Ctrl-a ? | See help (lists keybindings)


### Escape key
All screen commands are prefixed by an escape key, by default C-a (that's Control-a, sometimes written ^a). To send a literal C-a to the programs in screen, use C-a a. This is useful when working with screen within screen. For example C-a a n will move screen to a new window on the screen within screen.

### Misc

| Command | Description 
| ---  | ---
| Ctrl-a Ctrl-l | redraw window
| Ctrl-a M | monitor window for activity
| Ctrl-a _ | monitor window for silence
| Ctrl-a Ctrl-v | enter digraph (for producing non-ASCII characters)
| Ctrl-a x | lock session (password protect)
| Ctrl-a : | enter screen command
| Ctrl-a H | enable logging in the screen session

### Scrollback-buffer

In copy mode, one can navigate the scrollback buffer in various ways:

| Command | Description 
| ---  | ---
| Ctrl-u | half page up
| Ctrl-d | half page down
| Ctrl-b | back
| Ctrl-f | forward
| h | cursor left
| j | cursor down
| k | cursor up
| l | cursor right

### Scripting

| Command | Description 
| ---  | ---
| screen -S <name> -X <command> | send a command to a named session 
| screen -S <name> -X screen ping example.com | create a new window and run ping example.com
| screen -S <name> [-p <page>] -X stuff $'quit\r' | stuff characters into the input buffer using bash to expand a newline character

An example:

    # run bash within screen
    screen -AmdS bash_shell bash
    # run top within that bash session
    screen -S bash_shell -p 0 -X stuff $'top\r'

    # ... some time later

    # stuff 'q' to tell top to quit
    screen -S bash_shell -X stuff 'q'
    # stuff 'exit\n' to exit bash session
    screen -S bash_shell -X stuff $'ex

### Screenrc

[https://gist.github.com/mosquito/d109e44a2c6884c34f9c](https://gist.github.com/mosquito/d109e44a2c6884c34f9c)
