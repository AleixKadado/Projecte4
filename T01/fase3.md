# Política de Còpies de Seguretat – Muntatges i Serveis Tècnics SL

## 1) Dades Objecte de Còpia

### **Servidor**

#### **Dades crítiques (còpia més freqüent)**
- **Bases de dades de Comptabilitat i Clients (20 GB).**
- **Freqüència:**
  - Còpia incremental cada 4 hores
  - Còpia completa setmanal

#### **Dades importants però no crítiques**
- **Documents de Projectes (300 GB)**
- **Carpetes Personals dels usuaris (100 GB)**
- **Freqüència:**
  - Còpia incremental diària
  - Còpia completa setmanal

### **Equips Clients**
- No es fa còpia completa dels 10 PCs.
- Només es protegeix la carpeta **Documents dels tècnics**, amb una còpia incremental diària.
- La informació important està centralitzada al servidor.

---

## 2) Cronograma Setmanal Detallat

| **Dia**     | **Dades**                               | **Tipus de còpia** | **Mitjà**          |
|-------------|------------------------------------------|---------------------|---------------------|
| Dilluns     | BD (cada 4 h), Documents, Carpetes       | Incremental         | NAS                 |
| Dimarts     | BD (cada 4 h), Documents, Carpetes       | Incremental         | NAS                 |
| Dimecres    | BD (cada 4 h), Documents, Carpetes       | Incremental         | NAS                 |
| Dijous      | BD (cada 4 h), Documents, Carpetes       | Incremental         | NAS                 |
| Divendres   | BD (cada 4 h), Documents, Carpetes       | Incremental         | NAS                 |
| Dissabte    | BD (cada 4 h), Documents, Carpetes       | Incremental         | NAS                 |
| Diumenge    | Totes les dades del servidor             | Completa setmanal   | NAS + Núvol         |

### **Còpia mensual**
- El **primer diumenge de cada mes**: còpia completa al núvol com a punt de retenció llarg.

---

## 3) Elecció de Mitjans i Ubicació (Regla 3-2-1)

### **Mitjà 1 (Local)**
- NAS empresarial ubicat al rack de l’empresa.
- Permet automatitzar totes les còpies incrementals i completes amb alta velocitat.

### **Mitjà 2 (Extern)**
- Còpia al núvol (Azure Backup o Google Cloud Storage).
- Protegeix davant incendis, robatoris i desastres totals.

### **Ubicació Fora de Lloc**
- La còpia externa es guarda **al núvol (off-site lògic)**.
- La verificació de restauracions és responsabilitat del tècnic de sistemes.

### **Compliment de la Regla 3-2-1**
- **3 còpies:** dades originals + NAS + Cloud  
- **2 mitjans diferents:** NAS i Cloud  
- **1 còpia fora de lloc:** núvol  

---

## 4) Estratègia de Recuperació (RTO/RPO)

### **RPO (4 hores)**
- Garantit gràcies a:
  - Còpies incrementals de la BD cada 4 hores.
- Es garanteix no perdre més treball que aquest interval.

### **RTO (4 hores)**
- Garantit gràcies a:
  - Restauració ràpida des del NAS local.
  - Combinació de còpia completa setmanal + incrementals per reconstruir el sistema.

### **En cas de desastre total**
- Restauració des del núvol.
- Temps més elevat, però dades garantides.


