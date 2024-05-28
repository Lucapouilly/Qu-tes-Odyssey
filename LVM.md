## Ajout du PV à debian-vg
  
```pvcreate /dev/nvme0n2```
![](https://github.com/Lucapouilly/Quetes-Odyssey/blob/main/Ressources/lvm/pvs%201.png)
  
## Ajouter le nouveau PV au VG existant
  
```vgextend debian-vg /dev/nvme0n2```
![](https://github.com/Lucapouilly/Quetes-Odyssey/blob/main/Ressources/lvm/vgs%201.png)
  
## Création de la snapshot
  
```lvcreate --size 5G --snapchot --name home-snap /dev/debian-vg/home```
![](https://github.com/Lucapouilly/Quetes-Odyssey/blob/main/Ressources/lvm/lvs%201.png)
  
## Création popint de montage et montage 
  
```mkdir /home-snap```
```mount /dev/debian-vg/home-snap /home-snap```
  
## Vérification snapchot
  
![](https://github.com/Lucapouilly/Quetes-Odyssey/blob/main/Ressources/lvm/verif%20snap.png)
  
## Démontage snapchot
  
```umount /home-snap```
  
## Suppression snapchot
  
```lvremove /dev/debian-vg/home-snap```
  
## Vérification de l'état des LV apres suppréssion de la snapchot
  
```lvs```
![](https://github.com/Lucapouilly/Quetes-Odyssey/blob/main/Ressources/lvm/Capture%20d%E2%80%99e%CC%81cran%202024-05-28%20a%CC%80%2010.39.39.png)
