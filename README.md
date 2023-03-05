# i3-vm-README

You can install i3 window manager through `sudo apt install i3` in Ubuntu 20.0.4.
Once the installation is completed, you need to simply log out and before logging in, go to the settings and switch to i3 environment and then log in.  
Now you will see a prompt asking you to make a .config file. Press enter and select your modifier key which is windows key in my case.
After hitting enter, you shall see a blank purple background with a thin taskbar at the bottom.
Learn some basic commands like opening a new terminal, opening new tabs and configuring their layouts horizontally or vertically, stacking, tabbing the terminals, creating and switching to new workspaces and opening applications.  
Once I learnt these I realised I really needed to config the wm as there were some very obvious changes to be made.  
The first was tap to left click and set the natural scroll direction. To do these, I appended the following in my `.config` file which I found in the `~/.config/i3/config`. If you missed to create the config file in the beginning, you can run `i3-config-wizard` command in the terminal.  

```
```

`xinput` shows all the available input devices and we can also change their properties through the `xinput set-props <DEVICE_ID> <PROPERTY_ID> 1`  
