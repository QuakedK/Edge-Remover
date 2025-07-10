# What gets downloaded?

A folder named Edge Remover is created in your C: drive, and Setup.exe is downloaded and placed inside it

# #1 What's Setup.exe?
Setup.exe is the old and offical Microsoft Edge Installer, as noted by it being offically signed by Microsoft Corporation.
The Setup's purpose is to uninstall Edge with the following the following Command-Line Arguments --uninstall --system-level --force-uninstall.
```bat
:: Example with Command-Line Arguments.
"C:\Edge Remover\setup.exe" --uninstall --system-level --force-uninstall
```
# #2 File Signing and legitimacy
<img width="1214" height="507" alt="Edge Signing" src="https://github.com/user-attachments/assets/055bf0db-e497-4db5-be50-8eed23d6187a" />

# #3 Download Code.
```bat
:: Downloading Microsoft Edge Setup (Used for uninstalling Edge with Command-Line Arguments)
set "EdgeSetupURL=https://github.com/QuakedK/Edge-Remover/raw/refs/heads/main/Downloads/setup.exe"
set "EdgeSetupName=setup.exe"
set "DownloadsFolder=C:\Edge Remover"
mkdir "C:\Edge Remover" >nul 2>&1
curl -s -L "%EdgeSetupURL%" -o "%DownloadsFolder%\%EdgeSetupName%"
if exist "%DownloadsFolder%\%EdgeSetupName%" (
    echo Microsoft Edge Setup installed successfully. >nul 2>&1
    goto :EdgeMenu
) else (
    echo Microsoft Edge Setup failed to installed. >nul 2>&1
    goto :EdgeInstallFailed
) 
```
