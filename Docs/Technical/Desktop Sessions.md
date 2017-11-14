#### Desktop sessions

Set Default session (should probably be done on fat client chroot; perhaps not necessary if LDM-SESSION is set to `Lubuntu.desktop` in `ltsp.conf`)

From:

http://askubuntu.com/questions/62833/how-do-i-change-the-default-session-for-when-using-auto-logins

 The list of sessions is described in the directory

    /usr/share/xsessions

Some of the more common session names are as follows:
For unity-2d the session file is called `ubuntu-2d.desktop`

For gnome-classic the session file is called `gnome-classic.desktop`

For gnome-classic (no effects) aka gnome-fallback the session file is called `gnome-fallback.desktop`

For unity-3d the session file is called ubuntu.desktop

For Lubuntu the session file is called `Lubuntu.desktop`

For LXDE the session file is called `LXDE.desktop`
Thus, if you change the light-dm configuration file to "ubuntu-2d" this will default the session to Unity-2D
i.e.
sudo nano /etc/lightdm/lightdm.conf


change the line

    user-session=ubuntu

to

    user-session=ubuntu-2d

Note - if you don't have a lightdm.conf file then for a autologin use the following values for this file:

    [SeatDefaults]
    greeter-session=unity-greeter
    user-session=ubuntu-2d
    autologin-user=myusername
    autologin-user-timeout=0

Another possibility is to run:

    sudo /usr/lib/lightdm/lightdm-set-defaults -s <session-name>


E.g.:

    sudo /usr/lib/lightdm/lightdm-set-defaults -s ubuntu-2d


This will also create the lightdm.conf file if it wasn't already present.
