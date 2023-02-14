Listar todas as regras
~~~
iptables -nL
~~~

Inserir bloqueio para que apenas algumas pessoas acesse o serviço web do servidor.

No servidor:
~~~
iptables -I INPUT 4 -p tcp -s IP --dport PORTA -j ACCEPT
~~~
