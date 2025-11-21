# T02: DPR — Còpies de Seguretat  
## Cas pràctic

---

## 🔹 Breu descripció

### **Introducció al cas**
A la tasca anterior heu dissenyat una política de còpies de seguretat pel client **"Muntatges i Serveis Tècnics SL"**.  
Ara toca portar aquesta política a la pràctica. El client demana unes **guies tècniques amb proves de concepte** perquè el seu personal pugui implementar correctament el pla de còpies.

---

# 🟦 Part 1: Còpia de seguretat dels equips clients Windows

Encara que el DPR no contempla normalment fer còpia dels equips clients, es farà una **excepció** amb l’equip Windows del **director de l’empresa**, ja que conté informació sensible que no es vol guardar al servidor.

S’ha de definir una política de còpies seguint **l’esquema 3-2-1**, amb:

- **Còpia local** → al segon disc del seu equip  
- **Còpia al cloud** → Google Drive usant **Duplicati**

---

## 🔸 **Prova de concepte (Windows 11 VM)**

Crea una màquina virtual amb:

- **Disc 1:** Sistema operatiu Windows 11  
- **Disc 2:** 10 GB → emmagatzematge de còpies  
- **Google Drive:** usar un compte NO escolar

### Requisits:
- Còpia del **perfil d’usuari cada hora** → disc secundari  
- **Còpia a Google Drive** → cada dia a les **18:00**

---

## 🔹 Procediment a documentar

### **1. Instal·lació de Duplicati**
Incloure:
- Descàrrega  
- Instal·lació  
- Reinici del servei  
- Primera execució  

### **2. Configuració dels plans de còpia**
Crear:
- **Pla 1:** Còpia horària → disc secundari  
- **Pla 2:** Còpia diària 18:00 → Google Drive  

Detallar:
- Què es copia (perfil usuari, Documents…)  
- Xifrat  
- Programació horària  
- Ubicació destí  
- Verificació de còpies  

### **3. Proves de funcionament**
- Crear arxius a Documents i altres carpetes del perfil  
- Deixar que Duplicati faci diverses còpies  
- Comprovar versions, logs i historial

### **4. Restauració des del disc secundari**
- Esborrar el contingut de Documents  
- Restaurar utilitzant la còpia local  
- Validar recuperació correcta

### **5. Restauració des del cloud (Google Drive)**
- Simular pèrdua total  
- Restaurar des de la còpia remota  
- Comprovar integritat  

---

# 🟪 Part 2: Còpia de seguretat servidor Linux (Ubuntu Server)

La solució proposada és **Duplicity**, que permet:

- Còpies locals  
- Còpies remotes  
- Xifrat  
- Integració amb **cron**

S’ha de crear una **guia tècnica completa**.

---

## 🔸 Prova de concepte (Ubuntu Server VM)

### **1. Preparar la unitat externa**
Afegir un segon disc de 10 GB i:

```bash
sudo mkfs.xfs /dev/sdb
sudo mkdir -p /media/backup
sudo mount /dev/sdb /media/backup
