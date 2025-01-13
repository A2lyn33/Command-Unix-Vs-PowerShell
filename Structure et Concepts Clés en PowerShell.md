# 🌳 Structure et Concepts Clés en PowerShell

| **Concept/Commande**         | **Description**                                                                                           |
|-------------------------------|-----------------------------------------------------------------------------------------------------------|
| **🖥️ Prompt**                | L'invite de commandes où vous saisissez vos commandes PowerShell. Peut être personnalisée via `$profile`. |
| **📂 Modules**               | Contiennent des groupes de commandes liées. Les modules peuvent être importés avec `Import-Module`.       |
| **🔧 Cmdlets**               | Commandes de base en PowerShell, structurées en `Verbe-Nom` (ex. `Get-Process`, `Set-Location`).          |
| **📜 Scripts**               | Fichiers PowerShell avec extension `.ps1`, contenant des séquences de commandes.                         |
| **📦 Package Management**    | Permet de gérer des modules et des scripts à l'aide de `Install-Module`, `Find-Module`, ou `Update-Module`. |
| **🔒 Sécurité des Scripts**  | Les scripts PowerShell sont soumis à une politique d'exécution (ex. `Get-ExecutionPolicy`, `Set-ExecutionPolicy`). |
| **🔗 Alias**                 | Raccourcis pour les cmdlets (ex. `ls` pour `Get-ChildItem`). Peut être géré avec `New-Alias` et `Get-Alias`. |
| **🔍 Pipeline**              | Permet de passer les sorties d’une commande en entrée d'une autre commande via `|`. Exemple : `Get-Process | Select-Object Name, ID`. |
| **📄 Variables**             | Stockent des données ou des objets. Exemple : `$variable = "Hello"`. Utilisez `Get-Variable` pour les voir. |
| **💾 Profil**                | Fichier PowerShell exécuté au démarrage pour charger des paramètres ou commandes personnalisées. Exemple : `$profile`. |
| **📊 Logs et Historique**    | PowerShell sauvegarde l'historique des commandes via `Get-History`. Des logs peuvent être configurés pour des diagnostics avancés. |

---

## 📂 Répertoires Clés dans PowerShell

| **Répertoire**                 | **Description**                                                                                     |
|--------------------------------|-----------------------------------------------------------------------------------------------------|
| **🏠 `$HOME`**                 | Répertoire utilisateur courant, comme `/home/user` en Unix. Utilisé pour stocker des fichiers et profils personnalisés. |
| **📜 `$PROFILE`**              | Fichier chargé automatiquement au démarrage. Permet de personnaliser PowerShell.                  |
| **📂 `$PSModulePath`**         | Chemins des modules PowerShell disponibles. Exemple : `C:\Program Files\WindowsPowerShell\Modules`. |
| **🖥️ `C:\Windows\System32`**  | Contient des outils système accessibles dans PowerShell.                                            |
| **📂 `C:\Program Files`**      | Répertoire commun pour les applications installées.                                                |
| **📂 `$ENV:Path`**             | Variable d'environnement contenant les chemins des exécutables accessibles depuis PowerShell.       |

---

## 🔧 Cmdlets Essentielles

| **Cmdlet**             | **Description**                                                                                 |
|------------------------|-------------------------------------------------------------------------------------------------|
| **`Get-Command`**      | Liste toutes les commandes disponibles.                                                        |
| **`Get-Help`**         | Fournit des informations d'aide pour une commande spécifique. Exemple : `Get-Help Get-Process`. |
| **`Get-Process`**      | Affiche les processus en cours d'exécution.                                                    |
| **`Get-Service`**      | Liste tous les services Windows actifs ou arrêtés.                                             |
| **`Set-Location`**     | Change le répertoire courant (équivalent de `cd` en Unix).                                     |
| **`Get-ChildItem`**    | Liste les fichiers et dossiers (équivalent de `ls` en Unix).                                   |
| **`Copy-Item`**        | Copie des fichiers ou dossiers (équivalent de `cp` en Unix).                                   |
| **`Remove-Item`**      | Supprime des fichiers ou dossiers (équivalent de `rm` en Unix).                                |
| **`New-Item`**         | Crée un nouveau fichier ou dossier (équivalent de `mkdir` ou `touch` en Unix).                 |
| **`Select-String`**    | Recherche des motifs dans des fichiers ou du texte (équivalent de `grep` en Unix).             |
| **`Export-Csv`**       | Exporte des données vers un fichier CSV.                                                       |
| **`Import-Csv`**       | Importe des données depuis un fichier CSV.                                                     |

---

## 🛠️ Notes et Bonnes Pratiques

1. **Modularité :** PowerShell fonctionne avec des **modules** que vous pouvez importer ou télécharger pour ajouter de nouvelles fonctionnalités.
2. **Sécurité :** Configurez votre politique d'exécution avec soin (par exemple, `RemoteSigned`) pour autoriser uniquement les scripts de confiance.
3. **Automatisation :** Combinez des cmdlets et le pipeline (`|`) pour automatiser des tâches complexes.
4. **Interopérabilité :** PowerShell peut exécuter des commandes Windows natives comme `ipconfig` ou `ping`, ainsi que des scripts Bash dans des environnements compatibles.

---
