# 🛡️ PARE Security & Infrastructure Lab (PSIL)

> **Apprendre. Construire. Sécuriser. Documenter.**

---

# 📖 Présentation

Le **PARE Security & Infrastructure Lab (PSIL)** est un laboratoire informatique personnel conçu pour développer des compétences pratiques en administration système, réseau et cybersécurité.

L'objectif est de concevoir et d'administrer une infrastructure d'entreprise réaliste en utilisant un environnement de virtualisation professionnel.

Chaque étape du projet est documentée afin de constituer un portfolio technique démontrant les compétences acquises en infrastructure et sécurité informatique.

---

# 🎯 Objectifs du projet

* Construire une infrastructure informatique complète.
* Maîtriser la virtualisation.
* Administrer Windows Server.
* Administrer des systèmes Linux.
* Déployer Active Directory.
* Concevoir un réseau d'entreprise segmenté.
* Mettre en place un pare-feu.
* Sécuriser les systèmes.
* Déployer une solution de supervision.
* Automatiser certaines tâches d'administration.
* Documenter chaque étape du projet.

---

# 🛠️ Technologies utilisées

## Virtualisation

* VMware Workstation 17 Pro

## Systèmes

* Windows Server
* Ubuntu Server
* Kali Linux
* pfSense CE

## Administration et sécurité

* Active Directory
* DNS
* DHCP
* PowerShell
* Bash
* Python
* Wazuh
* Git
* GitHub

---

# 📅 Feuille de route

| Phase                                              | État        |
| -------------------------------------------------- | ----------- |
| Phase 0 – Cahier des charges                       | ✅ Terminée  |
| Phase 1 – Virtualisation et infrastructure de base | 🟡 En cours |
| Phase 2 – Réseau                                   | ⏳ À venir   |
| Phase 3 – Windows Server / Active Directory        | ⏳ À venir   |
| Phase 4 – Linux Server                             | ⏳ À venir   |
| Phase 5 – Services réseau                          | ⏳ À venir   |
| Phase 6 – Pare-feu et sécurité réseau              | ⏳ À venir   |
| Phase 7 – Hardening systèmes                       | ⏳ À venir   |
| Phase 8 – Supervision                              | ⏳ À venir   |
| Phase 9 – Réponse à incident                       | ⏳ À venir   |
| Phase 10 – Audit de sécurité                       | ⏳ À venir   |
| Phase 11 – Automatisation                          | ⏳ À venir   |
| Phase 12 – Cloud                                   | ⏳ À venir   |
| Projet final                                       | ⏳ À venir   |

---

# 📂 Structure du dépôt

```text
PSIL/
│
├── README.md
│
├── docs/
│   ├── phase0/
│   └── phase1/
│
├── journal/
│
├── diagrams/
│
├── images/
│
├── reports/
│
├── scripts/
│
└── templates/
```

---

# 🖥️ Infrastructure du laboratoire

Architecture prévue :

```text
                 Internet
                    |
               VMware NAT
                    |
               pfSense
                    |
              Réseau LAN PSIL
                    |
    --------------------------------
    |              |              |
 Windows Server  Ubuntu        Kali
   DC01          Server       Security
```

Composants prévus :

* Pare-feu pfSense
* Contrôleur de domaine Windows Server
* Poste client Windows
* Serveur Ubuntu
* Machine Kali Linux
* Serveur de supervision Wazuh

---

# ✅ Réalisations actuelles

## Phase 1 — Jour 3 : Déploiement pfSense

État :

✅ VMware Workstation 17 Pro configuré
✅ Réseaux VMware configurés :

* VMnet8 NAT (WAN)
* VMnet1 Host-Only (LAN)

✅ VM PSIL-pfSense créée

Configuration pfSense :

```
Version : pfSense 2.8.1-RELEASE

WAN :
em0
192.168.44.120/24
DHCP

LAN :
em1
192.168.1.1/24
Statique

DHCP LAN :
192.168.1.100 - 192.168.1.199
```

Le pare-feu principal du laboratoire est opérationnel.

---

# 📈 Avancement du projet

```text
███████░░░░░░░░░░░░░░░░░░░░░░░░░░░ 15 %
```

---

# 🎓 Compétences développées

À travers ce projet, je développe des compétences en :

* Virtualisation VMware
* Administration système
* Réseaux TCP/IP
* Routage
* Pare-feu
* Windows Server
* Active Directory
* Linux
* Sécurité informatique
* Supervision
* Automatisation
* Documentation technique

---

# 📚 Documentation

Toute la documentation du projet est disponible dans le dossier **docs/**.

Chaque phase comprend :

* les objectifs ;
* la théorie associée ;
* les manipulations réalisées ;
* les captures d'écran ;
* les problèmes rencontrés ;
* les solutions appliquées.

---

# 📜 Licence

Ce projet est distribué sous licence **MIT**.

---

# 👨‍💻 Auteur

**Abdoul Kader PARE**

Étudiant en Licence 3 Informatique

Spécialisation :
**Administration Système • Réseau • Cybersécurité**

GitHub :
https://github.com/mrpare645-stack
## 📚 Documentation Phase 1

- [Jour 1 — Initialisation du projet](docs/phase1/jour1.md)
- [Jour 2 — Structure et documentation](docs/phase1/jour2.md)
- [Jour 3 — Déploiement pfSense avec VMware](docs/phase1/jour3.md)
