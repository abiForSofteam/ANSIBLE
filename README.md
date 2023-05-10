<h1> Mise en oeuvre d'un environnement d'automatisation avec Ansible</h1>
<h3> Déployons trois VMs pour la mise en place de cette automatisation :</h3>
<ul>
 <li>La première machine qui sera un système Centos, servira de noeud master, nous l'appellerons binate</li>
 <li>Les deux autres (une qui sera un système Centos, et l'autre un système Ubuntu) servirons de noeuds cibles, nous les appelerons respectivement aliyou1 et aliyou2:</li>
 </ul>
 
<br /><img src="https://raw.githubusercontent.com/abiForSofteam/ANSIBLE/main/lesVMs.png" />

### <br /><br /> Les adresses ip que j'ai attribuées à chacune des machines sont les suivantes:
<br />binate  : 192.168.56.10
<br /><img src="https://raw.githubusercontent.com/abiForSofteam/ANSIBLE/main/ip_binate.png" />
<br /><br />aliyou1 : 192.168.56.11
<br /><img src="https://raw.githubusercontent.com/abiForSofteam/ANSIBLE/main/ip_aliyou1b.png" />
<br /><br />aliyou2 : 192.168.56.12
<br /><img src="https://raw.githubusercontent.com/abiForSofteam/ANSIBLE/main/ip_aliyou2.png" />

### <br /><br /> Les informations système des différentes machines sont les suivantes:


### Installation et configuration de Ansible sur la VM binate
Pour le système Centos, le package Ansible est disponible dans le dépôt EPEL (Extra Packages for Entreprise Linux)
La commande pour installer ce dépôt est la suivante : 
<br /> **sudo dnf install epel-release**
ILLUSTRATION

### Mise en place de la résolution de nom sur les différentes machines
En effet, avant la mise en place de cette configuration, si à partir de la VM binate je fais : **ping aliyou1** ou **ping aliyou2** , un message me dira que aliyou1 n'est pas reconnu, aliyou2 non plus; idem si on lance cette même commande à l'endroit de la VM binate, et depuis aliyou1 et aliyou2.
<br /><img src="https://raw.githubusercontent.com/abiForSofteam/ANSIBLE/main/ping_aliyou1_aliyou2_2.png" />

<br />Pourtant, aliyou1 et aliyou2 répondront si je lance la commande en prenant en compte leur adresse ip au lieu de leur nom (**ping 192.168.56.11**,  **ping 192.168.56.12**)

La résolution de nom permet à chaque machine de reconnaître l'autre à partir de son nom, il n'est plus nécessaire de lui spécifier son adressse ip.

Cette configuration se fait **pour chaque VM** dans le fichier suivant : **/etc/hosts**
<br />La commande suivante permet de l'éditer : **sudo vi /etc/hosts**
<br /><img src="https://raw.githubusercontent.com/abiForSofteam/ANSIBLE/main/hosts.png" />

Après la mise en place de cette configuration, les différentes VMs répondent désormais
<br /><img src="https://raw.githubusercontent.com/abiForSofteam/ANSIBLE/main/ping_aliyou1_aliyou2.png" />


## Configuration
<sub>Par défaut, Ansible définit son espace de travail dans /etc/ansible... (capture)
Nous pouvons changer ce comportement.
Nous allons effectivement définir notre répertoire aliyoubinate_project comme répertoire de travail.
Pour cela, nous copions le répertoire  /etc/ansible/ansible.cfg dans notre répertoire de travail aliyoubinate_project (capture)

Ansible a besoin d'identifier les ma chines cibles sur lesquels il va opérer.
Ces machines sont listées dans le fichier inventaire dont le chemin est spécifié dans le fichier de configuration que nous devons de copier dans notre fichier de configuration aliyoubinate_project; nous l'appellerons hosts.ini(capture)

Ansible a également besoin d'identifier...</sub>


<sub>La communication entre la machine master et les machines cibles se fait par le protocole SSH.
Nous devons assurer que cette communication, essentielle pour le fonctionnement de Ansible, est bien en place.
Pour cela, nous allons créer un utilisateur ansible sur les machines avec le même mot de passe de préférence.
Cette création sera faite via le compte root.
Nous préférerons une connexion par clé ssh (qui est plus sécurisée)  à une connexion par mot de passe.
Passons donc en utilisateur root : sudo -i
Puis procédons à la création des clés (privée et publique):
ssh-keygen -t rsa
...

Le chemin des clés est spécifié lors de cette création, nous en aurons besoin par la suite.</sub>
