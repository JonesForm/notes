### Notes

1: [IP sweep](#ip-sweep)

<a id="ip-sweep></a>

'''IP Sweep

#!/bin/bash

for ip in 'seq 1 254' ; do
ping -c 1 $1.$ip | grep "64 bytes" | cit -d " " -f 4 | tr -d ":" &
done

'''