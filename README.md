 ## Mise en oeuvre d'un environnement d'automatisation avec Ansible
 
 Déployons trois VMs pour la mise en place de cette automatisation :
 - La première machine qui sera un système Centos, servira de noeud master, nous l'appellerons binate
 - Les deux autres (une qui sera un système Centos, et l'autre un système Ubuntu) servirons de noeuds cibles, nous les appelerons respectivement aliyou1 et aliyou2:
 
<img src="https://raw.githubusercontent.com/abiForSofteam/ANSIBLE/main/VMs.png" />

Les adresses ip que j'ai attribuées à chacune des machines sont les suivantes:
binate : 912.168.56.10
aliyou1 : 912.168.56.11
aliyou2 : 912.168.56.12




### Installation et configuration de Ansible sur la VM binate

ILLUSTRATION
