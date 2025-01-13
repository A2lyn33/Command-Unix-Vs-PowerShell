# Commandes de bases Unix et PowerShell
---
| **🖥️ Commande Unix/Linux** | **⚡ Commande PowerShell**        | **📘 Explications**                                                              |
|----------------------------|----------------------------------|---------------------------------------------------------------------------------|
| **📂 cp**                 | `Copy-Item`                     | Copie des fichiers ou dossiers. Ex. : `Copy-Item source.txt dest.txt`.         |
| **🗑️ rm**                 | `Remove-Item`                   | Supprime des fichiers ou dossiers. Ex. : `Remove-Item file.txt`.               |
| **📁 cd**                 | `Set-Location`                  | Change le répertoire courant. Ex. : `Set-Location C:\Users`.                   |
| **📂 mkdir**              | `New-Item -ItemType Directory`  | Crée un nouveau dossier. Ex. : `New-Item -Path . -Name NewFolder -ItemType Directory`. |
| **❓ man**                | `Get-Help`                      | Affiche l’aide d’une commande. Ex. : `Get-Help Copy-Item`.                     |
| **⏳ history**            | `Get-History`                   | Affiche l’historique des commandes PowerShell.                                 |
| **🔗 alias**              | Plusieurs commandes :           | Gère les alias dans PowerShell.                                                |
|                           | - `New-Alias`                  | Crée un alias. Ex. : `New-Alias ll Get-ChildItem`.                             |
|                           | - `Set-Alias`                  | Modifie un alias existant.                                                     |
|                           | - `Get-Alias`                  | Liste les alias disponibles.                                                   |
|                           | - `Export-Alias`, `Import-Alias`| Sauvegarde ou charge des alias depuis un fichier.                              |
| **📄 cat**                | `Get-Content`                   | Affiche le contenu d’un fichier. Ex. : `Get-Content file.txt`.                 |
| **🔀 mv**                 | `Move-Item`                     | Déplace ou renomme un fichier/dossier. Ex. : `Move-Item oldname.txt newname.txt`. |
| **📜 ls**                 | `Get-ChildItem`                 | Liste les fichiers et dossiers. Ex. : `Get-ChildItem C:\Path`.                 |
| **🛤️ pwd**               | `Get-Location`                  | Affiche le chemin du répertoire courant.                                       |
| **📢 echo**               | `Write-Output`                  | Affiche un texte dans la console. Ex. : `Write-Output "Hello World"`.          |
| **🖋️ touch**             | `New-Item`                      | Crée un fichier vide. Ex. : `New-Item -Path file.txt`.                         |
| **🔍 find**              | `Get-ChildItem` avec filtres    | Recherche des fichiers. Ex. : `Get-ChildItem -Path C:\ -Recurse -Filter *.txt`. |
| **📑 grep**              | `Select-String`                 | Recherche un motif dans un fichier. Ex. : `Select-String -Path file.txt -Pattern "text"`. |
| **⬆️ head**              | `Get-Content` avec `-TotalCount`| Affiche les premières lignes d’un fichier. Ex. : `Get-Content file.txt -TotalCount 5`. |
| **⬇️ tail**              | `Get-Content` avec `-Tail`      | Affiche les dernières lignes d’un fichier. Ex. : `Get-Content file.txt -Tail 5`. |
| **🙋‍♂️ whoami**          | `$env:USERNAME` ou `whoami.exe` | Affiche l’utilisateur courant.                                                |
| **🔒 chmod**             | `icacls`                        | Modifie les permissions des fichiers. Ex. : `icacls file.txt /grant User:F`.   |
| **⚙️ ps**                | `Get-Process`                   | Affiche les processus en cours. Ex. : `Get-Process`.                           |
| **✂️ kill**              | `Stop-Process`                  | Termine un processus. Ex. : `Stop-Process -Name notepad`.                      |
| **💾 df**                | `Get-PSDrive`                   | Affiche les informations sur les disques montés. Ex. : `Get-PSDrive`.          |

---

### **🔍 Détails supplémentaires :**
1. **Différences principales :**
   - PowerShell manipule des objets, pas des chaînes de caractères. Par exemple, `Get-Process` retourne des objets processus manipulables.
   - Les commandes PowerShell suivent une syntaxe `Verbe-Nom` explicite.

2. **Gestion avancée des alias :**
   - PowerShell permet de sauvegarder et importer des alias, ce qui n'est pas natif dans Unix.

3. **Recherche avancée :**
   - `Select-String` permet des recherches complexes grâce aux expressions régulières.
### **Commandes PowerShell : `Select-String`**

`Select-String` est l'équivalent PowerShell de la commande Unix/Linux `grep`. Elle est utilisée pour rechercher des motifs dans le contenu de fichiers, chaînes ou objets, avec la possibilité d'utiliser des expressions régulières (regex) pour des recherches avancées.

---

### 🧐 **Qu'est-ce que `Select-String` ?**
`Select-String` est l'équivalent PowerShell de la commande **`grep`** en Unix/Linux. Elle permet de rechercher :
- 🔍 du texte ou des motifs dans des **fichiers**,
- 📝 des **chaînes de texte**,
- 📦 ou d'autres objets.

---

### 🛠️ **Syntaxe simple :**
```powershell
Select-String -Pattern <motif> -Path <chemin_fichier>
```

---

### 📚 **Exemples pratiques :**

#### 1. 🔍 **Rechercher un mot dans un fichier :**
```powershell
Select-String -Pattern "erreur" -Path "log.txt"
```
Cela affiche toutes les lignes du fichier **`log.txt`** contenant le mot **erreur**.

#### 2. 📂 **Rechercher dans tous les fichiers d'un dossier :**
```powershell
Select-String -Pattern "warning" -Path "C:\Logs\*.log"
```
Cela recherche **warning** dans tous les fichiers **`.log`** du dossier **`C:\Logs`**.

#### 3. 📖 **Afficher une recherche avec du contexte :**
```powershell
Select-String -Pattern "error" -Path "log.txt" -Context 2,2
```
Cela affiche les **2 lignes avant et après** chaque ligne contenant **error**.

#### 4. 📝 **Rechercher dans une chaîne de texte :**
```powershell
"Bonjour le monde" | Select-String -Pattern "monde"
```
Cela recherche **monde** dans le texte directement passé via le pipeline.

---

### ⚙️ **Options principales :**

- **`-Pattern` :** 🔤 Le texte ou motif à rechercher (compatible regex).  
- **`-Path` :** 📂 Le fichier ou dossier dans lequel effectuer la recherche.  
- **`-Context <avant,après>` :** 📖 Ajoute des lignes avant/après pour un contexte.  
- **`-CaseSensitive` :** 🔡 Recherche sensible à la casse.  
- **`-AllMatches` :** 🔄 Trouve toutes les correspondances sur une même ligne.

---

### ⚔️ **Comparaison avec `grep` :**

| **Fonctionnalité**           | **`Select-String`**           | **`grep`**                  |
|------------------------------|-------------------------------|-----------------------------|
| Recherche simple             | ✅ Oui                        | ✅ Oui                      |
| Sensibilité à la casse       | ✅ Option `-CaseSensitive`    | ✅ Option `-i` (ignorer)    |
| Recherche dans un dossier    | ✅ Oui (`-Path "*.log"`)      | ✅ Oui (`grep -r`)          |
| Afficher le contexte         | ✅ Oui (`-Context`)           | ✅ Oui (`grep -C`)          |
| Recherche dans une chaîne    | ✅ Oui, via le pipeline       | ❌ Non, fichier requis      |

---

### 🚀 **Résumé rapide :**

#### 1️⃣ **Recherche simple dans un fichier :**
```powershell
Select-String -Pattern "motif" -Path "fichier.txt"
```

#### 2️⃣ **Recherche avancée dans un dossier avec contexte :**
```powershell
Select-String -Pattern "motif" -Path "C:\Dossier\*.txt" -Context 2,2
```
---
