# T03: Pla de Recuperació davant Desastres (DRP) — Imatges del Sistema

## Breu Descripció

### Introducció al Cas  
Recordeu el cas del portàtil al qual no es podia accedir? En aquella situació, la vostra perícia tant per recuperar l’accés com per posteriorment fortificar-lo va impressionar molt al client. Per això, us ha encarregat un nou projecte: l’elaboració d’un **Pla de Contingència i Continuïtat del Negoci**, que inclou un **Pla de Recuperació davant Desastres (DRP)**.

Aquest pla ha de contemplar tots els processos de restauració de dades, hardware i software crític en cas d’un esdeveniment catastròfic, per tal de recuperar l’activitat normal el més ràpid possible.  

Un aspecte crític és garantir que els treballadors puguin disposar ràpidament dels seus equips en cas de robatori, avaria, etc. Per tant, cal crear **imatges de restauració del sistema**. No és viable reinstal·lar tot des de zero (sistema operatiu, aplicacions, configuracions), perquè el **temps de posada en marxa (RTO)** ha de ser mínim.

Tots els equips de l’empresa utilitzen **GNU/Linux**, concretament **Zorin OS 18**, amb diverses aplicacions ja configurades, de manera que l’imatge ha de conservar tot això.

---

## Fase 1: Anàlisi i Justificació de la Solució Tècnica

1. **Investigació d’eines**  
   Cerqueu almenys **quatre eines** per crear imatges de disc (disk imaging) que permetin restaurar sistemes amb configuració i aplicacions preservades. Trieu **2 solucions comercials** i **2 de comunitat** (open-source).

2. **Comparativa**  
   Per a cada eina, analitzeu i comenteu:
   - Característiques principals (suport de tipus de sistema de fitxers, compressió, encriptació, facilitat d’ús, interoperabilitat, restauració, etc.)
   - Avantatges i limitacions
   - Preu (llicència, cost per equip, cost de manteniment)

3. **Proposta de Solució**  
   Sobre la base de la comparativa, decidiu quina eina proposeu per al client. Justifiqueu la vostra elecció tenint en compte:
   - Cost  
   - Risc  
   - Facilitat d’ús  
   - Rendiment  
   - Compatibilitat amb Zorin OS  
   - Temps de recuperació estimat

---

## Fase 2: Guia d’Ús Tècnica (Manual Operatiu)

Com a prova de concepte, utilitzareu **Rescuezilla** per fer la guia d’imatge i restauració. Heu de fer els següents passos sobre màquines virtuals:

1. **Crear una imatge completa del sistema**  
   - Utilitzeu una màquina virtual que simuli un equip de l’empresa amb **Zorin OS 18**  
   - Generar la imatge completament (sistema operatiu + aplicacions + configuracions)

2. **Restaurar la imatge**  
   - Feu una segona màquina virtual idèntica a la primera (mateix RAM, CPU, disc, xarxa) però **sense cap sistema operatiu**  
   - Restaureu-hi la imatge creada prèviament

3. **Documentació**  
   - Elaboreu una guia tècnica detallada per al personal de manteniment, amb instruccions pas a pas  
   - Incloeu captures de pantalla (imatges) quan sigui rellevant (inici de Rescuezilla, selecció de particions, procés d’escriptura de la imatge, verificació, restauració...)  
   - Indiqueu precaucions, requisits previs i consells (per exemple, comprovar espai en disc, backups de seguretat, validació de la imatge, etc.)

---

## Materials i Links de Suport

- INCIBE — *¿Ya tienes tu Plan de Recuperación ante Desastres?* (Blog, agost 2019)  
  https://www.incibe.es/empresas/blog/tienes-tu-plan-recuperacion-desastres  
- Rescuezilla — pàgina oficial


