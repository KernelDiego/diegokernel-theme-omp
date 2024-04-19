
# How config theme in Windows:

## Install OhMyPosh with winget

```powershell
winget install JanDeDobbeleer.OhMyPosh -s winget
```

> This installs a couple of things:
- oh-my-posh.exe - Windows executable
- themes - The latest Oh My Posh themes

---

## Add path Oh My Posh

For the PATH to be reloaded, a restart of your terminal is advised. If oh-my-posh is not recognized as a command, you can run the installer again, or add it manually to your PATH. For example:

```powershell
$env:Path += ";C:\Users\user\AppData\Local\Programs\oh-my-posh\bin"
```

---

## ANTIVIRUS SOFTWARE

> Due to frequent updates of Oh My Posh, Antivirus software occasionally flags it (false positive). To ensure Oh My Posh isn't blocked you can either report it to your favorite Antivirus software as false positive (e.g. Report a false positive/negative to Microsoft for analysis) or create an exclusion for it. Exclusions should be added with the full path to the executable, you can get it with the following command from a PowerShell prompt:

```powershell
(Get-Command oh-my-posh).Source
```

---

## Update Oh My Posh

```powershell
winget upgrade JanDeDobbeleer.OhMyPosh -s winget
```

---

## Add My config

```powershell
oh-my-posh init pwsh --config 'https://raw.githubusercontent.com/KernelDiego/diegokernel-theme-omp/main/diegokernel.omp.json' | Invoke-Expression
```

## Once altered, reload your profile for the changes to take effect.

```powershell
. $PROFILE
```

> When the above command gives an error, make sure to create the profile first and add the oh-my-posh init above.

```powershell
New-Item -Path $PROFILE -Type File -Force
```

> Create a file in this path with this name

```powershell
C:\Users\user\OneDrive\Documentos\WindowsPowerShell\Microsoft.PowerShell_profile.ps1
```

> And add and save the following to the Microsoft.PowerShell_profile.ps1 file:

```powershell
oh-my-posh init pwsh --config 'https://raw.githubusercontent.com/KernelDiego/diegokernel-theme-omp/main/diegokernel.omp.json' | Invoke-Expression
```

> In this scenario, it can also be that PowerShell blocks running local scripts. To solve that, set PowerShell to only require remote scripts to be signed using *Set-ExecutionPolicy RemoteSigned*, or sign the profile.
