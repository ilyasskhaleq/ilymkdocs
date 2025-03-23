# Monitorització
## Logs

Que es un LOG?
Es un arxiu que es pot observar tots els registres d'events que passen en el sistema operatiu, son importnats ja que ens serveixen per fer un bon diagnostic d'un problema, també podem realitzar auditories o monitoritzar el rendiment del sistema.

On s'ubiquen?
Es poden trobar en la següent ruta:
![Comanda](./sprint5/2.png) 

Tenim la configuració dels logs en el següent arxiu.
![Comanda](./sprint5/3.png) 


Ara farem una prova amb dos terminals oberts per provar aquesta logs.
En el següent arxiu descomentem el que esta destacat i tot el que pasa sobre el que hem descomentat es guaradar en els logs de `syslog`.
![Comanda](./sprint5/4.png) 

La prova que farem consisteix en fer la següent comanda de una alerta d'email i es la següent comanda: ` logger -i -s -p mail.alert Alerta de mail!!`.
I al fer la següent comanda, observem que en el fitxer `var/log/syslog` podem obervar que ens ha avisat sobre aquesta alerta.
![Comanda](./sprint5/5.png) 

Seguirem fent mes proves:

En aquest cas modificarem el log de `mail.log`.
![Comanda](./sprint5/6.png)

I farem la prova del funcionament. 
I podem observar que al fer el `cat /var/log/mail.log` que ens avisa sobre la alerta.
![Comanda](./sprint5/7.png) 

Ara seguirem al el `.crit` que crearem un log amb el meu nom i sera igual que les anteriors vegades.

#### Journal
utilitzarem jounal per veure els avisos que han saltat, utilitzem la següent comanda per veure el critics.
Podem observar que ens han surtit totes les proves que hem fet anteriormen. 
![Comanda](./sprint5/9.png) 
### Logs en xarxa
En primer lloc instal·larem `rsyslog` i accedim al següent fitxer i descomentem les 4 linies.
![Comanda](./sprint5/20.png) 

Despues de la modificació fem un `sysstemctl restart rsyslog` i activem els següent ports.
![Comanda](./sprint5/21.png) 

En el que en aquest cas es el client afegim la ip del servidor i tornem a fer la següent comanda:`systemctl restart rsyslog`. 
![Comanda](./sprint5/22.png) 
Com podem observar en la dreta es el client i hem accedit a root i podem observar que es generen els següents logs.
![Comanda](./sprint5/23.png) 

### Rendiment
Per poder visualitzar el rendiment del sistema tenim un programa que es el següent.
![Comanda](./sprint5/1.png) 
Podrem observar els diferents procesoss que s'executen al mateix temps.
![Comanda](./sprint5/24.png) 

També podem obsrevar els recursos que gasta cada component.
![Comanda](./sprint5/25.png) 

I finalment podem observar Els sistemes de fitxers.
![Comanda](./sprint5/26.png)  

## Servidor actualizacions
Un servidor d'actualitzacions és una màquina centralitzada a la qual es connecten diversos equips clients per obtenir els paquets d'actualització. D’aquesta manera, s’evita saturar la xarxa i els serveis quan molts dispositius intenten descarregar el mateix paquet simultàniament.

Per verificar el correcte funcionament d’aquest sistema, farem servir l’eina Apache, que ens permetrà gestionar i distribuir aquestes actualitzacions de manera eficient.


En primer lloc instal·lem apache en el servidor.
![Comanda](./sprint5/10.png) 
També instal·lem `apt-mirror`
![Comanda](./sprint5/11.png) 
Accedim al arxiu `/etc/apt/mirror.list` i agreguem el següent codi.
![Comanda](./sprint5/12.png) 
Després de modificar el arxiu anterior, executem `apt-mirror`
![Comanda](./sprint5/13.png) 
Seguidament comprovem si els canvis que hem fet se han realitzat correctament.
![Comanda](./sprint5/14.png) 


Els següents passos que farem son en el client.

En primer lloc, afegim la clau GPG  de google a aquest sistema.
![Comanda](./sprint5/15.png) 
En aquest fitxer afegim la ruta del paquert de chrome afegin la ip del server.
![Comanda](./sprint5/16.png) 
Ara fem un update i podem obervar que esta la ruta que hem fet abans.
![Comanda](./sprint5/17.png) 
Ara fem un `apt install google-chrome-stable` i se instal·la chrome.
![Comanda](./sprint5/18.png) 
Seguidament comprovem si esta instal·lat.
![Comanda](./sprint5/27.png) 

## Auditoria
Realitzarem una auditoria amb lynis.
### Lynis
Lynis és una eina d'anàlisi de seguretat de codi obert que s'utilitza per:

+ Avaluar el nivell de seguretat d’un sistema.

+ Identificar configuracions febles o incorrectes.

+ Proporcionar recomanacions per millorar la protecció d’un servidor o equip Linux.

Aquesta eina està especialment dissenyada per a administradors de sistemes, auditors i professionals de la ciberseguretat.

Es important fer `sudo apt update`.

En primer lloc es instal·lar `sudo apt install lynis -y`     
![Comanda](./sprint5/30.png) 
Ara farem una auditoria amb la comanda `lynis audit system`.
![Comanda](./sprint5/31.png) 
Com podem observar tenim diferents apartats on tracten tots els temes del nostre sistema.
Yo me he fixat en un apartat on ens recomana instal·lar uns paquets que ens ajuden a millorar la seguretat del sisema.
![Comanda](./sprint5/32.png) 
![Comanda](./sprint5/33.png) 
![Comanda](./sprint5/34.png) 
![Comanda](./sprint5/35.png) 
Yo me he fixat en un apartat on ens recomana instal·lar uns paquets que ens ajuden a millorar la seguretat del sisema.
Seguidament he descargar els paquets que hem feien falta que son els següents.

+ apt-listbugs: Ajuda a identificar errors coneguts en paquets abans d'instal·lar-los.
+ apt-listchanges: Mostra canvis i notes importants en actualitzacions de paquets.
+ needrestart: Informa si cal reiniciar serveis després d’una actualització.
+ fail2ban: Protegeix contra atacs de força bruta bloquejant IPs sospitoses.
Instal·lem alguns paquets com aquests 3.
![Comanda](./sprint5/36.png) 
I comprovem que ja ens surt que ja estan instal·lats.
![Comanda](./sprint5/37.png) 
