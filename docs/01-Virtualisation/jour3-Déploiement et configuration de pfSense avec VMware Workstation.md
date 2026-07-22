# PSIL — Phase 1 : Mise en place de l'infrastructure virtuelle

## Jour 3 — Déploiement et configuration de pfSense avec VMware Workstation

## 1. Objectif

L'objectif de cette étape est de déployer le pare-feu/routeur principal du laboratoire PSIL.

pfSense sera utilisé comme :

* pare-feu réseau ;
* routeur entre les réseaux WAN et LAN ;
* serveur DHCP pour le réseau interne ;
* point central de contrôle des communications entre les machines du laboratoire.

---

# 2. Migration de VirtualBox vers VMware Workstation

Initialement prévu sur VirtualBox, le laboratoire a été migré vers VMware Workstation 17 Pro afin d'obtenir un environnement de virtualisation plus stable pour les machines réseau.

### Raisons du changement :

* problèmes de configuration réseau rencontrés avec VirtualBox ;
* meilleure gestion des interfaces virtuelles avec VMware ;
* environnement plus adapté pour les laboratoires réseau.

---

# 3. Configuration réseau VMware

Les réseaux virtuels suivants ont été utilisés :

| Réseau VMware | Type      | Sous-réseau     | Utilisation                         |
| ------------- | --------- | --------------- | ----------------------------------- |
| VMnet8        | NAT       | 192.168.44.0/24 | Accès Internet (WAN pfSense)        |
| VMnet1        | Host-Only | 192.168.1.0/24  | Réseau interne du laboratoire (LAN) |

Architecture réseau :

```
                 Internet
                    |
                VMnet8 NAT
                    |
              pfSense WAN
                    |
              pfSense LAN
              192.168.1.1/24
                    |
                VMnet1
                    |
       --------------------------
       |          |             |
      DC01     Ubuntu          Kali
```

---

# 4. Création de la VM pfSense

## Caractéristiques de la machine virtuelle

| Paramètre   | Valeur                                   |
| ----------- | ---------------------------------------- |
| Nom         | PSIL-pfSense                             |
| Hyperviseur | VMware Workstation 17 Pro                |
| Système     | FreeBSD 64 bits                          |
| RAM         | 4 Go                                     |
| Processeur  | 2 vCPU                                   |
| Disque      | 20 Go                                    |
| ISO         | netgate-installer-v1.2-RELEASE-amd64.iso |

---

# 5. Configuration des interfaces réseau

pfSense a détecté deux interfaces :

```
em0 — 00:0c:29:1e:50:bd
em1 — 00:0c:29:1e:50:c7
```

Configuration appliquée :

| Interface pfSense | Rôle | Réseau VMware    |
| ----------------- | ---- | ---------------- |
| em0               | WAN  | VMnet8 NAT       |
| em1               | LAN  | VMnet1 Host-Only |

---

# 6. Configuration du réseau LAN

Configuration finale :

```
Interface : LAN
Mode : Static IPv4

Adresse IP :
192.168.1.1/24
```

Le service DHCP pfSense est activé :

```
DHCP : Enabled

Plage DHCP :
192.168.1.100 - 192.168.1.199
```

Cette plage permettra :

* l'attribution automatique d'adresses aux clients ;
* de conserver les adresses basses pour les serveurs avec IP fixes.

Exemple :

```
192.168.1.10  → DC01
192.168.1.20  → Ubuntu Server
192.168.1.30  → autres services
```

---

# 7. Résultat du Jour 3

## Composants terminés

✅ VMware Workstation configuré
✅ Réseaux virtuels préparés
✅ VM pfSense créée
✅ Interfaces WAN/LAN configurées
✅ LAN configuré en 192.168.1.0/24
✅ DHCP interne activé

---

# 8. Prochaine étape

## Phase 1 — Jour 4

Déploiement du serveur Windows :

* création de la VM PSIL-DC01 ;
* installation Windows Server ;
* configuration IP fixe ;
* installation Active Directory Domain Services ;
* installation DNS ;
* création du domaine interne PSIL.
