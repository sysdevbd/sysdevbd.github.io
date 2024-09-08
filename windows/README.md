# Windows

## Links
- https://learn.microsoft.com/en-us/windows/wsl/install
- https://learn.microsoft.com/en-us/windows/wsl/disk-space
- https://learn.microsoft.com/en-us/windows/wsl/tutorials/gui-apps

## Install Ubuntu 24.04
- Open Windows Terminal app in Administrator mode
- `wsl -l -o`
- `wsl --install -d Ubuntu-24.04`
- Exit and open Terminal app in regular mode
- `wsl -d Ubuntu-24.04`
- Once inside the Ubuntu prompt, make sudo password less `echo "$USER ALL=(ALL) NOPASSWD: ALL" >> /etc/sudoers`

## List installed distros

`wsl -l -v`

## Manage Disk space

Nothing needs to be done by default. Just confirm the virtual disk size is large enough (at least 250GB).

- `wsl --system -d Ubuntu-24.04 df -h /mnt/wslg/distro`
- `(Get-ChildItem -Path HKCU:\Software\Microsoft\Windows\CurrentVersion\Lxss | Where-Object { $_.GetValue("DistributionName") -eq 'Ubuntu-24.04' }).GetValue("BasePath") + "\ext4.vhdx"`

## Upgrade PowerShell

- https://learn.microsoft.com/en-us/powershell/scripting/install/installing-powershell-on-windows?view=powershell-7.4#winget
- `winget search Microsoft.PowerShell`
- `winget install --id Microsoft.PowerShell --source winget`
