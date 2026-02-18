# PatronnatCentrafricain
Plateforme numérique officielle du CESP : un portail institutionnel dynamique conçu pour fédérer le secteur privé. Ce projet inclut un espace membre sécurisé, un observatoire économique et des outils de plaidoyer, visant à digitaliser les services du patronat et booster l'investissement via une interface moderne et scalable.


# 🏛️ CESP - Plateforme Numérique du Patronat

> **Conseil des Entreprises du Secteur Privé** : La vitrine digitale au service du plaidoyer économique et du développement des entreprises.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Stack: Fullstack](https://img.shields.io/badge/Stack-Fullstack-blue.svg)](#-stack-technique)
[![Infra: OpenStack](https://img.shields.io/badge/Infrastructure-OpenStack-red.svg)](#-infrastructure--devops)

---

## 📖 Présentation
La plateforme **CESP** est un portail institutionnel dynamique conçu pour fédérer les acteurs économiques du secteur privé. Elle centralise les ressources stratégiques, facilite les adhésions et offre un observatoire économique en temps réel pour booster l'investissement.

## 🚀 Fonctionnalités Clés
- **Espace Membre Sécurisé** : Dashboard dédié pour le réseautage et la gestion des profils entreprises.
- **Observatoire Économique** : Visualisation de données et indicateurs du secteur privé.
- **Gestion des Adhésions** : Workflow automatisé pour l'inscription et les cotisations.
- **Portail de Plaidoyer** : Publication des réformes législatives et notes de conjoncture.
- **Back-Office Admin** : CMS complet pour la gestion de contenu et des membres.

---

## 🛠️ Stack Technique
* **Frontend :** React.js / Next.js (Architecture moderne & SEO friendly)
* **Styling :** Tailwind CSS (Design responsive & Dark mode)
* **Backend :** Node.js (Express) ou Laravel (API RESTful robuste)
* **Base de données :** PostgreSQL / Redis (Caching)
* **Conteneurisation :** Docker & Docker Compose

---

## 🌐 Infrastructure & DevOps (OpenStack)
Le projet est conçu pour être déployé sur une infrastructure Cloud souveraine via **OpenStack**.

### 🏗️ Déploiement via Kolla-Ansible
L'infrastructure utilise **Kolla-Ansible** pour garantir une haute disponibilité des services.

1.  **Préparation de l'inventaire** :
    ```bash
    cp -r /usr/share/kolla-ansible/ansible/inventory/* .
    ```
2.  **Configuration du Cloud (globals.yml)** :
    ```yaml
    kolla_base_distro: "centos"
    openstack_release: "zed"
    network_interface: "eth0"
    neutron_external_interface: "eth1"
    ```
3.  **Déploiement des conteneurs** :
    ```bash
    kolla-ansible -i ./multinode bootstrap-servers
    kolla-ansible -i ./multinode prechecks
    kolla-ansible -i ./multinode deploy
    ```

### 🐋 Docker Compose (Mode Dev/Test)
Pour lancer l'environnement localement :
```bash
docker-compose up -d --build
