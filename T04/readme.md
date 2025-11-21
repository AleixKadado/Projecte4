# T04: Accés Remot

## Breu Descripció
Aquesta activitat introdueix els conceptes i eines essencials per administrar sistemes informàtics de manera remota. L'objectiu és entendre i dominar les tecnologies que permeten gestionar equips i servidors sense necessitat de trobar-se físicament davant d’ells.

---

## Introducció Teòrica

### La importància de l'accés remot
En l'àmbit professional de l'administració de sistemes i el suport tècnic, l’accés remot és una habilitat fonamental. La majoria de servidors i infraestructures que gestionarem estaran:

- En **sales CPD** (Centres de Processament de Dades),
- A **altres seus corporatives**,
- A **centres de dades d’Internet**,
- O directament al **núvol (Cloud)**.

Quan un client té una incidència crítica, no és viable desplaçar-se físicament fins al lloc on es troba la màquina afectada. La nostra capacitat per intervenir ràpidament, sense importar on estiguem, és un valor essencial com a tècnics i consultors.

Dominar aquestes eines ens permet:

- Resoldre incidències amb rapidesa.
- Gestionar infraestructures distribuïdes.
- Forçar la seguretat d’accés.
- Realitzar tasques de manteniment, configuració i supervisió de manera eficient.

---

## Eines d'Accés Remot

### 🔐 SSH (Secure Shell)
SSH és l’eina fonamental per administrar servidors Linux i, en molts casos, també sistemes Windows.

**Característiques principals:**
- Comunicació xifrada (protocol segur).
- Accés a terminal i execució d’ordres remotes.
- Transferència d’arxius (SCP, SFTP).
- Possibilitat d'autenticació amb claus públiques/privades.
- Control remot fins i tot en servidors sense entorn gràfic.

És la “eina quirúrgica” dels administradors de sistemes.

---

### 🖥️ Escriptoris Remots (RDP i alternatives)
Quan hem d’accedir a sistemes que requereixen entorn gràfic (com servidors Windows o equips d’usuari), utilitzem protocols d’escriptori remot.

**RDP (Remote Desktop Protocol)**  
- Protocol nadiu de Windows.
- Permet accés a un escriptori complet.
- Suport per a compartició de carpetes, impressió i multimedia.

**Alternatives per a Linux:**
- **xRDP** (suport al protocol RDP)
- **VNC** (TigerVNC, RealVNC, TightVNC)

---

### 🤝 Eines d’assistència remota
Per donar suport a clients o usuaris finals, sovint necessitem eines senzilles que no requereixin configuracions complicades.

**Algunes eines destacades:**
- **TeamViewer**: Connexions ràpides i amb codi d’accés.
- **AnyDesk**: Lleuger, ràpid i multiplataforma.
- **Chrome Remote Desktop**: Vinculat al navegador, fàcil per a usuaris no tècnics.

Aquestes eines són ideals per:
- Assistència tècnica puntual.
- Suport a usuaris amb poca experiència.
- Connexions ràpides sense configuració de ports ni VPN.

---

## Objectiu de la Unitat
L’objectiu principal d’aquesta unitat és que sigueu capaços d’utilitzar i entendre totes aquestes eines per administrar sistemes de manera professional. Al final de la unitat s’avaluarà:

- El vostre domini de SSH.
- La vostra capacitat per utilitzar RDP i eines equivalents.
- L’ús correcte d’eines d’assistència remota.
- La comprensió de bones pràctiques de seguretat en accés remot.

L’accés remot no és només una eina: és una competència essencial en l’administració moderna de sistemes i serveis.

---

## Materials i Links de Suport

- **0227. UD4. AA1. Accés Remot**  
  Disponible al Moodle del mòdul de *Serveis de Xarxa*.


