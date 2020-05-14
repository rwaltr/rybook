#Tidbits

### Chocolaty
Need a package manager for windows. Use [choco!](https://chocolatey.org/)

Run the following as an Administrator in CMD!

    @"%SystemRoot%\System32\WindowsPowerShell\v1.0\powershell.exe" -NoProfile -InputFormat None -ExecutionPolicy Bypass -Command "iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))" && SET "PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin"

Then you can use ```` choco install <$> ```` to install common packages!


### Magic Wormhole
Magic wormhole is easy to install on linux, but on windows it has more stuff to install than normal. [This snippit helps](https://gist.github.com/princebot/782a86e8f75709ca405f9acdee1d247d)

```powershell
::
:: This script installs wormhole (https://github.com/warner/magic-wormhole) and
:: its prerequisites. Run this as an administrator.
::

:: Install chocolatey.
@"%SystemRoot%\System32\WindowsPowerShell\v1.0\powershell.exe" -NoProfile -InputFormat None -ExecutionPolicy Bypass -Command "iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))" && SET "PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin"

:: Install Python 3.
choco install -y python

:: Install Microsoft Visual C++ Build Tools 2015.
choco install -y vcbuildtools

:: Refresh environment variables so that we can call Python (this is not a 
:: native shell command: it is a script installed as part of chocolatey).
call RefreshEnv

:: Install wormhole.
pip install magic-wormhole
```
