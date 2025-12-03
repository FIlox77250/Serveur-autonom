# CO – R4 Administration des systèmes 2025-2026

Projet collaboratif réalisé à 4 personnes.
Ce projet contient un script d’audit et de maintenance des systèmes, avec journalisation, sauvegarde dynamique et contrôle des services critiques.

## 🚀 Description du projet

CO est un projet développé en équipe pour :

* Apprendre à travailler en collaboration avec Git et GitHub.
* Développer un script de gestion et maintenance système.
* Auditer les performances et la sécurité d’un serveur Linux.

Le script inclut :

### 1️⃣ Audit de performance et gestion des services

* Vérification de l’espace disque (/home) et de la mémoire vive (RAM) avec seuils critiques (85% disque, 90% RAM).
* Comptage des connexions HTTP/HTTPS actives via `netstat`.
* Redémarrage conditionnel des services critiques : `fail2ban`, `rsyslog`, `mariadb`.

### 2️⃣ Sauvegarde dynamique et intégrité

* Acceptation d’un argument `-d` pour le répertoire à sauvegarder.
* Validation de l’argument et sortie avec codes 102 ou 103 en cas d’erreur.
* Archivage avec compression Xz, uniquement fichiers `.conf` et `.html`.
* Nom des archives dynamique : `NOM_REP_ANNEE_MOIS_JOUR_HEURE`.
* Génération d’un checksum SHA512 pour vérification d’intégrité.

### 3️⃣ Audit de sécurité et nettoyage

* Identification des utilisateurs inactifs depuis plus de 30 jours.
* Affichage de la liste et confirmation avant toute action.

### 4️⃣ Journalisation et robustesse

* Création d’un fichier de log unique dans `/var/log/maintenance`.
* Comptage de lignes et filtrage d’IP dans un fichier d’analyse.
* Gestion des interruptions avec `trap` pour consigner les erreurs.

### 5️⃣ Planification

* Commande Cron à ajouter pour exécuter le script tous les dimanches à 20h00 :

```cron
0 20 * * 0 /chemin/vers/le/script.sh
```

---

## 👥 Équipe

* Baptiste Margalef
* Guillaume LeGrand
* Lucas Pacheco Ribeiro
* Antonin Gouhoury

## 🛠️ Technologies utilisées

* Git / GitHub
* Visual Studio Code
* Bash / Linux

## 📦 Installation

Pour récupérer le projet sur votre machine :

```bash
git clone https://github.com/FIlox77250/Serveur-autonom.git
cd Serveur-autonom
```

Puis ouvrez le dossier dans VS Code.

## 🔧 Contribution

1. Créez une branche pour chaque fonctionnalité :

```bash
git checkout -b nom-de-branche
```

2. Travaillez sur votre code
3. Ouvrez une **pull request** sur GitHub pour fusionner

## 📄 Licence

Ce projet est disponible sous licence libre (à définir selon vos besoins).
