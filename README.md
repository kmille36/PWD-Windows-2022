# PWD-Windows-2022

*NEWS: Try my labs: https://thuonghai2711.tech/pages/labs.html*

Under development. Testing purposes.

Video tutorial (Click on image to open Youtube video):

[![IMAGE ALT TEXT](http://img.youtube.com/vi/vPdvj_0ycDg/0.jpg)](https://youtu.be/vPdvj_0ycDg)

MS Learn 1H Remote App Demonstration

![image](https://user-images.githubusercontent.com/58414694/216879247-25b55257-1b63-45ab-808f-5bc1320eeb99.png)

Main: https://labs.play-with-docker.com/ (guacamole)

(ctrl+insert copy), (shift+insert paste)

``` bash
wget https://github.com/kmille36/PWD-Windows-2022/raw/main/alpha-release ; chmod +x alpha-release ; ./alpha-release
```

Or: https://labs.play-with-docker.com/ (no guacamole)

``` bash
curl -sLkO https://github.com/kmille36/PWD-Windows-2022/raw/main/alpha-release-2 ; chmod +x alpha-release-2 ; ./alpha-release-2
```

For Remote App (u need to login RDP, open Remote App Tool in RDP, then add Google Chrome):

OPTIONAL (DO IT ONCE): Disable RDP Warning command and ask for password (for easier connection):

``` powershell
reg add "HKEY_CURRENT_USER\Software\Microsoft\Terminal Server Client" /v "AuthenticationLevelOverride" /t "REG_DWORD" /d 0 /f
reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows NT\Terminal Services" /v "fPromptForPassword" /t "REG_DWORD" /d 0 /f
```

Type your RDP IP when prompted:

``` powershell
$IP = Read-Host -Prompt 'Input your RDP IP' ; iwr -uri https://github.com/kmille36/PWD-Windows-2022/raw/main/GoogleChrome.rdp -OutFile ./GoogleChrome.rdp -UseBasicParsing -UseDefaultCredentials ; ((GC -path GoogleChrome.rdp -Raw) -replace 'APPIP', $IP) | Set-Content -Path GoogleChrome.rdp ; cmdkey /generic:"$IP" /user:"azureuser" /pass:"WindowsPassword@001" ; mstsc GoogleChrome.rdp
```
1H: https://bit.ly/3wDhsRd

Login: https://microsoft.com/devicelogin

In PWD, Click OPEN PORT the type 8080 and press OK (or connect rdp using ip). Enjoy! (U can close PWD tab after done!).

# IF IT GOT ANY ERROR, CLOSE PWD SESSION AND START AGAIN #

(guacamole: azure/azure | RDP: azureuser/WindowsPassword@001 )
