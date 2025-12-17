# Introducció

Molt bé, equip de consultors júniors. En aquest projecte ens trobem amb un requisit tècnic molt habitual: la **centralització de dades en entorns Linux**.

## El cas del client: DevOptimize Solutions

**DevOptimize Solutions** és una petita startup de desenvolupament de programari que treballa exclusivament amb Linux. Actualment pateixen un problema crític de desorganització del seu codi font i dels seus actius (documents de disseny, scripts, etc.).

Cada desenvolupador manté còpies locals, fet que provoca:
- Errors constants de versió  
- Pèrdua d’eficiència  
- Dificultat per treballar en equip  

## Solució proposada

El client ha contractat els nostres serveis per implementar un **servidor de fitxers centralitzat**. Donat que tot l’entorn és Linux, la solució més adequada és **NFS (Network File System)**, concretament **NFSv3**, per ser nativa, ràpida i eficient.

Cal tenir en compte que:
- El client **no disposa d’un sistema d’autenticació centralitzada**
- No té previst implementar-lo a curt termini

## Objectiu de la demostració

Per mostrar com funcionaria la solució i quines són les seves limitacions, es demana crear una demostració pràctica que inclogui:

- Un **servidor NFS (NFSv3)**
- Un **client Linux** que consumeixi els recursos compartits
- Creació d’**usuaris i grups** per simular l’entorn real
- Control d’accés mitjançant:
  - Opcions d’exportació (`/etc/exports`)
  - Permisos del sistema de fitxers (`chmod`, `chown`)

