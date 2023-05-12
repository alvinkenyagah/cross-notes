# cross-notes

## ohmyposh terminal theming

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

## Initializing WSL desktop GUI

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
