### Installation serveur DHCP


# configuration DHCP
![](https://github.com/Lucapouilly/Quetes-Odyssey/blob/main/DHCP%20linux/ConfigueDHCP.png)

# adressage IP fixe du client
![](https://github.com/Lucapouilly/Quetes-Odyssey/blob/main/DHCP%20linux/IPfixeclient.png)

# modification interface par défault
édition du fichier isc-dhcp-server

INTERFACEv4="enp0s3"

# adressage ip du serveur

ifconfig enp0s3 172.20.0.1

# ajout des modifications au fichier resolv
![](https://github.com/Lucapouilly/Quetes-Odyssey/blob/main/DHCP%20linux/fichier-resolv.conf.png)

# vérification status DHCP
![](https://github.com/Lucapouilly/Quetes-Odyssey/blob/main/DHCP%20linux/verifDHCP.png)

# vérification adresse ip client
![](https://github.com/Lucapouilly/Quetes-Odyssey/blob/main/DHCP%20linux/verif%20ip.png)


