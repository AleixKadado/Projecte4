# T01: DRP — Còpies de Seguretat  
## Estudi de cas client (treball cooperatiu)

---

## 🔹 Breu Descripció

### **Introducció**
La primera hora el vostre responsable de seguretat us presenta el tema de les còpies de seguretat a partir d’un material didàctic. A continuació, caldrà que treballeu els aspectes del tema i ho fareu mitjançant una dinàmica cooperativa.

---

## 🔹 Presentació del cas client

### **Empresa:** *Muntatges i Serveis Tècnics SL*  
Petita empresa dedicada a la instal·lació i manteniment d'equips industrials.

### **Infraestructura Tècnica**
- **Servidor de Fitxers (Ubuntu Server)** — Conté tota la documentació crítica:
  - *Documents de Projectes:* Plànols, especificacions tècniques (300 GB, creixement moderat).
  - *Bases de Dades (Comptabilitat i Clients):* Crítiques i d'ús diari (20 GB, canvi constant).
  - *Carpetes Personals dels Usuaris:* Feina diària (100 GB).
- **10 Equips Clients (Windows 10/11)**  
  Treballen majoritàriament amb fitxers del servidor, amb alguns arxius locals temporals.
- **Connexió a Internet:** Fibra òptica 600 Mbps simètrica.

### **Requisits de Recuperació**
- **RTO:** Les dades de Comptabilitat/Clients han d’estar disponibles en menys de **4 hores**.
- **RPO:**  
  - Dades generals: màxim **24 hores** de pèrdua.  
  - Dades Comptabilitat/Clients: màxim **4 hores** de pèrdua.
- **Retenció:** Historial mínim d’**un mes**.

---

# 🔹 Fase 1: Treball individual

Respon de forma individual basant-te en el cas pràctic:

### **1. Què copiar? (Priorització)**
- Quines són les dades més crítiques del servidor?  
- Cal fer còpia dels 10 equips clients? Justifica-ho.

### **2. Periodicitat i Tipus de Còpia**
Proposa una planificació setmanal indicant:  
- Diari / Setmanal / Mensual  
- Tipus: Completa, Diferencial o Incremental  
- Especialment per a les dades crítiques.

### **3. Mitjans i Ubicació**
- Quin tipus de mitjà de còpia utilitzaries? (Discs externs, NAS, Cloud, Cintes)  
- Segons la **regla 3-2-1**, on guardaries les còpies?

---

# 🔹 Fase 2: Treball per parelles

### **1. Discussió i Consens**
Compareu les respostes individual de la Fase 1.

### **2. Elaboració d'una Proposta Unificada**
Dissenyeu el vostre propi **Esquema 3-2-1 de Còpies**.

| **Element** | **Proposta de la Parella** | **Justificació** |
|-------------|-----------------------------|-------------------|
| **Dades Crítiques** |  |  |
| **Periodicitat (BD)** |  |  |
| **Tipus de Còpia (BD)** |  |  |
| **Mitjà 1 (Local)** |  |  |
| **Mitjà 2 (Extern)** |  |  |

---

# 🔹 Fase 3: Treball en grup

### **1. Debat i Selecció**
Cada parella presenta el seu esquema 3-2-1.  
El grup avalua: cost, temps de recuperació, seguretat, simplicitat.

### **2. Política Final de Còpies**
El grup redacta la **Política de Còpies de Seguretat Definitiva** per a *Muntatges i Serveis Tècnics SL*.

---

# 📄 Document Final (Fase 3)

El document final ha d'incloure:

---

## **1) Dades Objecte de Còpia**
Indicar:
- Quines dades es copien.
- Freqüència.
- Diferenciar *Servidor / Clients* i *Crítiques / No crítiques*.

---

## **2) Cronograma Setmanal Detallat**

| **Dia** | **Dades** | **Tipus de Còpia** | **Mitjà** |
|---------|-----------|---------------------|-----------|
| Dilluns |   |   |   |
| Dimarts |   |   |   |
| Dimecres |   |   |   |
| Dijous |   |   |   |
| Divendres |   |   |   |
| Dissabte |   |   |   |
| Diumenge |   |   |   |

---

## **3) Elecció de Mitjans i Ubicació (Regla 3-2-1)**

- **Mitjà 1 (Local):** Quin dispositiu s’utilitza (USB, NAS…)
- **Mitjà 2 (Extern):** Quin servei/proveïdor (Cloud, LTO…)
- **Ubicació Fora de Lloc:** On es guarda la còpia externa i qui la gestiona.

---

## **4) Estratègia de Recuperació (RTO/RPO)**
Descriure com es garanteix:
- RTO de 4 hores  
- RPO de 4 hores  
per a les dades de Comptabilitat/Clients.

---

# 📚 Materials i links de suport
- Moodle 0226 Seguretat Informàtica – RA2.AA3 Còpies  
- INCIBE — *Copias de seguridad. Una guía de aproximación para el empresario*  
- Xataka — *Backup 3-2-1, el método definitivo para mantener a salvo tus datos*  
  (YouTube, setembre 2017)  
  https://youtu.be/PM_M4Iz6I4o?si=F7DRyDDTZE3hjWn8


