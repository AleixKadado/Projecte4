# T10: Servidor Impressió Linux — CUPS (Tasca Individual)

## Breu Descripció

### Introducció
Molt bé, equip. A la nostra consultora, **EverPia**, busquem optimitzar els recursos dels nostres clients per reduir costos i simplificar la gestió.  
Un dels punts més caòtics en qualsevol oficina és la **gestió d’impressores**: drivers incompatibles, costos de tòner descontrolats i equips que no saben a quina impressora estan enviant la feina.

**Solució professional:** implementar un **Servidor d’Impressió Centralitzat**.

**Client:** DevOptimize Solutions  
- Clients: Linux (Zorin OS)  
- Servidors: Ubuntu Server

---

### La Vostra Missió: Prova de Concepte (PoC)
Abans de comprar impressores de xarxa cares, el client vol veure una PoC que demostri que un servidor Linux pot gestionar una impressora i compartir-la de manera transparent amb els clients Zorin.  

**Solució simulada:** impressora virtual **cups-pdf**  
- Imprimeix en un fitxer PDF al servidor en lloc de paper.  

**Objectiu:** configurar l’escenari i demostrar que un client pot enviar treballs d’impressió al servidor.

---

### Escenari de Treball
**Màquina 1 (Servidor):** Ubuntu Server  
- Xarxa: NAT + Host-Only  

**Màquina 2 (Client):** Zorin OS Desktop  
- Xarxa: mateixa configuració que el servidor

---

### Pasos de la PoC
1. Instal·lació de **CUPS** al servidor.  
2. Instal·lació de la **impresora virtual cups-pdf**.  
3. Configuració de l’administració de CUPS i habilitar que escolti per totes les interfícies.  
4. Compartir la impressora mitjançant el frontal web de CUPS.  
5. Al client Zorin, afegir la impressora.  
6. Fer proves d’impressió amb diversos documents.  
7. Comprovar al servidor que s’han generat els arxius PDF corresponents.

**Documentació:**  
- Registrar totes les comandes utilitzades  
- Afegir captures de pantalla per demostrar el correcte funcionament

---

### Materials i Links de Suport
- Material propi: **UD5. AA1. CUPS**. Disponible al Moodle del mòdul de Sistemes Operatius en Xarxa  
- J.B. Alex Mantich. (2024, 15 febrer). *Instalación de servidor de impresión en CUPS para Linux* [Vídeo, YouTube]  
  [https://www.youtube.com/watch?v=FNwSTrOSgZQ](https://www.youtube.com/watch?v=FNwSTrOSgZQ)  
- Canonical. *Network File System (NFS)*. Ubuntu Server Documentation  
  [https://documentation.ubuntu.com/server/how-to/networking/install-nfs/](https://documentation.ubuntu.com/server/how-to/networking/install-nfs/)  
- R00t/2025, 25 abril. *How To Install CUPS Print Server on Ubuntu 24.04 LTS*. Idroot  
  [https://idroot.us/install-cups-print-server-ubuntu-24-04/](https://idroot.us/install-cups-print-server-ubuntu-24-04/)

