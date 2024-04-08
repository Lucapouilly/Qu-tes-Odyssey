### Découpage Symétrique

172.16.1.0/24

je prend la puissance de 2 supérieur à 50: 2^6=64-2=60 62 adresse par sous reseau

CIDR on fait 32-6=26
CIDR /26

|                        | adresse reseau | début de plage | fin de plage | adresse broadcast |
|------------------------|----------------|----------------|--------------|-------------------|
| pole informatiques     | 172.16.1.0/26  | 172.16.1.1     | 172.16.1.62  | 172.16.1.63       |
| poles développement    | 172.16.1.64    | 172.16.1.65    | 172.16.1.126 | 172.16.1.127      |
| pole administratif     | 172.16.1.128   | 172.16.1.129   | 172.16.1.191 | 172.16.1.191      |
| pole technicien        | 172.16.1.192   | 172.16.1.193   | 172.16.1.254 | 172.16.1.255      |

### Découpage Asymétrique

pole informatiques on fait 2^6=64 -2= 60 equipements  32-6  CIDR /26
  
pole développement on fait 2^4=16 -2= 14 équipement   32-4  CIDR /28
  
pole administratif on fait 2^5=32 -2= 30 équipements  32-5  CIDR /27
  
pole technicien on fait 2^5=32 -2= 30 équipements     32-5  CIDR /27

|                        | adresse reseau | début de plage | fin de plage | adresse broadcast |
|------------------------|----------------|----------------|--------------|-------------------|
| pole informatiques     | 172.16.1.0/26  | 172.16.1.1     | 172.16.1.62  | 172.16.1.63       |
| pole administratif     | 172.16.1.64/27 | 172.16.1.65    | 172.16.1.94  | 172.16.1.95       |
| pole technicien        | 172.16.1.96/27 | 172.16.1.97    | 172.16.1.125 | 172.16.1.126      |
| poles développement    | 172.16.1.127/28| 172.16.1.128   | 172.16.1.143 | 172.16.1.144      |

