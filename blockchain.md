## Loki Dev Notes

```
./lokid --service-node
./loki-wallet-cli
set ask-password 0
print_quorum_state
```


### MAC Guide

Digital Ocean

Remove key:
```
rm ~/.loki/key
```
WALLET
```
./loki-wallet-cli  --restore-deterministic-wallet
--daemon-address doopool.xyz:22020
set_daemon doopool.xyz:22020
```

—
1. Ssh in to your service node

2. In the root directory and prior to attaching to any screens, paste the following script in and run:

```
====
#!/bin/bash
wget https://github.com/loki-project/loki/releases/download/v2.0.2/loki-linux-x64-v2.0.2.zip

sudo apt-get update

sudo apt-get upgrade

sudo apt install unzip

unzip loki-linux-x64-v2.0.2.zip
rm -f loki-linux-x64-v2.0.2.zip
cd loki-linux-x64-v2.0.2


===
```

“Do you want to continue? Y/N:” `Y`


3. Execute the following line-by-line to enter the screen running the daemon and exit the process
```
screen -ls
screen -x <lokidprocess>
exit
```


4. Paste the following script in the attached screen to remove old version and start the new version:
```
#!/bin/bash
cd ..
rm -R  loki-linux-x64-1.0.4
cd loki-linux-x64-v2.0.2
./lokid --service-node
```
*wait for uptime proof to double check ~2-10mins*

5. Safely exit screen and logout

```
ctrl-AD
Exit
```
```
sudo systemctl stop lokid.service
sudo sed -i -e 's/1.0.4/2.0.0/g' /etc/systemd/system/lokid.service
sudo systemctl daemon-reload
sudo systemctl start lokid.service
# Confirm the version. Should output: Loki 'Festive Freya' (v2.0.0-53452b9)
~/loki-linux-x64-2.0.0/lokid version
# Print your service node status.
~/loki-linux-x64-2.0.0/lokid print_sn_status
```
```
loki-wallet-cli --command "show_transfers" --wallet-file=/path/to/wallet --password 'password' | egrep '^ '| sed 's/^ //g'| sed 's/ \+/,/g' >> my_txns.csv
```


// Copying Key
```
//Exit snode
cd .. && cd .loki
sudo rm key <pw>
scp ~/.loki/key  snode@157.230.132.137:~/.loki/key
rm ~/.loki/key
```
