find / -perm -u=s -type f 2>/dev/null
find / -perm -o=x -type f 2>/dev/null
find / -writable -type f 2>/dev/null

openssl passwd -1


