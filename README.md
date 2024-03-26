# Configuration SSH Linux / VSCode

## Create and use SSH keys

### Generate keys
```
ssh-keygen
```  
A flag can be added
```
ssh-keygen -b 4096
```  

Select where you want your RSA key to be stored

### Copy key's ID on server
Adapt following line to your situation  
```
ssh-copy-id <username>@<remote_host>
```  
Copy public key to add to server in "autorized_keys" file.

### Connect in SSH
```
ssh username@remote_host
```

### Remove auth by password
```
sudo nano /etc/ssh/sshd_config
```  
Verify than following line exists and is not commented  
```
PasswordAuthentication no
```  
Run ssh again  
```
sudo systemctl restart ssh
```  
Reconnect in SSH (as viewed above)

<!--https://www.digitalocean.com/community/tutorials/how-to-set-up-ssh-keys-on-ubuntu-20-04-->

## SSH for VSCode
The purpose of doing a SSH here is to connect VSCode (installed in Windows env) to your Unix env.  
VSCode/Windows acts as a client, it must give its public key to the "server".  
In Windows, open a cmd/powershell and run :  
```
ssh-keygen -t rsa -b 4096
```
Let it stored in the default path and enter no passphrase.  
Then copy the RSA key in ```id_rsa.pub``` stored in ```C:\Users\<your_user_name>\.ssh```.  
Go to your Unix env under path ```/home/<your_user_name>/.ssh/``` and add your key in the ```authorized_keys``` file.  
Save it and exit (ctrl + O / ctrl + X).
