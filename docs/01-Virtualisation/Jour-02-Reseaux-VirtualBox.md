# PSIL – Phase 1 – Jour 2

# 🌐 Les réseaux VirtualBox

---

# 📖 Prérequis

Avant cette séance, il est recommandé de connaître :

- Les bases de la virtualisation
- Le rôle d'une machine virtuelle
- Le fonctionnement de VirtualBox

---

# 🎯 Objectifs

À la fin de cette séance, je dois être capable de :

- Comprendre le fonctionnement d'une carte réseau virtuelle.
- Identifier les différents modes réseau de VirtualBox.
- Choisir le mode réseau adapté selon un besoin.
- Comprendre le rôle d'une passerelle (Gateway).
- Comprendre l'architecture réseau qui sera utilisée dans le laboratoire PSIL.

---

# 📚 Partie théorique

## La carte réseau virtuelle

Chaque machine virtuelle possède une ou plusieurs cartes réseau virtuelles (Network Interface Card - NIC).

Ces cartes permettent à la machine virtuelle de communiquer avec :

- le système hôte ;
- les autres machines virtuelles ;
- Internet.

---

## Les différents modes réseau VirtualBox

### NAT (Network Address Translation)

Le mode NAT permet à une machine virtuelle d'accéder à Internet en utilisant la connexion du système hôte.

Caractéristiques :

- Accès à Internet.
- Configuration automatique.
- Les autres machines du réseau ne peuvent pas accéder directement à la VM.

Utilisation :

- Installation des systèmes.
- Téléchargement des mises à jour.
- Navigation Internet.

---

### NAT Network

Le mode NAT Network permet :

- aux machines virtuelles de communiquer entre elles ;
- tout en conservant un accès à Internet.

Il est adapté aux petits laboratoires nécessitant Internet.

---

### Bridged Adapter

La machine virtuelle est directement connectée au réseau physique.

Elle reçoit une adresse IP provenant du routeur comme un ordinateur réel.

Avantages :

- Communication avec tous les équipements du réseau.

Inconvénients :

- La machine virtuelle est exposée au réseau physique.

---

### Host-Only Adapter

Le mode Host-Only crée un réseau privé entre :

- le système hôte ;
- les machines virtuelles.

Les machines virtuelles peuvent communiquer entre elles mais ne disposent pas d'un accès Internet.

Ce mode est particulièrement adapté aux laboratoires.

---

### Internal Network

Le mode Internal Network isole totalement les machines virtuelles.

Les VM peuvent communiquer uniquement entre elles.

Ni le système hôte ni Internet ne sont accessibles.

Ce mode est utilisé pour des laboratoires très isolés ou des tests de cybersécurité.

---

# Le rôle de pfSense

Dans le laboratoire PSIL, pfSense jouera le rôle de :

- passerelle (Gateway) ;
- pare-feu (Firewall) ;
- routeur.

Il permettra aux machines du laboratoire d'accéder à Internet de manière contrôlée.

---

# WAN et LAN

Le pare-feu possède deux interfaces réseau.

## WAN

Le WAN représente le réseau externe.

Dans notre laboratoire, le WAN sera connecté au NAT de VirtualBox afin d'obtenir un accès à Internet.

## LAN

Le LAN représente le réseau interne de l'entreprise.

Toutes les machines virtuelles communiqueront sur ce réseau.

---

# La passerelle (Default Gateway)

Une passerelle est l'équipement qui permet à une machine de communiquer avec des réseaux extérieurs.

Dans le PSIL, la passerelle sera pfSense.

Toutes les machines utiliseront l'adresse IP LAN de pfSense comme passerelle par défaut.

---

# Architecture prévue

```

Internet
│
Box Internet
│
NAT VirtualBox
│
pfSense (WAN)
│
pfSense (LAN)
│
├── DC01
├── Ubuntu
├── Windows Client
└── Kali Linux

```

---

# 🛠️ Mise en pratique

Au cours de cette séance :

- Étude des différents modes réseau VirtualBox.
- Analyse de leurs avantages et inconvénients.
- Compréhension du rôle du pare-feu pfSense.
- Compréhension du rôle de la passerelle.
- Préparation de l'architecture réseau du laboratoire.

---

# ✅ Résultat obtenu

À la fin de cette séance, je suis capable de :

- choisir un mode réseau VirtualBox selon le contexte ;
- expliquer le rôle de NAT, Host-Only et Bridged ;
- comprendre pourquoi pfSense possède deux cartes réseau (WAN et LAN) ;
- expliquer le rôle d'une passerelle dans une infrastructure.

---

# 📝 Ce qu'il faut retenir

- Une machine virtuelle possède une ou plusieurs cartes réseau.
- Le mode NAT permet un accès simple à Internet.
- Le mode Host-Only est idéal pour un laboratoire.
- Le mode Bridged connecte directement la VM au réseau physique.
- Le pare-feu pfSense contrôle les communications entre le réseau interne et Internet.
- Toutes les machines du laboratoire utiliseront pfSense comme passerelle.

---

# 📌 Ressources complémentaires

- Documentation Oracle VirtualBox
- Documentation pfSense
- Documentation Cisco Networking Academy

---

# 💡 Réflexion personnelle

Cette séance m'a permis de comprendre que la conception d'un réseau est une étape essentielle avant le déploiement des machines virtuelles.

J'ai également compris que le choix du mode réseau influence directement la sécurité, l'isolation et le fonctionnement du laboratoire.
