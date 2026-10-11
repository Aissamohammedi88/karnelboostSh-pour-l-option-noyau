
<div align="center">

# ⚡ NametronSh

### System Suite · Professional Edition · v4.0.0

**Une suite d’administration système en Bash : benchmarks, audit, sauvegardes et dashboard web.**

<img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=700&size=20&duration=2500&pause=800&color=00F7FF&center=true&vCenter=true&width=700&lines=NAMETRONSH+SYSTEM+SUITE;BENCHMARK+%2F+AUDIT+%2F+BACKUP;DASHBOARD+%2B+API+REST;ADMINISTRATION+SYST%C3%88ME+EN+MODE+CLI" alt="Bannière animée NametronSh">

<br>

![Version](https://img.shields.io/badge/version-4.0.0-00d9ff?style=for-the-badge)
![Bash](https://img.shields.io/badge/Bash-4%2B-4eaa25?style=for-the-badge&logo=gnubash&logoColor=white)
![Modules](https://img.shields.io/badge/modules-16-ff00e6?style=for-the-badge)
![Licence](https://img.shields.io/badge/licence-NEXUS--OPEN--2.0-ffb000?style=for-the-badge)

[Installation](#installation) ·
[Menu interactif](#menu-interactif) ·
[Commandes](#commandes-cli) ·
[Dashboard](#dashboard-web) ·
[Sécurité](#sécurité)

</div>

---

<a id="presentation"></a>
## Présentation

**NametronSh** rassemble des outils d’administration système dans le script
`nexus_suite.sh`. Le projet propose un menu interactif, des commandes directes
et un dashboard web.

### Modules annoncés

- Benchmark CPU, mémoire et disque
- Audit de sécurité et informations sur les services
- Nettoyage et réglages du noyau
- Analyse réseau et détection matérielle
- Sauvegardes et rapports JSON
- Journaux, configuration et état d’exécution
- Dashboard web et API REST
- Options de simulation et de diagnostic

> Les opérations de nettoyage et de réglage peuvent modifier le système.
> Lis les commandes et utilise le mode `--dry-run` lorsqu’il est disponible.

---

<a id="installation"></a>
## Installation

Remplace `VOTRE-NOM` par le nom de ton compte GitHub :

```bash
git clone https://github.com/VOTRE-NOM/NametronSh.git
cd NametronSh
chmod +x nexus_suite.sh
./nexus_suite.sh
```

### Prérequis

- Linux
- Bash 4 ou plus récent
- Python 3 pour les composants qui utilisent le dashboard ou le serveur web

Vérifie les versions installées :

```bash
bash --version
python3 --version
```

---

<a id="menu-interactif"></a>
## Menu interactif

Lance le script sans argument pour ouvrir le menu, si cette fonction est incluse
dans ta version :

```bash
./nexus_suite.sh
```

Clique sur une option pour afficher sa commande :

<details>
<summary>⚡ 1 — Tout optimiser</summary>

Lance la séquence complète prévue par le script.

```bash
./nexus_suite.sh all
```

</details>

<details>
<summary>📊 2 — Benchmark complet</summary>

Mesure les performances système disponibles dans le module benchmark.

```bash
./nexus_suite.sh bench
```

</details>

<details>
<summary>🧹 3 — Nettoyer le disque</summary>

Commence par simuler l’opération si le mode simulation est pris en charge.

```bash
./nexus_suite.sh --dry-run clean
```

</details>

<details>
<summary>⚙️ 4 — Réglages du noyau</summary>

Exécute le module de réglages noyau configuré par le script.

```bash
./nexus_suite.sh kernel
```

</details>

<details>
<summary>🔒 5 — Audit de sécurité</summary>

Lance les vérifications de sécurité configurées dans l’outil.

```bash
./nexus_suite.sh audit
```

</details>

<details>
<summary>🔍 6 — Audit des services</summary>

Affiche les informations prises en charge sur les services système.

```bash
./nexus_suite.sh services
```

</details>

<details>
<summary>🌐 7 — Analyse réseau</summary>

Lance le module d’information réseau.

```bash
./nexus_suite.sh network
```

</details>

<details>
<summary>🖥️ 8 — Détection matérielle</summary>

Affiche les informations matérielles détectées par le script.

```bash
./nexus_suite.sh hardware
```

</details>

<details>
<summary>💾 9 — Sauvegarde</summary>

Lance le module de sauvegarde.

```bash
./nexus_suite.sh backup
```

</details>

<details>
<summary>📄 Générer un rapport JSON</summary>

```bash
./nexus_suite.sh --json report
```

</details>

<details>
<summary>🌐 Lancer le dashboard web</summary>

```bash
./nexus_suite.sh web
```

</details>

<details>
<summary>❌ Quitter</summary>

Dans le menu du terminal, sélectionne `0` pour quitter.

</details>

---

<a id="commandes-cli"></a>
## Commandes CLI

| Commande | Fonction |
|---|---|
| `bench` | Benchmark CPU, mémoire et disque |
| `audit` | Audit de sécurité |
| `clean` | Nettoyage |
| `kernel` | Réglages du noyau |
| `services` | Informations sur les services |
| `network` | Informations réseau |
| `hardware` | Informations matérielles |
| `backup` | Sauvegarde |
| `report` | Rapport JSON |
| `web` | Dashboard web |
| `all` | Exécution de la séquence complète prévue |

### Options

```bash
# Simuler une opération lorsqu’elle prend en charge le mode dry-run
./nexus_suite.sh --dry-run clean

# Afficher des informations de diagnostic supplémentaires
./nexus_suite.sh --verbose audit

# Demander une sortie JSON
./nexus_suite.sh --json report

# Choisir le port du dashboard
./nexus_suite.sh --port 8080 web

# Ne pas ouvrir automatiquement le navigateur
./nexus_suite.sh --no-browser web
```

---

<a id="benchmarks"></a>
## Benchmarks

Le module benchmark peut présenter des mesures d’utilisation et des tests de
performance. Exemple de format de sortie :

```text
BENCHMARK — EXEMPLE

RAM utilisée :                  42.3 %
Disque utilisé :                68 %
Load average :                  1.2

Test de calcul CPU :            0.42 s
Écriture de 100 Mo :            0.8 s
Lecture de 100 Mo :             0.3 s
```

Ces chiffres sont des **exemples**, pas une garantie de résultats. Les mesures
dépendent de la machine, du système, de la charge et des conditions du test.
Un nettoyage ne garantit pas une baisse de l’utilisation de la RAM ou du disque.

---

<a id="audit-securite"></a>
## Audit de sécurité

Lance l’audit avec :

```bash
./nexus_suite.sh audit
```

Les contrôles annoncés peuvent inclure des paramètres SSH, le pare-feu,
les mises à jour et les ports en écoute.

Le score sur 100 est un indicateur produit par le script. Il ne constitue ni
une certification ni une garantie de sécurité. Examine les résultats et vérifie
les changements proposés avant de les appliquer.

---

<a id="dashboard-web"></a>
## Dashboard web

Lancement :

```bash
./nexus_suite.sh web
```

Adresse locale annoncée par défaut :

```text
http://localhost:9999/
```

Fonctionnalités annoncées :

- Statistiques de mémoire, disque, charge CPU et disponibilité système
- Barres de progression et console d’activité
- Actualisation automatique
- Raccourcis clavier et actions rapides

### API REST annoncée

| Endpoint | Description |
|---|---|
| `GET /` | Page du dashboard |
| `GET /api/stats` | Statistiques système |
| `GET /api/action?cmd=audit` | Déclenchement d’une action |
| `GET /health` | Vérification de disponibilité |
| `GET /api/version` | Version du service |

### Sécurité du dashboard

La configuration fournie indique `auth_required: false`. Ne rends pas le
dashboard accessible depuis Internet ou un réseau partagé avec cette option.

L’endpoint `/api/action` peut lancer une action système. Protège l’accès avant
tout déploiement réseau ; une requête `POST` est préférable pour déclencher une
action. N’utilise pas de token réel dans un dépôt public.

---

<a id="fichiers-generes"></a>
## Fichiers générés

Le répertoire annoncé est `~/Documents/nexus_suite/` :

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

Les fichiers réellement créés et la durée de conservation des journaux
dépendent de la version et de la configuration du script.

---

<a id="configuration"></a>
## Configuration

Exemple de structure de configuration :

```json
{
  "port": 9999,
  "token": "REMPLACE_PAR_UN_TOKEN_LOCAL",
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

Ne publie jamais un vrai token dans le dépôt. Vérifie dans le code comment
l’option `auth_required` est utilisée avant de lancer le dashboard.

---

<a id="utilisation-responsable"></a>
## Utilisation responsable

Utilise NametronSh uniquement sur des systèmes que tu possèdes ou que tu es
autorisé à administrer.

- Lis le script avant de l’exécuter.
- Utilise `--dry-run` avant toute opération qui modifie des fichiers ou des réglages.
- Fais une sauvegarde avant une modification importante.
- Ne lance pas le script en tant que superutilisateur sans comprendre les effets.
- Ne publie pas de secrets, tokens ou configurations sensibles.

---

<a id="licence"></a>
## Licence et crédits

**Auteur :** Aissa Mohammedi (DGK)  
**Projet :** NametronSh — Code Nametron 3 Lara  
**Licence annoncée :** NEXUS-OPEN-2.0  
**Build indiqué :** `a7f3c9e1b2d4`

Ajoute le texte complet de la licence dans un fichier `LICENSE` à la racine du
dépôt afin que les conditions d’utilisation soient claires.

<div align="center">

**⭐ Si le projet t’est utile, ajoute une étoile au dépôt.**

*NametronSh — outils système, contrôle local et utilisation responsable.*

</div>
