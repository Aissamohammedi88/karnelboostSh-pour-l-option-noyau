
<div align="center">

# ⚡ NametronSh — System Suite

### v4.0.0 · Professional Edition

**16 modules · Bash · Dashboard web · API REST**

![Version](https://img.shields.io/badge/version-4.0.0-00d9ff?style=for-the-badge)
![Bash](https://img.shields.io/badge/Bash-4%2B-4eaa25?style=for-the-badge&logo=gnubash&logoColor=white)
![Modules](https://img.shields.io/badge/modules-16-ff00e6?style=for-the-badge)
![Licence](https://img.shields.io/badge/licence-NEXUS--OPEN--2.0-ffb000?style=for-the-badge)

*Mesure · Audite · Nettoie · Surveille*

[Installation](#installation) ·
[Menu](#menu-interactif) ·
[Commandes](#commandes-cli) ·
[Dashboard](#dashboard-web) ·
[Sécurité](#sécurité)

</div>

---

<a id="presentation"></a>
## 🎯 Présentation

**NametronSh** est une suite d’administration système pilotée depuis un seul
script : `nexus_suite.sh`.

Elle regroupe des fonctions de benchmark, d’audit, de nettoyage, de sauvegarde,
de rapport et de consultation du système. Le projet annonce également un
dashboard web avec API REST.

> Les fonctionnalités disponibles dépendent de la version réelle du script.
> Consulte les commandes et options implémentées avant de les utiliser.

### Fonctionnalités annoncées

- Menu interactif et interface en ligne de commande
- Benchmark CPU, mémoire et disque
- Audit de paramètres système
- Nettoyage avec mode simulation
- Informations sur le noyau, les services, le réseau et le matériel
- Sauvegardes et rapports JSON
- Journaux, fichiers d’état et configuration
- Dashboard web et API REST

---

<a id="installation"></a>
## 🚀 Installation

Remplace `VOTRE_NOM` par le nom de ton compte GitHub :

```bash
git clone https://github.com/VOTRE_NOM/NametronSh.git
cd NametronSh
chmod +x nexus_suite.sh
./nexus_suite.sh
```

Le lancement sans argument ouvre le menu interactif, si cette fonction est
présente dans la version du script.

### Prérequis

- Linux
- Bash 4 ou plus récent
- Python 3 si le dashboard ou ses outils associés en ont besoin

<details>
<summary>🔎 Vérifier les versions installées</summary>

```bash
bash --version
python3 --version
```

</details>

---

<a id="menu-interactif"></a>
## 🖥️ Menu interactif

Lance le script sans argument :

```bash
./nexus_suite.sh
```

Le menu annoncé permet d’accéder aux fonctions suivantes :

```text
[1] ⚡ Tout optimiser
[2] 📊 Benchmark complet
[3] 🧹 Nettoyer le disque
[4] ⚙️ Optimiser le noyau
[5] 🔒 Audit sécurité
[6] 🔍 Audit des services
[7] 🌐 Analyse réseau
[8] 🖥️ Détection matérielle
[9] 💾 Sauvegarde des configurations
    📄 Générer un rapport JSON
    🌐 Lancer le dashboard web
    🔧 Installer le démarrage automatique
    📋 Voir le bilan final
[0] ❌ Quitter
```

Les choix du menu doivent correspondre aux options réellement disponibles dans
`nexus_suite.sh`.

---

<a id="commandes-cli"></a>
## ⚡ Commandes CLI

```bash
./nexus_suite.sh bench       # Benchmark CPU, mémoire et disque
./nexus_suite.sh audit       # Audit de sécurité
./nexus_suite.sh clean       # Nettoyage
./nexus_suite.sh kernel      # Réglages du noyau
./nexus_suite.sh services    # Informations sur les services
./nexus_suite.sh network     # Informations réseau
./nexus_suite.sh hardware    # Informations matérielles
./nexus_suite.sh backup      # Sauvegarde
./nexus_suite.sh report      # Rapport JSON
./nexus_suite.sh web         # Dashboard web
./nexus_suite.sh all         # Exécution de toutes les actions prévues
```

### Options

```bash
./nexus_suite.sh --dry-run clean       # Simuler le nettoyage
./nexus_suite.sh --verbose audit       # Afficher plus de détails
./nexus_suite.sh --json report         # Demander une sortie JSON
./nexus_suite.sh --port 8080 web       # Choisir le port du dashboard
./nexus_suite.sh --no-browser web      # Ne pas ouvrir le navigateur
```

> Utilise `--dry-run` avant une opération qui pourrait modifier ton système.

---

<a id="benchmarks"></a>
## 📊 Benchmarks

La commande `bench` peut afficher des mesures de mémoire, d’espace disque, de
charge système et des tests de lecture ou d’écriture.

```text
Exemple de résultats — les valeurs varient selon la machine

RAM utilisée :                 42.3 %
Disque utilisé :               68 %
Load average :                 1.2
Test de calcul CPU :           0.42 s
Écriture de 100 Mo :           0.8 s
Lecture de 100 Mo :            0.3 s
```

Les chiffres ci-dessus sont illustratifs. Les résultats dépendent notamment
du matériel, du système, de la charge et de l’espace disponible. Un nettoyage
ne garantit pas une baisse de l’utilisation de la mémoire ou du disque.

---

<a id="audit"></a>
## 🔒 Audit de sécurité

```bash
./nexus_suite.sh audit
```

Les vérifications annoncées peuvent porter sur des paramètres comme la
connexion SSH root, le pare-feu, les mises à jour et les ports en écoute.

Un score sur 100 est un indicateur fourni par l’outil, pas une certification
ni une garantie que le système est sécurisé. Examine les résultats avant
d’entreprendre une modification.

---

<a id="dashboard-web"></a>
## 🌐 Dashboard web

Lancement annoncé :

```bash
./nexus_suite.sh web
```

Adresse locale par défaut :

```text
http://localhost:9999/
```

Fonctionnalités annoncées :

- Affichage des statistiques système
- Barres de progression
- Console d’activité
- Raccourcis clavier
- Actualisation périodique

### API REST annoncée

| Endpoint | Description |
|---|---|
| `GET /` | Page du dashboard |
| `GET /api/stats` | Statistiques système |
| `GET /api/action?cmd=audit` | Déclenchement d’une action |
| `GET /health` | Vérification de disponibilité |
| `GET /api/version` | Version du service |

### ⚠️ Sécuriser le dashboard

La configuration d’exemple indique `auth_required: false`. Ne rends pas le
dashboard accessible depuis Internet ou un réseau partagé avec ce réglage.

L’endpoint `/api/action` peut lancer des commandes. Pour un déploiement réel,
protège l’accès et privilégie une méthode HTTP `POST` pour déclencher des
actions. Ne publie jamais de vrai token dans le dépôt.

---

<a id="fichiers-generes"></a>
## 📁 Fichiers générés

Le script annonce l’utilisation du répertoire `~/Documents/nexus_suite/` :

```text
nexus_suite/
├── logs/       # Journaux
├── reports/    # Rapports JSON
├── backups/    # Sauvegardes et manifestes
├── config/     # Configuration
├── cache/      # Fichiers temporaires
├── plugins/    # Extensions
├── state/      # État et verrouillage
├── dashboard.html
└── server.py
```

La structure exacte et la durée de conservation des journaux dépendent du
comportement réel du script.

---

<a id="configuration"></a>
## ⚙️ Configuration

Exemple de structure JSON :

```json
{
  "port": 9999,
  "token": "REMPLACER_PAR_UN_TOKEN_LOCAL",
  "options": {
    "backup_before_clean": true,
    "log_level": "info",
    "auth_required": false
  },
  "kernel": {
    "swappiness": 10,
    "vfs_cache_pressure": 50
  }
}
```

Ne réutilise pas ce token d’exemple. Vérifie dans le code comment le champ
`auth_required` est appliqué avant de lancer le dashboard.

---

<a id="securite"></a>
## 🛡️ Utilisation responsable

Utilise NametronSh uniquement sur des machines que tu possèdes ou que tu es
autorisé à administrer.

- Lis le code avant de l’exécuter.
- Commence en mode `--dry-run` lorsqu’il est disponible.
- Fais une sauvegarde avant de modifier le système.
- Ne lance pas de commandes en tant que superutilisateur sans comprendre
  leurs effets.
- Ne publie pas de secrets, tokens ou données de configuration sensibles.

---

<a id="licence"></a>
## 📄 Licence et crédits

**Auteur :** Aissa Mohammedi (DGK)  
**Licence annoncée :** NEXUS-OPEN-2.0

Ajoute le texte complet de la licence dans un fichier `LICENSE` à la racine du
dépôt afin que les conditions d’utilisation soient claires.

<div align="center">

**⭐ Si le projet t’est utile, tu peux lui donner une étoile sur GitHub.**

*NametronSh — administration système avec prudence et transparence.*

</div>
