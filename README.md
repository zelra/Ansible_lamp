# Déploiement rapide de serveur LAMP avec Ansible
-------------------------------------------

Ce "Playbook" est composé de 3 roles : "common", "web" et "db"

- "common" permet d'installer les outils de base sur la nouvelle machine
- "web" permet l'installation et la configuration d'Apache2 et de PHP
- "db"(database) permet l'installation et la configuration de MySQL 

Ce playbook a été testé sur deux VMs : une Ubuntu (maitre) et une Debian (esclave).
Il est possible de rajouter une infinité d'esclaves en editant le fichier "hosts" à la racine de ce playbook.
Les machines sont rajoutées comme ça :

	[type_1]
	ma_machine_1

	[type 2]
	ma_machine_2

Il possible d'appliquer des roles qu'à certains types de machines. Il faut éditer le fichier "server.yml" et remplacer "hosts: all" par "hosts: type_x".

Avant de lancer l'installation, vérifier que vous avez bien configuré la connexion ssh par clef entre les 2 machines.
Pour lancer l'installation, tapez la commande suivante:

	ansible-playbook -i hosts server.yml

Pour vérifier que l'installation a été fait correctement, tapez sur l'URL de votre navigateur :

	 http://ip_de_nouvelle_machine/index.php

Si ça a fonctionné, un "Hello World" devrait apparaitre.
 

