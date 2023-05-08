# Configuration SSH Linux

## Commandes pour créer et utiliser des clés SSH sur Linux

On veut fermer tout le trafic entrant et autoriser le trafic sortant
On veut aussi autoriser les protocoles ssh (port 22 en tcp), http/https (ports 80/443 en tcp), dns (port 53 en udp) et dhcp (port 68 en udp)

### générer les clés
$ ```ssh-keygen```
you can add a flag like so
$ ```ssh-keygen -b 4096```

select where you want the RSA key pair to be stored

### copier la l'ID de clé sur le serveur
adapter le format suivant
$ ```ssh-copy-id username@remote_host```

### se connecter en ssh
$ ```ssh username@remote_host```

### Retirer l'authentification par mdp
$ ```sudo nano /etc/ssh/sshd_config```
vérifier que la ligne suivante existe et n'est pas commentée
```PasswordAuthentication no```
puis redémarer ssh
```sudo systemctl restart ssh```
se reconnecter avec la commande vu précédemment

Légende :
$ pour les commandes

<!--https://www.digitalocean.com/community/tutorials/how-to-set-up-ssh-keys-on-ubuntu-20-04-->