# PSIL – Phase 1 – Jour 1

## Module : Introduction à la Virtualisation

 

## Objectifs

À la fin de cette séance, je devais être capable de :

- Comprendre la virtualisation.
- Comprendre le rôle d'un hyperviseur.
- Différencier un hyperviseur de type 1 et de type 2.
- Expliquer pourquoi VirtualBox est utilisé dans le PSIL.
- Comprendre les avantages et les limites de la virtualisation.

---

# Qu'est-ce que la virtualisation ?

La virtualisation est une technologie permettant d'exécuter plusieurs machines virtuelles sur un seul ordinateur physique.

Chaque machine virtuelle dispose de ses propres ressources virtuelles (CPU, RAM, disque, carte réseau) tout en partageant les ressources du PC hôte.

---

# Pourquoi virtualiser ?

La virtualisation permet :

- d'économiser du matériel ;
- de réduire les coûts ;
- de faciliter les tests ;
- d'améliorer la maintenance ;
- d'isoler les services ;
- de créer rapidement de nouveaux serveurs.

---

# Les limites

La virtualisation dépend des ressources disponibles :

- processeur ;
- mémoire RAM ;
- stockage ;
- virtualisation matérielle (Intel VT-x / AMD-V).



# Les hyperviseurs

## Hyperviseur de type 1

Fonctionne directement sur le matériel.

Exemples :

- VMware ESXi
- Hyper-V Server
- Proxmox VE



## Hyperviseur de type 2

Fonctionne au-dessus d'un système d'exploitation.

Exemples :

- Oracle VirtualBox
- VMware Workstation

Le PSIL utilise VirtualBox.

---

# Pourquoi VirtualBox ?

- Gratuit
- Stable
- Facile à utiliser
- Suffisant pour un laboratoire personnel



# Configuration du PC hôte

- OS : Windows 10 Pro
- CPU : Intel Core i5-6300U
- RAM : 16 Go
- Stockage : SSD 256 Go
- Virtualisation : Activée

---

# Ce que j'ai appris

- Une entreprise moderne utilise généralement la virtualisation.
- Les rôles importants sont répartis sur plusieurs machines virtuelles.
- La séparation des services améliore la maintenance, la sécurité et la disponibilité.
- Le PC physique est appelé **Host**.
- Les machines virtuelles sont appelées **Guests**.



# Questions de réflexion

Pourquoi ne pas installer tous les services sur une seule machine virtuelle ?

Réponse :

Séparer les services facilite la maintenance, améliore la sécurité, permet d'allouer les ressources de manière plus adaptée et limite l'impact d'une panne. Si une machine virtuelle rencontre un problème, les autres services continuent de fonctionner.



# Conclusion

Cette première journée a permis de comprendre les bases de la virtualisation, indispensable pour construire le laboratoire PSIL.
