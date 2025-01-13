# 🌳 Arborescence Classique Unix/Linux

| **Répertoire**   | **Description**                                                                                          |
|-------------------|----------------------------------------------------------------------------------------------------------|
| **📁 /**         | Racine du système de fichiers. Tous les autres répertoires sont montés à partir de celui-ci.            |
| **⚙️ /bin**      | Contient les commandes essentielles du système accessibles par tous les utilisateurs (ex. `ls`, `cp`, `mv`). |
| **🔧 /sbin**     | Contient les commandes essentielles destinées aux administrateurs système (ex. `ifconfig`, `reboot`).    |
| **🛠️ /etc**      | Fichiers de configuration système et des applications (ex. `/etc/passwd`, `/etc/fstab`).                |
| **💽 /dev**      | Contient les fichiers spéciaux représentant les périphériques matériels (ex. `/dev/sda` pour un disque). |
| **📊 /proc**     | Répertoire virtuel qui fournit des informations sur les processus et le système en cours d'exécution.   |
| **🖥️ /sys**      | Répertoire virtuel contenant des informations sur le matériel et les périphériques connectés.           |
| **📂 /tmp**      | Répertoire pour les fichiers temporaires (souvent nettoyé automatiquement au redémarrage).              |
| **📈 /var**      | Contient les fichiers variables tels que les logs, les spools d’impression et les fichiers temporaires des applications. |
| **📦 /usr**      | Contient les programmes utilisateur, les bibliothèques, et la documentation.                            |
| **📦 /usr/bin**  | Contient des commandes utilisateur additionnelles (ex. `vim`, `git`).                                   |
| **🔐 /usr/sbin** | Contient des commandes administratives additionnelles.                                                  |
| **📦 /usr/local**| Répertoire pour les logiciels installés manuellement par l’utilisateur.                                 |
| **🏠 /home**     | Répertoire personnel des utilisateurs. Chaque utilisateur a un sous-répertoire (ex. `/home/john`).     |
| **👑 /root**     | Répertoire personnel du super-utilisateur (root).                                                      |
| **📚 /lib**      | Bibliothèques partagées essentielles utilisées par les binaires dans `/bin` et `/sbin`.                 |
| **📚 /lib64**    | Bibliothèques 64 bits (sur les systèmes 64 bits).                                                      |
| **📦 /opt**      | Contient des logiciels optionnels ou tiers installés manuellement.                                     |
| **🚀 /boot**     | Contient les fichiers nécessaires au démarrage du système (ex. `vmlinuz`, `initrd.img`).               |
| **💾 /media**    | Points de montage pour les périphériques amovibles (ex. clé USB, CD-ROM).                              |
| **🗂️ /mnt**      | Points de montage temporaires pour les systèmes de fichiers.                                           |
| **🖧 /srv**      | Contient des données spécifiques aux services offerts par le système (ex. sites web pour un serveur HTTP). |

---

## 🔍 Notes

1. **Répertoires virtuels :**
   - **`/proc`** et **`/sys`** ne contiennent pas de fichiers "réels", mais des informations générées dynamiquement par le noyau.

2. **Organisation modulaire :**
   - Les répertoires **`/bin`**, **`/sbin`**, et **`/usr/bin`** sont séparés pour distinguer les commandes essentielles du système des logiciels additionnels.

3. **Flexibilité :**
   - Les points de montage comme **`/media`** et **`/mnt`** permettent d’ajouter des périphériques ou des systèmes de fichiers externes.
