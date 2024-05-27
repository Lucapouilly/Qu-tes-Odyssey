## Creation partition disque sda,sdb et sdc, choix type RAID

```cfdisk /dev/sda```   
```cfdifk /dev/sdb```
    
## Création du RAID
    
```sudo mdadm --create /dev/md0 --level 1 --raid-devices 2 /dev/sda1 /dev/sdb1```
    
## Vérification de l'etat du RAID
    
![](https://github.com/Lucapouilly/Quetes-Odyssey/blob/main/Ressources/Capture%20d%E2%80%99e%CC%81cran%202024-05-27%20a%CC%80%2018.18.48.png)
    
## Formatage volume RAID
    
```sudo mkfs.ext4 /dev/md0 -L "PersonalData"```
    
## Création point de montage/montage
    
```sudo mkdir /home/wilder/Data-RAID1 -p```   
```sudo mount /dev/md0 /home/wilder/Data-RAID1/```
    
## Ajout du point de monatge au démarage dans le fichier ```/etc/fstab/```
    
```/dev/md0 /home/wilder1/Data-RAID1 ext4 nofail 0 0```
    
## Vérrouillage de la partition RAID
    
```ARRAY /dev/md0 metadata=1.2 name=glpi-server:0 UUID=c8ac8bd1:890768a9:6574eb8d:8ea08c09```
    
## Simulation panne
    
- Marque le disue comme déffaillant  
```sudo mdadm --manage /dev/md0 --fail /dev/sdb1``` 
- retire le disque à chaud    
```sudo mdadm --manage /dev/md0 --remove /dev/sdb1```
    
![](https://github.com/Lucapouilly/Quetes-Odyssey/blob/main/Ressources/mise%20en%20panne%20raid.png)

## Ajout du disque sdc au RAID
   
``` sudo mdadm --manage /dev/md0 --add /dev/sdc1```
    
## Vérification de la reconstruction
![](https://github.com/Lucapouilly/Quetes-Odyssey/blob/main/Ressources/reconstruction.png)
    
![](https://github.com/Lucapouilly/Quetes-Odyssey/blob/main/Ressources/verif%20final%20raid%201.png)
    

# Création du RAID 5
    
```sudo mdadm --create /dev/md1 --level 5 --raid-devices 4 /dev/sdd1 /dev/sde1 /dev/sdf1 /dev/sdg1```

## Formatage et volume RAID 5
    
```sudo mkfs.ext4 /dev/md1 -L "Archives-DATA"```
    
## Création point de montage et montages du volume RAID
    
```sudo mkdir /home/wilder1/Archives-RAID5 -p```
```sudo mount /dev/md1 /home/wilder/Data-RAID5/```
   
## Vérrouillage nom de la paartition RAID
    
```ARRAY /dev/md1 metadata=1.2 name=glpi-server:0 UUID=7a14947c:f0fbff65:b663684d:fceada09```
    
## Vérification de l'etat du RAID5

![](https://github.com/Lucapouilly/Quetes-Odyssey/blob/main/Ressources/verif%20raid%205.png)



