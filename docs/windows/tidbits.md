#Tidbits

Need a package manager for windows. Use [choco!](https://chocolatey.org/)

Run the following as an Administrator in CMD!

    @"%SystemRoot%\System32\WindowsPowerShell\v1.0\powershell.exe" -NoProfile -InputFormat None -ExecutionPolicy Bypass -Command "iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))" && SET "PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin"

Then you can use ```` choco install <$> ```` to install common packages!

