### Notes

- [IP sweep](#ip-sweep)
- [Mass Lock](#mass-lock)

## IP Sweep
```
#!/bin/bash

if [ "$1" == " " ]
then
echo "Your for an IP address!"
echo "Syntax: ./script.sh 192.168.1"

else
for ip in 'seq 1 254' ; do
ping -c 1 $1.$ip | grep "64 bytes" | cit -d " " -f 4 | tr -d ":" &
done
fi

```

## Mass lock

```
#!/bin/bash

<!-Read IP addresses from a file->
ips_file="ips.txt"
ips=()

while read -r ip; do
  ips+=("$ip")
done < "$ips_file"

<!- Lock the screen on each system ->
for system in "${ips[@]}"; do
    ssh root@$system "xscreensaver-command -lock"
done
```