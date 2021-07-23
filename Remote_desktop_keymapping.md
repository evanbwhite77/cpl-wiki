# Remote desktop keymapping {#remote_desktop_keymapping}

If you\'re a mac user and you don\'t wanna have to confuse your muscle
memory with all new keyboard shortcuts while using the Windows remote
desktop, this is the guide for you.

1.  Download and install [Karabiner
    Elements](http://https://karabiner-elements.pqrs.org/)
2.  Download the [keymapping configuration
    file](https://drive.google.com/file/d/1Oen-5T9CGmu3PyT3WOL3FPwSHXuF8xDJ/view?usp=sharing).
    This is a file containing three custom keymappings for Microsoft
    Remote Desktop.
3.  You now need to move the file containing the keymappings to the
    place that Karabiner looks for it, which is
    \`\~/.config/karabiner/karabiner.json\`. You can do this in
    commandline, or from finder by entering command+shift+G and typing
    \'\~/.config/karabiner\' in the window that pops up to navigate to
    the destination, then dragging and dropping it there from another
    finder window. You\'ll also need to rename it to \`karabiner.json\`.
4.  Start Karabiner if it is not already running. You should see a
    little square on the bar at the top of the screen. Click it and hit
    preferences. Navigate to the \`Complex modifications\` tab. You
    should see three enabled rules:

-   -   Map command+2 to F2 on remote desktop
    -   Map option +L/R arrow to command+L/R arrow and control+L/R arrow
        to option+L/R arrow on remote desktop
    -   Swap command and control on remote dekstop

1.  Remove any of these you don\'t want, otherwise you should be all
    set!
2.  Feel free to reach out to me (Charles) if there are other
    keybindings you want.