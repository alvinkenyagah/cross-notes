# Setup


## oh my posh terminal theming

https://ohmyposh.dev/docs/installation/linux

The cmd theme config located in clink directory ie `C:\Program Files (x86)\clink` file called `oh-my-posh.lua`

To configure powershell theme enter `notepad $PROFILE`

### configure linux terminal

Install brew
`/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"`

Install oh my posh `brew install jandedobbeleer/oh-my-posh/oh-my-posh` .

Add `eval "$(oh-my-posh init bash)"` at the end of the line of `.bashrc` .

Run `exec bash` to restart termnal for effect to take place.

Customize your terminal adding a predefined theme ie `eval "$(oh-my-posh init bash --config /home/linuxbrew/.linuxbrew/Cellar/oh-my-posh/16.2.3/themes/emodipt-extend.omp.json)"       _`

find all available themes by entering ``` ls /home/linuxbrew/.linuxbrew/Cellar/oh-my-posh/16.2.3/themes/ ``` in the termianal


### wsl shell theming

https://learn.microsoft.com/en-us/windows/terminal/tutorials/custom-prompt-setup#customize-your-wsl-prompt-with-oh-my-posh

# Initializing WSL desktop GU



## WSL 2 GNOME Desktop

**NOTE:** If you want the ultimate Linux desktop experience, I highly recommend installing Linux as your main OS. I no longer use Windows (except in a VM) so I will not be maintaining this guide anymore.

Think Xfce looks dated? Want a conventional Ubuntu experience? This tutorial will guide you through installing Ubuntu's default desktop environment, GNOME.

GNOME is one of the more complex — and that means more difficult to run — desktop environments, so [for](https://www.reddit.com/r/Windows10/comments/8dnyig/using_a_gui_with_wsl_on_windows_10_ubuntu_wsl/) [years](https://www.reddit.com/r/bashonubuntuonwindows/comments/9amqjr/gnome_desktop_using_vcxsrv_cant_make_it_work/) [people](https://askubuntu.com/questions/1169695/gnome-under-ubuntu-18-04-for-windows-wont-run) [couldn't](https://superuser.com/questions/1559755/gnome-desktop-environment-on-ubuntu-wsl-starting-error) [figure](https://www.reddit.com/r/bashonubuntuonwindows/comments/haof3n/cant_run_gnome_in_ubuntu_2004_lts_wsl/) [out](https://www.reddit.com/r/bashonubuntuonwindows/comments/eqwoxy/gnome_and_kde_in_wsl/) [how](https://www.reddit.com/r/bashonubuntuonwindows/comments/8dp2yu/gnome_or_kde_on_wsl/) [to](https://www.reddit.com/r/bashonubuntuonwindows/comments/hh0q9s/gnomesession_wsl2/) [run](https://www.reddit.com/r/bashonubuntuonwindows/comments/b222hp/running_everything_on_gnome/) [it](https://www.reddit.com/r/bashonubuntuonwindows/comments/8yfw8z/gnome_on_windows/) on WSL 2. On [WSL 1](https://github.com/Microsoft/WSL/issues/637) it could only run using very complicated methods that didn't transfer to well WSL 2. Any forlorn attempts to run it on WSL 2 only resulted in a smoldering heap of error messages.

__But now you can!__


## Requirements:
 - WSL 2
 - Ubuntu 20.04 (other distros not tested)
 - An X server for Windows, such as [VcXsrv](https://sourceforge.net/projects/vcxsrv/)
 - Basic knowledege on how to run GUI apps with WSL 2 (not required but highly recommended)


## Getting ready

You've been regularly updating your distro, haven't you?

```sh
sudo apt update
sudo apt upgrade
```

Install GNOME: (maybe go eat a snack while it's installing?)

```sh
sudo apt install ubuntu-desktop gnome
```

Open up your `~/.bashrc`:

```sh
nano ~/.bashrc
```

And paste this in at the end and save:

```sh
export DISPLAY=$(cat /etc/resolv.conf | grep nameserver | awk '{print $2}'):0
export LIBGL_ALWAYS_INDIRECT=1
```

If you try to start GNOME now, you'll get a lot of errors. Something along the lines of this, but a ton more errors:

```sh
Unable to init server: Could not connect: Connection refused

(gnome-session-check-accelerated:6054): Gtk-WARNING **: 11:04:51.973: cannot open display: :0
Unable to init server: Could not connect: Connection refused

(gnome-session-check-accelerated:6055): Gtk-WARNING **: 11:04:52.234: cannot open display: :0
gnome-session-binary[6044]: WARNING: software acceleration check failed: Child process exited with code 1
gnome-session-binary[6044]: CRITICAL: We failed, but the fail whale is dead. Sorry....
```

The trick is to enable `systemd`: (note that this does break a lot of stuff such as Visual Studio Code Remote)

```sh
git clone https://github.com/DamionGans/ubuntu-wsl2-systemd-script.git
cd ubuntu-wsl2-systemd-script/
bash ubuntu-wsl2-systemd-script.sh
```

Now shut down WSL 2: (run this in Windows)

```sh
wsl --shutdown
```


## Starting GNOME

First, fire up your X server on Windows. Make sure you let it through your firewall and disable access control.

Now, start up Ubuntu again and start GNOME:

```sh
gnome-session
```

If you don't get any error messages, you should be good. Wait a few seconds for GNOME to start up.

<img width="1007" alt="desktop" src="https://user-images.githubusercontent.com/50341827/88995077-68591600-d2af-11ea-91e6-55d528a57dd2.png">

Now you have a great GUI desktop and you won't need any intensive virtual machines anymore!

Profit?


## Notes

 - You can disable the screensaver with `gsettings set org.gnome.desktop.session idle-delay 0`.
 - You can also try KDE Plamsa using a similar method! Just `sudo apt install kde-plasma-desktop` instead and start it with `startplasma-x11`.


## Troubleshooting

If you can't get this to work, try [Xfce](https://github.com/QMonkey/wsl-tutorial/blob/master/README.wsl2.md).

If you still can't get it to work, you can ask for help on an online forum such as [r/bashonubuntuonwindows](https://www.reddit.com/r/bashonubuntuonwindows/).




<ul>

<li>  
  
### Kali
https://www.kali.org/docs/wsl/win-kex/#optional-steps
  
In kali terminal run ``` kex --sl -s ```
 
Start Win-KeX as root in window mode via: ``` sudo kex –esm ```

  </li>
  
  <li>

### Ubuntu

In ubuntu terminal run `sudo /etc/init.d/xrdp start`

Open remote desktop and paste `localhost:3390`

  </li>
    
  </ul>

## Configuring github ssh

`cd ~/.ssh && ls`   //Check for existing keys

`ssh-keygen -o -t rsa -C "your-email@mail.com"`  //Create ssh key

`cat ~/.ssh/id_rsa.pub`   //view public key

https://github.com/settings/keys    //Add your public key to GitHub

`eval $(ssh-agent) && ssh-add ~/.ssh/id_rsa &>/dev/null`  (keeps asking for key)

## NODE TUNNEL

`npm install -g localtunnel`
### Usage
`lt --port 8000`

### Debloat windows
- Run Windows powershell as administrator
- `iwr -useb https://christitus.com/win | iex`

## Create Swap Partition on Linux
- `https://www.digitalocean.com/community/tutorials/how-to-add-swap-space-on-ubuntu-22-04`
