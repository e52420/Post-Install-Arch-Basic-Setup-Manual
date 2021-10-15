# ayoub-basic-config

# Basic system utilities


## Programs

```bash
sudo pacman -S pulseaudio pavucontrol pamixer libnotify notification-daemon udiskie ntfs-3g cbatticon volumeicon glib2 gvfs picom lxappearance feh nitrogen lxsession neovim rofi ranger thunar trayer vlc kvantum-qt5 libmtp simple-mtpfs kdenlive obs-studio discord 
```
## Fonts 

```bash
sudo pacman -S ttf-dejavu ttf-liberation noto-fonts
```

## Xprofile

Now you can use *~/.xprofile* to run programs before your window manager starts:

```bash
touch ~/.xprofile
```

```bash
setxkbmap es &
nm-applet &
udiskie -t &
volumeicon &
cbatticon &
picom &
nitrogen --restore &
lxsession &
lxappearance &
```

## Systray

By default, you have a system tray in Qtile, but there's nothing running in it.
You can launch the programs we've just installed like so:

```bash
udiskie -t &
nm-applet &
```

Now you should see icons that you can click to configure drives and networking.
Optionally, you can install tray icons for volume and battery:

```bash
sudo pacman -S volumeicon cbatticon

```
## Notifications

I like having desktop notifications as well, for that you need to install
[**libnotify**](https://wiki.archlinux.org/index.php/Desktop_notifications#Libnotify)
and [**notification-daemon**](https://www.archlinux.org/packages/community/x86_64/notification-daemon/):

```bash
sudo pacman -S libnotify notification-daemon
```

```bash
# Create this file with nano or vim
sudo nvim /usr/share/dbus-1/services/org.freedesktop.Notifications.service
# Paste these lines
[D-BUS Service]
Name=org.freedesktop.Notifications
Exec=/usr/lib/notification-daemon-1.0/notification-daemon
```

Test it like so:

```bash
notify-send "Hello World"
```

## Qt

[**Kvantum**]

```bash
echo "export QT_STYLE_OVERRIDE=kvantum" >> ~/.profile
```

