# kali Linux GUI Desktop in Android using Termux

### Just Follow the steps to install Kali Linux with XFCE4 Desktop GUI in Android using Termux:

* Download and install [Termux](https://f-droid.org/en/packages/com.termux/) in Android. ([Play Store release](https://play.google.com/store/apps/details?id=com.termux) is no more updated, so is not recommended.)
* Open Termux and run the following commands (will download around 100MB of files):
  ```
  apt update
  apt install proot-distro -y
  proot-distro install nethunter
  proot-distro login nethuter
  ```
* After completion of the above steps, you will be in Kali Linux Shell. Rul the following commands in the Kali Shell (will download another 100MB of files):
  ```
  apt update
  apt install --no-install-recommends xfce4 -y
  apt install dbus-x11 -y
  apt install tightvncserver -y
  vncserver
  ```
* When it asks, Create and confirm a new password and remember it. You will need it to login in later steps.
* After setting the password, run the following command:
  ```
  vncserver -kill :1
  rm -f ~/.vnc/xstartup
  echo -e '#!/bin/bash\nxrdb \$HOME/.Xresources\nstartxfce4 &' > ~/.vnc/xstartup
  sudo chmod +x ~/.vnc/xstartup
  vncserver
  ```
* Let Termux run in background by pressing HOME button in Android.
* Install [VNC Viewer](https://play.google.com/store/apps/details?id=com.realvnc.viewer.android) in Android and open it.
* Press the + button in the lower right corner.
  * Under Address type `localhost:5901`.
  * Under Name type any name (doesn't matter) to remember that its Kali Linux on Termux.
  * Press Create and an Entry by the name you entered will appear.
* Press the entry you just created in VNC Viewer.
* Type in the password you created in the fourth step (Turn on the Remember password slider if preffered) and press continue in the upper right corner.
* You will soon be in your Kali Linux XFCE4 Desktop Environment.