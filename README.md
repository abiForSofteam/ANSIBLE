 ## Mise en oeuvre d'un environnement d'automatisation avec Ansible
 
 Déployons trois VMs pour la mise en place de cette automatisation :
 - La première machine qui sera un système Centos, servira de noeud master, nous l'appellerons binate
 - Les deux autres (une qui sera un système Centos, et l'autre un système Ubuntu) servirons de noeuds cibles, nous les appelerons respectivement aliyou1 et aliyou2:
 
<br /><img src="https://raw.githubusercontent.com/abiForSofteam/ANSIBLE/main/VMs.png" />



### <br /><br /> Les adresses ip que j'ai attribuées à chacune des machines sont les suivantes:
<br /><br />binate  : 192.168.56.10
<br /><img src="https://raw.githubusercontent.com/abiForSofteam/ANSIBLE/main/ip_binate.png" />
<br />aliyou1 : 192.168.56.11
<br /><img src="https://raw.githubusercontent.com/abiForSofteam/ANSIBLE/main/ip_aliyou1.png" />
<br />aliyou2 : 192.168.56.12
<br /><img src="https://raw.githubusercontent.com/abiForSofteam/ANSIBLE/main/ip_aliyou2.png" />


### Installation et configuration de Ansible sur la VM binate

ILLUSTRATION
