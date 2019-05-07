## Terminal

### SSH

// log in
```
ssh root@
```

//Show privatekey
```
cat ~/.ssh/id_rsa
```

// Show pub key
```
cat ~/.ssh/id_rsa.pub
```

// Copy to server
```
ssh-copy-id -i /Users/jpthor/.ssh/<key> root@
```

// Edit files
```
vi /etc/ssh/sshd_config
:wq		// write quit
:q! 		// exit
service sshd reload
```


// script to remove password
only allow key based logins
```
sed -n 'H;${x;s/\#PasswordAuthentication yes/PasswordAuthentication no/;p;}' /etc/ssh/
chmod 777 sshd_config
sshd_config > tmp_sshd_config
cat tmp_sshd_config > /etc/ssh/sshd_config
rm tmp_sshd_config
```

Users
```
adduser snode
usermod -aG sudo snode
mkdir /home/snode/.ssh
cp -rf /root/.ssh/* /home/snode/.ssh/
chown -R snode:snode /home/snode/.ssh
```
```
pkill -9 -f <processID>
-or-
kill <ID>
```


HomeBrew
```
// clean install - Mac
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
// linus install
sh -c "$(curl -fsSL https://raw.githubusercontent.com/Linuxbrew/install/master/install.sh)"
```

// essentials
```
sudo apt-get install build-essential curl file git
```
