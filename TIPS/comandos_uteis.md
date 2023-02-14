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

# SENHAS LINUX

### GERAR SENHAS NO PADRÃO PASSWD DO LINUX

Com o openssl podemos fazer mais coisas do que gerar hashes.

openssl passwd {algo} {password}
~~~
openssl passwd -1
~~~

### CRACKING SENHAS LINUX
Exemplo de hash de senha do Linux: $1$e7NfNpNi$A6nCwOTqrNR2oDuIKirRZ.
~~~
john -w /path/to/wordlist — format=md5crypt hashes
~~~
