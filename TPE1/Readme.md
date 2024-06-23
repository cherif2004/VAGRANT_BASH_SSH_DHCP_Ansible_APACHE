# Guide d'utilisation du fichier de COnfiguiration Vagrantfile

Ce projet utilise Vagrant pour créer une machine virtuelle Ubuntu Xenial 64 bits avec Docker pré-installé.

## Prérequis

- [Vagrant](https://www.vagrantup.com/downloads.html) doit être installé sur votre système.
- [VirtualBox](https://www.virtualbox.org/wiki/Downloads) (ou un autre fournisseur Vagrant) doit également être installé.

## Configuration de la machine virtuelle

Le fichier `Vagrantfile` contient la configuration de la machine virtuelle. Voici un aperçu de la configuration :

Vagrant.configure("2") do |config|

  config.vm.box = "ubuntu/xenial64"

  config.vm.provider "virtualbox" do |vb|

    vb.memory = "1024"

  end


  # Provisionnement avec un script shell pour installer Docker
  config.vm.provision "shell", inline: <<-SHELL

    sudo apt-get update
    sudo apt-get install -y docker.io
    sudo usermod -aG docker vagrant
    sudo systemctl enable docker
    sudo systemctl start docker
  SHELL
end 

 
###  Cette configuration spécifie que la machine virtuelle utilisera l'image "ubuntu/xenial64" et configurera 1024 Mo de mémoire. De plus, elle provisionnera Docker en exécutant un script shell.

**1**- **_Comment lancer la machine virtuelle_**

Il faut se positionner dans le  repertoire où se trouve le fichier de configuration Vagrantfile et saisir la commande :
  ``vagrant up --provision``
Cela va créer et provisionner la machine virtuelle selon la configuration spécifiée dans le fichier Vagrantfile.

**2**- **_Comment accéder à la machine virtuelle_**
Une fois la machine virtuelle démarrée, vous pouvez vous y connecter via SSH en utilisant la commande suivante : `` vagrant ssh``

Cela vous connectera à la machine virtuelle en utilisant les paramètres SSH définis dans le fichier Vagrantfile.

**3**- **_Comment sortir de la machine virtuelle_**

Pour quitter la session SSH et revenir à votre système hôte, vous pouvez simplement exécuter la commande `exit` dans le terminal de la machine virtuelle. 

**4**- **_Comment arrêter et fermer la machine virtuelle_**

Pour arrêter la machine virtuelle, vous pouvez exécuter la commande suivante dans le même répertoire que le fichier Vagrantfile : `vagrant halt`

Cela va arrêter la machine virtuelle de manière propre.

Si vous souhaitez supprimer complètement la machine virtuelle et libérer l'espace disque utilisé, vous pouvez utiliser la commande suivante : `vagrant destroy`


Vous serez invité à confirmer la suppression avant que la machine virtuelle ne soit complètement supprimée.
