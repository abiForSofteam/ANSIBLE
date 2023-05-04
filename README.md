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
<br />La commande suivante permet de l'éditer : **sudo vi /etc/hosts**
<br /><img src="https://raw.githubusercontent.com/abiForSofteam/ANSIBLE/main/hosts.png" />

Après la mise en place de cette configuration, les différentes VMs répondent désormais
<br /><img src="https://raw.githubusercontent.com/abiForSofteam/ANSIBLE/main/ping_aliyou1_aliyou2.png" />

<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
	<key>Ansi 0 Color</key>
	<dict>
		<key>Blue Component</key>
		<real>0.0</real>
		<key>Green Component</key>
		<real>0.0</real>
		<key>Red Component</key>
		<real>0.0</real>
	</dict>
	<key>Ansi 1 Color</key>
	<dict>
		<key>Blue Component</key>
		<real>0.0</real>
		<key>Green Component</key>
		<real>0.20898362994194031</real>
		<key>Red Component</key>
		<real>1</real>
	</dict>
	<key>Ansi 10 Color</key>
	<dict>
		<key>Blue Component</key>
		<real>0.0</real>
		<key>Green Component</key>
		<real>1</real>
		<key>Red Component</key>
		<real>0.0</real>
	</dict>
	<key>Ansi 11 Color</key>
	<dict>
		<key>Blue Component</key>
		<real>0.30980390310287476</real>
		<key>Green Component</key>
		<real>0.91372549533843994</real>
		<key>Red Component</key>
		<real>0.98823529481887817</real>
	</dict>
	<key>Ansi 12 Color</key>
	<dict>
		<key>Blue Component</key>
		<real>0.81176471710205078</real>
		<key>Green Component</key>
		<real>0.62352937459945679</real>
		<key>Red Component</key>
		<real>0.44705879688262939</real>
	</dict>
	<key>Ansi 13 Color</key>
	<dict>
		<key>Blue Component</key>
		<real>0.65882349014282227</real>
		<key>Green Component</key>
		<real>0.49803918600082397</real>
		<key>Red Component</key>
		<real>0.67843139171600342</real>
	</dict>
	<key>Ansi 14 Color</key>
	<dict>
		<key>Blue Component</key>
		<real>0.88627451658248901</real>
		<key>Green Component</key>
		<real>0.88627451658248901</real>
		<key>Red Component</key>
		<real>0.2039216011762619</real>
	</dict>
	<key>Ansi 15 Color</key>
	<dict>
		<key>Blue Component</key>
		<real>0.92549020051956177</real>
		<key>Green Component</key>
		<real>0.93333327770233154</real>
		<key>Red Component</key>
		<real>0.93333327770233154</real>
	</dict>
	<key>Ansi 2 Color</key>
	<dict>
		<key>Blue Component</key>
		<real>0.0</real>
		<key>Green Component</key>
		<real>1</real>
		<key>Red Component</key>
		<real>0.0</real>
	</dict>
	<key>Ansi 3 Color</key>
	<dict>
		<key>Blue Component</key>
		<real>0.0</real>
		<key>Green Component</key>
		<real>0.75023084878921509</real>
		<key>Red Component</key>
		<real>1</real>
	</dict>
	<key>Ansi 4 Color</key>
	<dict>
		<key>Blue Component</key>
		<real>0.51036852598190308</real>
		<key>Green Component</key>
		<real>0.55560648441314697</real>
		<key>Red Component</key>
		<real>0.0</real>
	</dict>
	<key>Ansi 5 Color</key>
	<dict>
		<key>Blue Component</key>
		<real>0.48235291242599487</real>
		<key>Green Component</key>
		<real>0.31372550129890442</real>
		<key>Red Component</key>
		<real>0.45882350206375122</real>
	</dict>
	<key>Ansi 6 Color</key>
	<dict>
		<key>Blue Component</key>
		<real>0.60392159223556519</real>
		<key>Green Component</key>
		<real>0.59607851505279541</real>
		<key>Red Component</key>
		<real>0.023529410362243652</real>
	</dict>
	<key>Ansi 7 Color</key>
	<dict>
		<key>Blue Component</key>
		<real>0.81176471710205078</real>
		<key>Green Component</key>
		<real>0.84313732385635376</real>
		<key>Red Component</key>
		<real>0.82745099067687988</real>
	</dict>
	<key>Ansi 8 Color</key>
	<dict>
		<key>Blue Component</key>
		<real>0.32549020648002625</real>
		<key>Green Component</key>
		<real>0.34117650985717773</real>
		<key>Red Component</key>
		<real>0.33333331346511841</real>
	</dict>
	<key>Ansi 9 Color</key>
	<dict>
		<key>Blue Component</key>
		<real>0.0</real>
		<key>Green Component</key>
		<real>0.0</real>
		<key>Red Component</key>
		<real>1</real>
	</dict>
	<key>Background Color</key>
	<dict>
		<key>Blue Component</key>
		<real>0.13274481892585754</real>
		<key>Green Component</key>
		<real>0.11682706326246262</real>
		<key>Red Component</key>
		<real>0.11773887276649475</real>
	</dict>
	<key>Bold Color</key>
	<dict>
		<key>Blue Component</key>
		<real>1</real>
		<key>Green Component</key>
		<real>1</real>
		<key>Red Component</key>
		<real>1</real>
	</dict>
	<key>Cursor Color</key>
	<dict>
		<key>Blue Component</key>
		<real>0.0</real>
		<key>Green Component</key>
		<real>0.75023084878921509</real>
		<key>Red Component</key>
		<real>1</real>
	</dict>
	<key>Cursor Text Color</key>
	<dict>
		<key>Blue Component</key>
		<real>0.99983131885528564</real>
		<key>Green Component</key>
		<real>1</real>
		<key>Red Component</key>
		<real>0.99989032745361328</real>
	</dict>
	<key>Foreground Color</key>
	<dict>
		<key>Blue Component</key>
		<real>0.80426216125488281</real>
		<key>Green Component</key>
		<real>0.80443644523620605</real>
		<key>Red Component</key>
		<real>0.80430960655212402</real>
	</dict>
	<key>Selected Text Color</key>
	<dict>
		<key>Blue Component</key>
		<real>0.0</real>
		<key>Green Component</key>
		<real>0.0</real>
		<key>Red Component</key>
		<real>0.0</real>
	</dict>
	<key>Selection Color</key>
	<dict>
		<key>Blue Component</key>
		<real>1</real>
		<key>Green Component</key>
		<real>0.8353000283241272</real>
		<key>Red Component</key>
		<real>0.70980000495910645</real>
	</dict>
</dict>
</plist>
