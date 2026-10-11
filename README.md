# karnelboostSh-pour-l-option-noyau
NametronSh - System Suite v4.0.0 Professional Edition | 2000 lignes bash pur, 16 modules, Dashboard + API REST, par Aissa Mohammedi (DGK)
# ⚡ NametronSh — System Suite v4.0.0

> **16 modules pros. 2000+ lignes bash pur. Logger, locking, dashboard temps réel + API REST.**
> **Zéro dépendance. Multi-distro. Dry-run. Par Aissa Mohammedi (DGK)**

<div align="center">

![Version](https://img.shields.io/badge/version-4.0.0-?style=for-the-badge)
![Bash](https://img.shields.io/badge/bash-4.0%2B-?style=for-the-badge)
![License](https://img.shields.io/badge/license-NEXUS--OPEN--2.0-?style=for-the-badge)
![Modules](https://img.shields.io/badge/modules-16-?style=for-the-badge)
![Lines](https://img.shields.io/badge/lines-2000%2B-?style=for-the-badge)


╔═══════════════════════════════════════════╗
║ ███╗ ██╗███████╗██╗ ██╗██╗ ██╗███████╗ ║
║ ████╗ ██║██╔════╝╚██╗██╔╝██║ ██║██╔════╝ ║
║ ██╔██╗ ██║█████╗ ╚███╔╝ ██║ ██║███████╗ ║
║ NametronSh — Code Nametron 3 Lara ║
╚═══════════════════════════════════════════╝


**[🚀 Installer](#-installation-5-secondes) • [🖥️ Menu](#️-menu-interactif) • [🌐 Dashboard](#-dashboard-web) • [📊 Benchmarks](#-benchmarks-avantaprès)**

</div>

---

### 🎯 C'est quoi NametronSh?

Un seul fichier `nexus_suite.sh` qui remplace 10 outils:
`neofetch + htop + ncdu + bleachbit + lynis + netdata + stacer`

Et en **version PRO**:
- ✅ Parser CLI robuste `getopt`
- ✅ Logger avec rotation 14j + niveaux
- ✅ Locking anti double exécution
- ✅ Gestion signaux SIGINT/SIGTERM
- ✅ Config JSON + State
- ✅ Plugin loader
- ✅ Dry-run partout

### 🚀 Installation 5 secondes

```bash
# Clone
git clone https://github.com/ton-user/NametronSh.git
cd NametronSh
chmod +x nexus_suite.sh
./nexus_suite.sh

# One-liner
curl -fsSL https://raw.githubusercontent.com/ton-user/NametronSh/main/nexus_suite.sh | bash

🖥️ Menu Interactif

Lance sans argument → menu pro:

Que veux-tu faire?

[1] ⚡ Tout optimiser (benchmark → backup → clean → kernel → report)
[2] 📊 Benchmark complet
[3] 🧹 Nettoyer le disque
[4] ⚙️ Optimiser le noyau
[5] 🔒 Audit sécurité (score /100)
[6] 🔍 Audit services
[7] 🌐 Analyse réseau
[8] 🖥️ Détection matérielle
[9] 💾 Backup configurations
📄 Générer rapport JSON
🌐 Lancer le Dashboard Web
🔧 Installer auto-démarrage
📋 Voir le bilan final
[0] ❌ Quitter

⚡ CLI Direct (pour les pros)

./nexus_suite.sh bench # Benchmark CPU/RAM/DISK
./nexus_suite.sh audit # Audit sécurité
./nexus_suite.sh clean # Nettoyage intelligent
./nexus_suite.sh kernel # Opti noyau
./nexus_suite.sh services # Services
./nexus_suite.sh network # Réseau
./nexus_suite.sh hardware # Hardware
./nexus_suite.sh backup # Backup
./nexus_suite.sh report # Rapport JSON
./nexus_suite.sh web # Dashboard
./nexus_suite.sh all # TOUT FAIRE

# Flags
./nexus_suite.sh --dry-run clean # Simule
./nexus_suite.sh --verbose audit # Debug
./nexus_suite.sh --json report # Sortie JSON
./nexus_suite.sh --port 8080 web # Port custom
./nexus_suite.sh --no-browser web # Sans navigateur

📊 Benchmarks Avant/Après

NametronSh mesure tout:

📊 BENCHMARK — ÉTAT INITIAL
RAM utilisée: 42.3%
Disque utilisé: 68%
Load average: 1.2

⚡ BENCHMARK CPU
Test calcul intensif (100k itérations): 0.42s
Écriture 100 Mo: 0.8s
Lecture 100 Mo: 0.3s

📈 GAINS MESURÉS
RAM: 42.3% → 28.1% (gain: 14.2 pts)
Disque: 68% → 52% (gain: 16 pts)
Durée: 12s

🔒 Audit Sécurité — Score /100

./nexus_suite.sh audit

Vérifie:
- Users sans mot de passe
- SSH PermitRootLogin
- Firewall UFW/firewalld
- Paquets à mettre à jour
- Ports en écoute
→ Score final /100 + problèmes détectés

🌐 Dashboard Web Temps Réel

./nexus_suite.sh web
# → http://localhost:9999/

*Features:*
- 4 stats live: RAM, Disque, CPU Load, Uptime + progress bars
- 10 boutons actions rapides
- Console live colorée
- Raccourcis: `1-9` Actions, `R` Refresh
- Auto-refresh 3s

*API REST:*

Endpoint Description
`GET /` Dashboard HTML
`GET /api/stats` RAM/disk/cpu/uptime/hostname
`GET /api/action?cmd=audit` Lance action
`GET /health` Healthcheck
`GET /api/version` Version

📁 Structure Générée

~/Documents/nexus_suite/
├── logs/nexus_suite_20261011.log (rotation 14j)
├── reports/rapport_*.json
├── backups/backup_*/MANIFEST.txt
├── config/config.json
├── cache/
├── plugins/ (loader prêt)
├── state/nexus.lock + state.json
├── dashboard.html
└── server.py

⚙️ Config JSON

`~/Documents/nexus_suite/config/config.json`:

{
"port": 9999,
"token": "nexus-dgk-2026",
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

🏆 Pourquoi NametronSh impressionne?

- *Junior* → "Wtf c'est un OS dans http://un.sh?!"
- *Senior DevOps* → "Logger pro, locking, trap, getopt, dry-run... c'est du code prod"
- *CTO* → "2000 lignes bash qui remplacent toute une stack monitoring"

📄 Licence

*NEXUS-OPEN-2.0* — Par *Aissa Mohammedi (DGK)* — Code Nametron 3 Lara
Québec 2026 — Build `a7f3c9e1b2d4`

---
<div align="center">
<strong>⭐ Star si tu kiffes NametronSh — Forge avec nous NEXUUR-CA/US/EU/ASIA</strong>
</div>


---
