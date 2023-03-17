<h1>IP Sweep</h1>

#!/bin/bash
<br />

if [ "$1" == "" ]
<br />
then
<br />
echo "You forgot an IP address."
<br />
echo "Syntax: ./ipsweep.sh 192.168.0"
<br />

else
<br />
for ip in 'seq 1 254' ; do
<br />
ping -c 1 $1.$ip | grep "64 bytes" | cut -d " " -f 4 | tr -d ":" &
<br />
done
<br />
fi
<br />
