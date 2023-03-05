# i3-vm-README

You can install i3 window manager through `sudo apt install i3` in Ubuntu 20.0.4.
Once the installation is completed, you need to simply log out and before logging in, go to the settings and switch to i3 environment and then log in.  
Now you will see a prompt asking you to make a .config file. Press enter and select your modifier key which is windows key in my case.
After hitting enter, you shall see a blank purple background with a thin taskbar at the bottom.
Learn some basic commands like opening a new terminal, opening new tabs and configuring their layouts horizontally or vertically, stacking, tabbing the terminals, creating and switching to new workspaces and opening applications.  
Once I learnt these I realised I really needed to config the wm as there were some very obvious changes to be made.  
The first was tap to left click and set the natural scroll direction. To do these, I appended the following in my `.config` file which I found in the `~/.config/i3/config`. If you missed to create the config file in the beginning, you can run `i3-config-wizard` command in the terminal.  

```
#My configs begin

#Touchpad configs
exec xinput set-prop 11 322 1
exec xinput set-prop 11 330 1

# Screenshots
bindsym Print exec --no-startup-id maim "/home/$USER/Pictures/$(date)"
bindsym $mod+Print exec --no-startup-id maim --window $(xdotool getactivewindow) "/home/$USER/Pictures/$(date)"
bindsym Shift+Print exec --no-startup-id maim --select "/home/$USER/Pictures/$(date)"

## Clipboard Screenshots
bindsym Ctrl+Print exec --no-startup-id maim | xclip -selection clipboard -t image/png
bindsym Ctrl+$mod+Print exec --no-startup-id maim --window $(xdotool getactivewindow) | xclip -selection clipboard -t image/png
bindsym Ctrl+Shift+Print exec --no-startup-id maim --select | xclip -selection clipboard -t image/png

```

`xinput` shows all the available input devices and we can also change their properties through the `xinput set-props <DEVICE_ID> <PROPERTY_ID> 1`  

`exec <Command>` executes the command whenever the i3 session begins.  

Now I added more custom commands such as,
```
bindsym $mod+shift+x exec i3lock
```

As you may find, this notation is very intuitive as in it binds the `$mod`+`shift`+`x` key combination to this execution of i3lock command. So now we don't need to open a terminal and enter the command each time we want to lock.
