# grab_beacon_config
![Screenshot](https://github.com/whickey-r7/grab_beacon_config/blob/main/Screen%20Shot%202020-11-23%20at%2011.53.15%20AM.png)


## download grab_beacon_config.nes

`sudo wget -P /usr/local/share/nmap/scripts https://raw.githubusercontent.com/whickey-r7/grab_beacon_config/main/grab_beacon_config.nse`

## python demo

```
import random


def generate_checksum(input):
    trial = ""
    total = 0
    i = 1
    while (total != input):
        total = 0
        trial = ''.join(
            random.choice("abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ1234567890") for i in range(4))
        for i in range(4):
            total = (total + ord(trial[i: i + 1])) % 256
            i = i + 1
    return "/" + trial


uri_x86 = generate_checksum(92)
uri_x64 = generate_checksum(93)
url = "https://172.16.242.1/"
print("[+] uri_x86= " + url + uri_x86)
print("[+] uri_x64= " + url + uri_x64)

```

#### python console

```
[+] uri_x86= https://172.16.242.1//Jq1p
[+] uri_x64= https://172.16.242.1//UENu
```

