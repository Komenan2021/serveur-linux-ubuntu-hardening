# 🐧 Serveur Linux Ubuntu 24.04 — Administration & durcissement

> Installation et configuration des services **SSH**, **DNS** et **FTP**, gestion des utilisateurs et des permissions, puis **durcissement** du système selon les bonnes pratiques de sécurité.

![OS](https://img.shields.io/badge/OS-Ubuntu%2024.04%20LTS-E95420) ![SSH](https://img.shields.io/badge/Service-SSH-4b5563) ![Hardening](https://img.shields.io/badge/S%C3%A9curit%C3%A9-Hardening-c00) ![Statut](https://img.shields.io/badge/statut-termin%C3%A9-2FA35F)

**Auteur :** Kouakou François Komenan — Analyste SOC / Technicien Réseau, Abidjan
**Portfolio :** https://thefulkom.tech/portfolio/

---

## 🎯 Objectif

Mettre en service un serveur Linux prêt pour la production : services réseau opérationnels, accès maîtrisés et surface d'attaque réduite.

## ⚙️ Ce qui a été mis en place

| Domaine | Réalisation |
|---|---|
| **SSH** | Accès à distance sécurisé |
| **DNS** | Serveur de noms pour le réseau du lab |
| **FTP** | Partage de fichiers |
| **Utilisateurs & groupes** | Comptes nominatifs, groupes par rôle, droits `sudo` limités |
| **Permissions** | Droits sur fichiers et dossiers selon le principe du moindre privilège |
| **Durcissement** | Réduction de la surface d'attaque (voir ci-dessous) |

## 🔐 Durcissement (hardening)

<!-- ✏️ Garde uniquement les mesures que tu as réellement appliquées, ajoute les autres -->

**SSH** (`/etc/ssh/sshd_config`) :
```
PermitRootLogin no
PasswordAuthentication no        # connexion par clé uniquement
MaxAuthTries 3
```

**Pare-feu** :
```bash
sudo ufw default deny incoming
sudo ufw allow OpenSSH
sudo ufw enable
```

**Autres mesures :**
- Mises à jour de sécurité automatiques (`unattended-upgrades`)
- Désactivation des services inutiles
- Protection contre la force brute (ex. `fail2ban`)
- Journalisation et surveillance des connexions (`/var/log/auth.log`)

## 🔎 Déroulement

1. Installation d'Ubuntu Server 24.04 LTS et mise à jour du système.
2. Création des utilisateurs, des groupes et des droits `sudo`.
3. Installation et configuration de **SSH**, **DNS** et **FTP**.
4. Application des permissions sur les dossiers partagés.
5. Durcissement : SSH, pare-feu, services, mises à jour.
6. Vérification : tests de connexion, ports ouverts (`ss -tulpn`), journaux.

## 📊 Résultats

<!-- ✏️ À compléter -->
- Services en production : _à compléter_
- Ports exposés après durcissement : _à compléter_
- Mesures de sécurité appliquées : _à compléter_

## 📜 Scripts

Dépose tes scripts Bash dans un dossier `scripts/` (ex. `scripts/creation-utilisateurs.sh`).

## 📸 Captures d'écran

| Fichier à déposer dans `images/` | Contenu |
|---|---|
| `01-ssh-config.png` | Configuration SSH durcie |
| `02-ufw-status.png` | Règles du pare-feu (`sudo ufw status verbose`) |
| `03-utilisateurs-groupes.png` | Utilisateurs, groupes et permissions |
| `04-dns.png` | Test de résolution DNS |
| `05-ftp.png` | Connexion FTP fonctionnelle |

![SSH](images/01-ssh-config.png)
![Pare-feu](images/02-ufw-status.png)
![Utilisateurs et groupes](images/03-utilisateurs-groupes.png)
![DNS](images/04-dns.png)
![FTP](images/05-ftp.png)

## 🧠 Compétences démontrées

`Linux` · `Ubuntu Server` · `SSH` · `DNS` · `FTP` · `Gestion des droits` · `Hardening` · `Bash`
