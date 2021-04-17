# dotfiles for Pop OS! i3

## What is this?

This is a minimal set of dotfiles/configs for i3 window manager, picom compistor,
rofi launcher, and alacritty terminal.

This provides some basic configurations which integrate with a Pop OS GNOME environment.

I intentionally don't have a fancy status bar, and this configuration will simply run the default i3status. 
This leaves that to the user, but provides basic theming.

Also, fancy rofi configuration is left out, though much is possible.


## What's required?

This assumes you've been running standard GNOME on Pop OS and thus are using the GDM login manager.

There's some packages to install on your Pop OS system before you can use this:

`sudo apt install i3 picom rofi alacritty feh gnome-flashback pasystray blueman`


A few settings must be configured for `gnome-flashback`:

First, this prevents the gnome desktop from showing up (it wouldn't work right anyway):

`gsettings set org.gnome.gnome-flashback desktop false`

Second, this prevents gnome from holding the systemtray, and allow i3bar to handle it:

`gsettings set org.gnome.gnome-flashback status-notifier-watcher false`


Now, I suggest using the `i3-gnome` project: https://github.com/i3-gnome/i3-gnome

You should read their docs, but essentially it creates an X session for Gnome+i3 and
puts a few scripts in place to run gnome-session with i3.

On Pop OS, we use the "Installation using make" instructions:

```
git clone git@github.com:i3-gnome/i3-gnome.git.
cd i3-gnome
sudo make install
```

Now, the config files from this repo should be copied to their respective locations.

```
mkdir -p $HOME/.config/{alacritty,i3,picom,rofi}
# copy files
```

Logout of GNOME.

In GDM, select your username, use the "gear" icon in lower right to choose "i3 - GNOME", then login.
