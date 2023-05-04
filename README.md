 ## Mise en oeuvre d'un environnement d'automatisation avec Ansible
 
 ### <br /><br /> Déployons trois VMs pour la mise en place de cette automatisation :
 - La première machine qui sera un système Centos, servira de noeud master, nous l'appellerons binate
 - Les deux autres (une qui sera un système Centos, et l'autre un système Ubuntu) servirons de noeuds cibles, nous les appelerons respectivement aliyou1 et aliyou2:
 
<br /><img src="https://raw.githubusercontent.com/abiForSofteam/ANSIBLE/main/VMs.png" />

### <br /><br /> Les adresses ip que j'ai attribuées à chacune des machines sont les suivantes:
<br />binate  : 192.168.56.10
<br /><img src="https://raw.githubusercontent.com/abiForSofteam/ANSIBLE/main/ip_binate.png" />
<br /><br />aliyou1 : 192.168.56.11
<br /><img src="https://raw.githubusercontent.com/abiForSofteam/ANSIBLE/main/ip_aliyou1.png" />
<br /><br />aliyou2 : 192.168.56.12
<br /><img src="https://raw.githubusercontent.com/abiForSofteam/ANSIBLE/main/ip_aliyou2.png" />

### <br /><br /> Les informations système des différentes machines sont les suivantes:


### Installation et configuration de Ansible sur la VM binate
ILLUSTRATION

### Mise en place de la résolution de nom sur les différentes machines
En effet, avant la mise en place de cette configuration, si à partir de la VM binate je fais : **ping aliyou1** ou **ping aliyou2** , un message me dira que aliyou1 n'est pas reconnu, aliyou2 non plus; idem si on lance cette même commande à l'endroit de la VM binate, et depuis aliyou1 et aliyou2.
<br /><img src="https://raw.githubusercontent.com/abiForSofteam/ANSIBLE/main/ping_aliyou1_aliyou2_2.png" />

<br />Pourtant, aliyou1 et aliyou2 répondront si je lance la commande en prenant en compte leur adresse ip au lieu de leur nom (**ping 192.168.56.11**,  **ping 192.168.56.12**)

La résolution de nom permet à chaque machine de reconnaître l'autre à partir de son nom, il n'est plus nécessaire de lui spécifier son adressse ip.

Cette configuration se fait **pour chaque VM** dans le fichier suivant : **/etc/hosts**
La commande suivante permet de l'éditer : **sudo vi /etc/hosts**
<br /><img src="https://raw.githubusercontent.com/abiForSofteam/ANSIBLE/main/hosts.png" />

Après la mise en place de cette configuration, les différentes VMs répondent désormais
<br /><img src="https://raw.githubusercontent.com/abiForSofteam/ANSIBLE/main/ping_aliyou1_aliyou2.png" />

