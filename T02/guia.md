# T02: Còpies de Seguretat a Linux amb Duplicity

En aquesta pràctica aprendrem a configurar i realitzar còpies de seguretat en un servidor Ubuntu utilitzant Duplicity i un segon disc dur de 10 GB.

---

## 1. Creació de la partició

El primer pas és preparar el nou disc creant-hi una partició.

```bash
sudo fdisk /dev/sdb
```

### Passos dins de fdisk:
- n → crear una partició nova  
- p → definir-la com a primària  
- ENTER → acceptar els valors per defecte  
- w → guardar els canvis

---

## 2. Format i muntatge

Un cop creada la partició, li assignem el sistema de fitxers XFS:

```bash
sudo mkfs.xfs /dev/sdb1
```

Ara creem el directori que farem servir per muntar el disc:

```bash
sudo mkdir -p /media/backup
```

I muntem la partició manualment:

```bash
sudo mount /dev/sdb1 /media/backup
```

---

## 3. Instal·lació de Duplicity

Instal·lem la utilitat Duplicity, que ens permet fer còpies de seguretat:

```bash
sudo apt install duplicity
```

---

## 4. Creació d’usuaris

Afegim dos usuaris nous amb directori personal:

```bash
sudo useradd -m -s /bin/bash usuari2
sudo useradd -m -s /bin/bash usuari3
```

Establim la seva contrasenya:

```bash
sudo passwd usuari2
sudo passwd usuari3
```

---

## 5. Creació d’arxius de prova

Per comprovar el funcionament, generem quatre fitxers de 10 MB al directori de l’usuari principal.

---

## 6. Còpia completa

Fem una còpia total de `/home` cap al disc de backup:

```bash
sudo duplicity full /home/ file:///media/backup/
```

---

## 7. Restauració de dades

Eliminem els fitxers de prova:

```bash
rm arxiu*
```

I restaurem la informació:

```bash
sudo duplicity restore file:///media/backup/ /home/usuari
```

---

## 8. Còpia incremental

Afegim un fitxer nou i fem una còpia incremental. Duplicity només copiarà el fitxer afegit.

---

## 9. Script de còpia automàtica (full)

Desmuntem la unitat abans:

```bash
sudo umount /media/backup
```

Script `fullbackup.sh`:

```bash
#!/bin/bash

export PASSPHRASE="usuariusuari1234"

mount /dev/sdb1 /media/backup
duplicity full /home file:///media/backup/homebackup
umount /media/backup
```

Permisos:

```bash
sudo chmod +x fullbackup.sh
```

---

## 10. Programació amb CRON (còpia completa)

Programem la còpia completa els diumenges a les 23:00:

```bash
sudo crontab -e
```

---

## 11. Script incremental automàtic

`incrementalbackup.sh`:

```bash
#!/bin/bash

export PASSPHRASE="usuariusuari1234"

mount /dev/sdb1 /media/backup
duplicity incremental /home file:///media/backup/homebackup
umount /media/backup
```

Permisos:

```bash
sudo chmod +x incrementalbackup.sh
```

---

## 12. Programació amb CRON (incremental)

Programem la còpia incremental de dilluns a dissabte a les 23:00:

```bash
sudo crontab -e
```

---
