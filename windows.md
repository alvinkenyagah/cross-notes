## Windows Hacks and Tips

### Activate Windows
- Run powershell as admin and enter command `irm https://get.activated.win | iex`

### Remove MS Edge
- Run powershell as admin and enter command `iex(irm https://cdn.jsdelivr.net/gh/he3als/EdgeRemover@main/get.ps1)`


### OLD CONTEXT MENU


- Right-click the Start button and choose Windows Terminal.
- Copy the following command and paste it into the Windows Terminal window:

`reg.exe add "HKCU\Software\Classes\CLSID\{86ca1aa0-34aa-4e8b-a509-50c905bae2a2}\InprocServer32" /f /ve`

- Press Enter to execute the command.
- Restart File Explorer or your computer for the changes to take effect. You’ll now see the legacy right-click context menu by default2.

### RESTORE OLD MENU

`reg.exe delete "HKCU\Software\Classes\CLSID\{86ca1aa0-34aa-4e8b-a509-50c905bae2a2}" /f`
