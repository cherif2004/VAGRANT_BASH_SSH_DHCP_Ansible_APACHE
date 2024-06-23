# TPE N°1: Infrastructure as Code (IaC) avec Vagrant
**Date:** *Mercredi 28 mars 2024*

1. Écrivez un `Vagrantfile` qui définit la configuration permettant de créer une VM sous VirtualBox et d’y installer Docker automatiquement.
2. Fournir une documentation uniquement au format Markdown (`.md`).

**Format de l’unique fichier à fournir:** `TPE-1-<matricule>-<nom>.tar.gz`

**Deadline:** *Vendredi 05 Avril 2024 à 00h00*

---

# TPE N°2 : Consolider la compréhension des concepts fondamentaux des protocoles SSH et DHCP.
**Date:** *Mercredi 03 Avril 2024*

1. Quels sont les éléments clés qui caractérisent un protocole réseau ?
2. Identifiez et expliquez les différents types de messages utilisés dans le protocole SSH.
3. Faites de même pour le protocole DHCP.
4. Quels sont les formats de chaque type de message pour les protocoles DHCP et SSH, respectivement ?
5. Décrivez l'ordre d'envoi des messages lors de l'établissement d'une connexion SSH.
6. Décrivez l'ordre d'envoi des messages pour l'obtention d'une adresse IP à partir d'un serveur DHCP.
7. Quelles sont les actions possibles après la réception de chaque type de message pour les protocoles DHCP et SSH, respectivement ?

*NB: Citez des sources fiables*

**Format de l’unique fichier à fournir:** `TPE-2-<matricule>-<nom>.pdf` (maximum 4 pages)

**Deadline:** *Mercredi 10 Avril 2024 à 07h00*

---

# TPE N°3: IaC avec Vagrant et Ansible
**Date:** *Samedi 06 Avril 2024*

1. Écrivez un `Vagrantfile` qui définit la configuration permettant de créer une VM sous VirtualBox à partir des informations suivantes :
   - Image de base: `generic/ubuntu2204`
   - CPU: 1 et RAM: 1Go
   - Définir une adresse IP et expliquez votre choix
   - Hostname: `dhcp-server`

2. Quelle est la commande permettant d'installer un serveur DHCP ? Quel est le chemin de son fichier de configuration et celui de son fichier de journalisation ?

3. Documentez-vous sur Ansible et son fonctionnement
   - Configurez votre machine hôte pour qu’il joue le rôle du Node Manager Ansible et `dhcp-server` comme node.
   - Écrivez le fichier `inventaire.ini`.
   - Testez votre configuration à l’aide du module ping d’Ansible.

4. Écrivez et testez un playbook Ansible pour installer et configurer le serveur DHCP sur `dhcp-server`.
   - Paramètres du serveur DHCP: adresse réseau, la plage d'adresses IP, le masque de sous-réseau
   - Configurez 2 hôtes fixes.

5. Décrivez un scénario de test et testez votre serveur DHCP.
6. Modifier le `Vagrantfile` pour qu’il exécute automatiquement le playbook Ansible pour installer et configurer le serveur DHCP.
7. Fournir une documentation uniquement au format Markdown (`.md`).

**Ressource:**
- [Introduction à Ansible](https://blog.stephane-robert.info/docs/infra-as-code/gestion-de-configuration/ansible/introduction/)

**Format de l’unique fichier à fournir:** `TPE-3-<matricule>-<nom>.tar.gz`

**Deadline:** *Vendredi 12 Avril 2024 à 00h00*

[Introduction à Ansible](https://blog.stephane-robert.info/docs/infra-as-code/gestion-de-configuration/ansible/introduction/)
