 ## Mise en oeuvre d'un environnement d'automatisation avec Ansible
 
 Déployons trois VMs pour la mise en place de cette automatisation :
 - La première machine qui sera un système Centos, servira de noeud master, nous l'appellerons binate
 - Les deux autres (une qui sera un système Centos, et l'autre un système Ubuntu) servirons de noeuds cibles, nous les appelerons respectivement aliyou1 et aliyou2:
 
<img src="https://raw.githubusercontent.com/abiForSofteam/ANSIBLE/main/VMs.png" />

Les adresses ip que j'ai attribuées à chacune des machines sont les suivantes:


binate  : 192.168.56.10

<img src="https://raw.githubusercontent.com/abiForSofteam/ANSIBLE/main/ip_binate.png" />
aliyou1 : 192.168.56.11

<img src="https://raw.githubusercontent.com/abiForSofteam/ANSIBLE/main/ip_aliyou1.png" />
aliyou2 : 192.168.56.12

<img src="https://raw.githubusercontent.com/abiForSofteam/ANSIBLE/main/ip_aliyou2.png" />


### Installation et configuration de Ansible sur la VM binate

ILLUSTRATION
