### PERMISSÕES EM ARQUIVOS
~~~
find / -perm -u=s -type f 2>/dev/null
~~~
~~~
find / -perm -o=x -type f 2>/dev/null
~~~
~~~
find / -writable -type f 2>/dev/null
~~~

### GERAR SENHAS PADRÃO PASSWD DO LINUX

Com o openssl podemos fazer mais coisas do que gerar hashes.

openssl passwd {algo} {password}
~~~
openssl passwd -1
~~~

