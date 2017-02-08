# Bash-Screen-Flip
Simple bash script that read screen state and inverts/reverts it accordingly

#!/bin/sh
rotation="$(xrandr -q --verbose|grep eDP-1|cut -b45-50)"
check="normal"
if [ "$check" == "$rotation" ];then
xrandr -o inverted
else
xrandr -o normal
fi
