# **T05: Accés Remot. Connexió via SSH (tasca individual)**  

Primer de tot, crearem dues màquines virtuals: una amb Windows i l’altra amb Ubuntu. Quan entrem a la màquina d’Ubuntu, obrirem el terminal i executarem unes quantes comandes per instal·lar el servei SSH i deixar-lo llest per utilitzar-lo.

![foto 32](img/1.png)

Comrpovem que s’ha instalat correctament

![foto 32](img/2.png)

la segona interficie la cambiem a host-only

![foto 32](img/3.png)

Editem el netplan per assignar la ip a la interficie, i al acabar fem un sudo netplan apply 

![foto 32](img/4.png)

Comprovar si s’ha assignat correctament

![foto 32](img/5.png)


Ara encenem la màquina amb Windows i li afegim una segona interfície de xarxa en mode *Host Only*, així les dues màquines podran comunicar-se sense problemes.

Un cop dins de Windows, anirem a **“Ver conexiones de red”** per revisar la configuració de l’adaptador i assegurar-nos que l’adreça IP s’ha assignat correctament.

![foto 32](img/6.png)

![foto 32](img/7.png)

Comprovar que s’ha assignat i es veuen entre elles

![foto 32](img/8.png)

Quan ja tenim totes les passes anteriors enllestides, podem provar de connectar-nos a la màquina Ubuntu des de la terminal de Windows amb la comanda:

**ssh usuari@192.168.56.200**

Com és la primera vegada que ens hi connectem, Windows ens mostrarà un avís de seguretat demanant-nos si volem confiar en la clau pública de la màquina Ubuntu. Simplement acceptem per continuar amb la connexió.

![foto 32](img/9.png)

Acceptem i ens connectem

![foto 32](img/10.png)

Com es pot veure, podem editar l’arxiu

![foto 32](img/11.png)

Per tal d’evitar que l’usuari *root* pugui accedir directament per SSH, obrirem l’arxiu **/etc/ssh/sshd\_config** i modificarem les línies corresponents. D’aquesta manera reforcem una mica la seguretat del sistema abans de continuar.

![foto 32](img/12.png)


Ara comprovarem que l’usuari *root* només pot iniciar sessió de forma local i no mitjançant SSH. Per fer aquesta verificació, primer haurem de posar o canviar la contrasenya del root amb la comanda següent:

![foto 32](img/13.png)

Al intentar fer SSH com a root no ens deixara

![foto 32](img/14.png)

Per garantir que només els usuaris autoritzats es puguin connectar remotament, crearem un nou compte d’usuari.

Per fer-ho, afegirem l’usuari **usuari15** amb la comanda següent:

**sudo useradd \-m \-s /bin/bash usuari15**

![foto 32](img/15.png)

A continuació assignarem una contrasenya al nou usuari amb:

**sudo passwd usuari15**

Després, obrirem l’arxiu de configuració d'SSH per indicar quins usuaris tenen permís per connectar-s’hi:

**sudo nano /etc/ssh/sshd\_config**

Un cop dins, afegirem la línia:

**AllowUsers usuari**

D’aquesta manera, només l’usuari especificat podrà iniciar sessió remotament mitjançant SSH.

![foto 32](img/16.png)

![foto 32](img/17.png)

![foto 32](img/18.png)

![foto 32](img/19.png)


Finalment, reiniciarem el servei SSH perquè tots els canvis que hem fet entrin en funcionament. Ho fem amb la comanda:

**sudo systemctl restart ssh**

![foto 32](img/20.png)

Ara, si intentem iniciar sessió amb usuari15 no podrem, mentre que amb l’usuari sí que funciona.

![foto 32](img/21.png)

![foto 32](img/22.png)

**Creació d’un túnel SSH (Proxy SOCKS)**  
Creem un túnel (pots utilitzar qualsevol port que no utilitzi el sistema):

![foto 32](img/23.png)

**Configuració del Proxy a Windows**  
 Configurem el proxy anant a:

**Tauler de control → Xarxa i Internet → Opcions d'Internet → Connexions → Configuració de la LAN**

![foto 32](img/24.png)

Habilitem Servidor Proxy amb IP local i port 9876\.

![foto 32](img/25.png)

![foto 32](img/26.png)

Validar el túnel amb wireshark

![foto 32](img/27.png)

**Configura al teu equip Windows 11 el servidor OpenSSH**  
Entrem a la configuració de Windows 11 i entrem a Sistema.

![foto 32](img/28.png)

Dins de Sistema hem d’entrar a **“veure característiques”** i permetre que l’aplicació faci canvis al dispositiu.

![foto 32](img/29.png)

![foto 32](img/30.png)

Un cop dins de l’aplicació, és **IMPORTANT** prémer **“veure les característiques disponibles”**.

![foto 32](img/31.png)

**Connecta’t remotament des de l’equip Linux (en el meu cas és Ubuntu)**  
 Per poder connectar-nos remotament primer hem de fer el següent:

Primer apaguem el tallafoc a Windows 11; busquem **“Tallafoc i protecció de xarxa”**, hi entrem i tot seguit entrem a **“Xarxa pública”** i la desactivem.

![foto 32](img/32.png)

![foto 32](img/33.png)

Executem powershell com a administrador

![foto 32](img/34.png)

iniciem el servei del servidor ssh

![foto 32](img/35.png)

![foto 32](img/36.png)

Ipconfig

![foto 32](img/37.png)

Des de l’equip Ubuntu ens connectarem a l’equip Windows fent servir la IP de la interfície de només host de l’equip Windows.

Abans de res, fem un **ping** des de l’Ubuntu per comprovar que els dos equips es poden veure entre ells. El comandament seria:

![foto 32](img/38.png)

Un cop comprovat que els dos equips es poden veure, ara sí que ens connectarem des de l’equip Ubuntu a l’equip Windows.

Ho farem utilitzant **ssh** seguit del nom de l’equip Windows i de la IP de només host.

![foto 32](img/39.png)



