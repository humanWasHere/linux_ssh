# Configuration SSH Linux

## Commandes pour créer et utiliser des clés SSH sur Linux

### Générer les clés
```ssh-keygen```  
On peut ajouter un drapeau comme à la ligne suivante  
```ssh-keygen -b 4096```  

Sélectionner où l'on veut stocker la pair de clé RSA

### Copier la l'ID de clé sur le serveur
Adapter le format suivant  
```ssh-copy-id username@remote_host```

### Se connecter en ssh
```ssh username@remote_host```

### Retirer l'authentification par mdp
```sudo nano /etc/ssh/sshd_config```  
Vérifier que la ligne suivante existe et n'est pas commentée  
```PasswordAuthentication no```  
Puis relancer ssh  
```sudo systemctl restart ssh```  
Se reconnecter avec la commande vu précédemment

<!--https://www.digitalocean.com/community/tutorials/how-to-set-up-ssh-keys-on-ubuntu-20-04-->