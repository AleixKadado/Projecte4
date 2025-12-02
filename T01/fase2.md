# Proposta Unificada – Esquema 3-2-1 de Còpies

| **Element** | **Proposta de la Parella** | **Justificació** |
|-------------|-----------------------------|-------------------|
| **Dades Crítiques** | Base de dades principal, documents del projecte i informes | Són els elements essencials per al funcionament i la traçabilitat del cas. |
| **Periodicitat (BD)** | Còpia diària a final de jornada | Evita pèrdues recents i garanteix tenir sempre una versió actualitzada. |
| **Tipus de Còpia (BD)** | Còpia incremental diària + completa setmanal | Les incrementals estalvien espai i temps; la completa garanteix un punt de restauració estable. |
| **Mitjà 1 (Local)** | NAS intern amb accés restringit | Permet restauració ràpida en cas d’error o pèrdua local, i és fàcil d’integrar en la xarxa. |
| **Mitjà 2 (Extern)** | Còpia al núvol (Google Drive / OneDrive) | Assegura la regla del “1 fora de lloc” i protegeix davant robatori, incendi o fallada física del centre. |

