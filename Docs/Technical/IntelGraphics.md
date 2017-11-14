#### Intel Graphics Drivers for LTSP Fat clients
http://techplay.net/blog/2014/12/10/intel-graphics-installer-on-ubuntu-14-dot-04-x64-ltsp-clients/

On the client chroot:

     Edit /etc/apt/sources.list.d/intellinuxgraphics.list
Add


     deb https://download.01.org/gfx/ubuntu/14.04/main trusty main # Intel Graphics Drivers
1. Save the file
2. Run


     wget --no-check-certificate https://download.01.org/gfx/RPM-GPG-KEY-ilg -O - | \
     sudo apt-key add -
Run (yes, it looks similar, but not quite)
1
2


    wget --no-check-certificate https://download.01.org/gfx/RPM-GPG-KEY-ilg-2 -O - |
    sudo apt-key add -


Run

    apt-get update

Run

    apt-get install i965-va-driver:amd64 libva-drm1:amd64 libva-egl1:amd64 libva-glx1:amd64 libva-intel-vaapi-driver:all libva-tpi1:amd64 libva-wayland1:amd64 libva-x11-1:amd64 libva1:amd64 vainfo:amd64

Run

    apt-get upgrade

Once complete, you should now have the same packages installed after running the intel-linux-graphics-installer manually. I haven’t tried it, but the same option should work with 32-bit systems if you remove the

    :amd64

option from the package names.
