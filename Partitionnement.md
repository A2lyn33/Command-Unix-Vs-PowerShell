# Systèmes de Gestion de Fichiers : Équivalences Linux et PowerShell

| **Fonctionnalité**               | **Linux (Outils CLI)**              | **PowerShell (Windows)**                   | **Description**                                                                 |
|-----------------------------------|-------------------------------------|-------------------------------------------|---------------------------------------------------------------------------------|
| **Lister les disques**            | `lsblk`, `fdisk -l`                 | `Get-Disk`, `Get-Partition`               | Permet d'afficher les disques et leurs partitions.                             |
| **Créer une partition**           | `fdisk`, `parted`                   | `New-Partition`                           | Crée une nouvelle partition sur un disque.                                     |
| **Formater une partition**        | `mkfs` (ex. `mkfs.ext4`)            | `Format-Volume`                           | Formate une partition avec un système de fichiers spécifique.                  |
| **Monter une partition**          | `mount`                             | `Mount-DiskImage`                          | Monte une partition ou une image disque.                                       |
| **Démonter une partition**        | `umount`                            | `Dismount-DiskImage`                      | Démonte une partition ou une image disque.                                     |
| **Modifier une partition**        | `parted`, `fdisk`, `cfdisk`         | `Resize-Partition`                        | Permet de redimensionner ou de modifier une partition existante.               |
| **Vérifier l’intégrité du système de fichiers** | `fsck`                              | `Repair-Volume`                           | Vérifie et répare un système de fichiers endommagé.                            |
| **Afficher des informations sur le disque** | `blkid`, `lsblk`, `df`            | `Get-Volume`, `Get-PhysicalDisk`          | Affiche des informations détaillées sur les disques et partitions.             |
| **Effacer un disque/partition**   | `shred`, `wipe`                     | `Clear-Disk`                              | Supprime toutes les données d’un disque ou partition.                          |
| **Gestion des volumes logiques**  | `lvm`                               | Non natif, mais outils tiers possibles     | Gestion des volumes logiques (création, extension, etc.).                      |
| **Créer une image disque**        | `dd`, `cat`                         | `New-VHD`, `Convert-VHD`                  | Crée ou convertit une image disque.                                            |
| **Détecter des disques externes** | `dmesg`, `lsusb`, `blkid`           | `Get-PnpDevice`, `Get-Disk`               | Identifie les périphériques externes connectés (ex. USB).                      |
| **Système de fichiers avancés**   | `btrfs`, `xfs`, `zfs`               | Non natif, mais avec logiciels tiers      | Utilisation et gestion de systèmes de fichiers avancés.                        |

## Tuto : Commandes de Gestion des Fichiers et Disques

### Lister les disques
- **Linux** :
  ```bash
  lsblk
  fdisk -l
  ```
- **PowerShell** :
  ```powershell
  Get-Disk
  Get-Partition
  ```

### Créer une partition
- **Linux** :
  ```bash
  parted /dev/sdX mkpart primary ext4 1MiB 100%
  fdisk /dev/sdX
  ```
- **PowerShell** :
  ```powershell
  New-Partition -DiskNumber 1 -UseMaximumSize -AssignDriveLetter
  ```

### Formater une partition
- **Linux** :
  ```bash
  mkfs.ext4 /dev/sdX1
  ```
- **PowerShell** :
  ```powershell
  Format-Volume -DriveLetter D -FileSystem NTFS
  ```

### Monter une partition
- **Linux** :
  ```bash
  mount /dev/sdX1 /mnt
  ```
- **PowerShell** :
  ```powershell
  Mount-DiskImage -ImagePath "C:\\path\\to\\image.vhd"
  ```

### Vérifier et réparer un système de fichiers
- **Linux** :
  ```bash
  fsck /dev/sdX1
  ```
- **PowerShell** :
  ```powershell
  Repair-Volume -DriveLetter D
  ```

### Effacer les données d’un disque
- **Linux** :
  ```bash
  shred -v /dev/sdX
  ```
- **PowerShell** :
  ```powershell
  Clear-Disk -Number 1 -RemoveData
  ```

### Créer une image disque
- **Linux** :
  ```bash
  dd if=/dev/sdX of=/path/to/image.img bs=1M
  ```
- **PowerShell** :
  ```powershell
  New-VHD -Path "C:\\path\\to\\image.vhd" -SizeBytes 10GB
  ```

