fglrx is not supported on any recent linux kernel. This is the patch file that will make it work for recent kernels. I'm using fedora 31 with the newest kernel.

If you are still using fglrx on a recent kernel (5.5+)

requirements:
xorg server version 1.17. Anything more recent the fglrx driver is not supported.

I'm running on Fedora 31 but use Fedora 22's x11 server. You can revert using rpm commands.  
If you have a more recent x11 server, you can revert using fedora 22 xorg-x11 with files as:

xorg-x11-server-Xorg-1.17.4-1.fc22.x86_64
xorg-x11-server-common-1.17.4-1.fc22.x86_64
xorg-x11-server-Xvfb-1.17.4-1.fc22.x86_64
xorg-x11-server-Xwayland-1.17.4-1.fc22.x86_64
xorg-x11-server-Xephyr-1.17.4-1.fc22.x86_64

Once reverted, add this exlude to the updates, so it won't use a recent xorg.
Update repo:
file: etc/yum.repos.d/fedora-updates.repo
section: [updates]

exclude=xorg-x11-server-Xorg xorg-x11-server-common xkeyboard-config

You can use any recent kernel now. This is the patch file needed for it to work on recent kernels
