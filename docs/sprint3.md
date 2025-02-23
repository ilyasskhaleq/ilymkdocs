# Introducció

En aquest Sprint treballarem amb un Server i diferents Clients( windows, Ubuntu), En primer lloc,
Instal·larem el domini LDAP i el configurarem, després Gestionarem el domini, Entorns grafics i finalment treballarem amb servidors SMB i nfs.

## Instal·lació domini LDAP

Per a fer la instal·lació d'un domini LDAP hem de configurar un servidor que ens servira 
com a directori per getionar l'autenticació i autorització d'usuaris i recursos en una xarxa.

Tenim dos formes de afegir el nostre domini una es en els arxius que descaragarem i la altra es la següent que es per la comanda reconfigure.
En primer lloc Posem Xarxa NAT per poder tener connexió i que els clients puguin connectar-se.
![Comanda](./imatgesSprint3/1.png)

Posem una ip estatica.
![Comanda](./imatgesSprint3/2.png)
![Comanda](./imatgesSprint3/3.png)


Ho comprovem fents diferents pings.
![Comanda](./imatgesSprint3/4.png)

Nem a l'ubicació següent i cambiem el nostre hostname en el meu cas ho he deixat per defecte.
![Comanda](./imatgesSprint3/5.png)

Nem al arxiu Hosts i agreguem la nostra ip i el nostre domini que afegerim proximament.
![Comanda](./imatgesSprint3/6.png)

Ara descarguem el paquet de LDAP
![Comanda](./imatgesSprint3/7.png)

Fem uh dpkg-recongure slapd 
![Comanda](./imatgesSprint3/8.png)

Posem que no volem omitir la conf.
![Comanda](./imatgesSprint3/9.png)

Posem el nostre domini
![Comanda](./imatgesSprint3/10.png)

Ara el nom de l'organització
![Comanda](./imatgesSprint3/11.png)

Posem la contrasenya i la confirmem.

![Comanda](./imatgesSprint3/12.png)

Posem la opcio SÍ.Posem a guaradar la nova configuració.
![Comanda](./imatgesSprint3/13.png)

Posem la opcio SÍ.Posem a guaradar la nova configuració. 
![Comanda](./imatgesSprint3/14.png)
![Comanda](./imatgesSprint3/16.png)

Ara per comprovar les dades farem seguidament la comanda slapcat.
![Comanda](./imatgesSprint3/16.png)

Nem al moodle i descarguem una carepta on tenim diferents arxius.
Ara accedir amb la comanda nano al arxiu uo.ldif i cambiem per a les nostres dades com el domini. 
![Comanda](./imatgesSprint3/17.png)

Ara nem al arxiu grup.ldif i fem quasi les mateixes configuracions. 
![Comanda](./imatgesSprint3/18.png)

Ens inisirim en el usu.ldif i fem diferents configuracions d'usuaris.
![Comanda](./imatgesSprint3/19.png)

Ara fem un ldapadd i afegim les configuracions que hem fet anteriorment, es te que dir esta es la segona opció de com afegir el nostre domini. Si tornem a fer un slapcat podem veure els canvis fets.
![Comanda](./imatgesSprint3/20.png)

Si tornem a fer un slapcat podem veure els canvis fets.
![Comanda](./imatgesSprint3/21.png)

## Unir equips al domini

Ara nem a unir el nostre primer client.
En primer lloc instal·lem ambla següent comanda, Al finalitzar la següent comanda sens obrira la següent finetra.
![Comanda](./imatgesSprint3/22.png)

Si per algun cas al instal·lar el anterior apt i hem saltat la configuració posem la següent comanda per poder configurar el LDAP.
Pisem que volem congifurar el LDAP.
![Comanda](./imatgesSprint3/24.png)

Posem la ip del nostre servidor i acceptar.
![Comanda](./imatgesSprint3/25.png)

Posem el nostre domini que hem posat anteriorment al fer la instal·lació en el SERVIDOR.
![Comanda](./imatgesSprint3/26.png)

Posem la versio 3.
![Comanda](./imatgesSprint3/27.png)

Cliquem la opcio Sí.
![Comanda](./imatgesSprint3/28.png)

Cliquem la opcio Sí.
![Comanda](./imatgesSprint3/29.png)

Posem admin per tener permisos de admin.
![Comanda](./imatgesSprint3/30.png)

Ara posem la contrasenya que hem posat al SERVIDOR i la tornem a posar per confirmar.
![Comanda](./imatgesSprint3/12.png)
![Comanda](./imatgesSprint3/13.png)

Tornem a posar els priviligis que tindrem.
![Comanda](./imatgesSprint3/31.png)

Posem md5 que es per encriptar la contrasenyar.
![Comanda](./imatgesSprint3/32.png)

Nem al arxiu /etc/nsswitch.conf  i fiquem exactament com es mostra en la imatge següent.
![Comanda](./imatgesSprint3/33.png)

Ara nem al arxiu /etc/pam.d/common-session i posem la comanda que esta en el requadre roig.
![Comanda](./imatgesSprint3/34.png)

Cambiem les següents en el fitxer 50-Ubuntu.conf.
![Comanda](./imatgesSprint3/35.png)

Ara fem un use alu 1 i accedim al alu1 desde codi i fem un whoami per veure els privilegis que tenim i veem que tenim de alu1.
![Comanda](./imatgesSprint3/36.png)
## Gestió de domini

Per gestionar utlitzarem diferents comandes de ldap.

Fem un rconfigure per esborrar altres usuaris o grups creats anteriorment.
![Comanda](./imatgesSprint3/37.png)

Ara agafaem un fitxer i agreguem dades que vulguem amb la seva ou i etc...
![Comanda](./imatgesSprint3/38.png)

Fem la següent comanda per afegir els usuaris que tenim al fitxer .ldif i posem la contra que hem dir anteriorment.
![Comanda](./imatgesSprint3/39.png)

Fem un slapcat i podem observar els usuaris que hem dit anteriorment.
![Comanda](./imatgesSprint3/40.png)

Ara podem utilitzar aquesta comanda per poder fer una busqueda.
![Comanda](./imatgesSprint3/41.png)

També podem utilitzar diferents filtres per fer unes bones busquedes com ara farem pel seu mail.
![Comanda](./imatgesSprint3/42.png)

També podem utilitzar pel filtre groups
![Comanda](./imatgesSprint3/43.png)

Ara podem utilitzar la comanda ldapmodify. Primer crearem un document que es dira proves.ldif i aqui podrem posar totes les modificacións que farem.
![Comanda](./imatgesSprint3/44.png)

I farem esta comanda per fer la modificació. Podrem observar que ens posant que se esta modificant.
![Comanda](./imatgesSprint3/45.png)

Ara en ves de utilitzar la comanda ldapdelete utilitzem la de ldapmodify i al arxiu posem en el lloc de type posem delete aixi podem esborrar els usuaris.
![Comanda](./imatgesSprint3/46.png)

Ara tornem a fer la comanda anterior i podem observar que esta borrant al usuari.
![Comanda](./imatgesSprint3/47.png)

Ara fem una altra modificació afegint un mail a un usuari especific.
![Comanda](./imatgesSprint3/48.png)

I realitzem la comanda i fem un search.

![Comanda](./imatgesSprint3/49.png)

Ara farem una altra modificació de tipo modrdn i cambiarem el cn a MiguelAngel.
![Comanda](./imatgesSprint3/50.png)

Tornem a fer la comanda ldapmodify i al fer un search podem observar que el cambi ha funcionat correctament.
![Comanda](./imatgesSprint3/51.png)



## Entorns gràfics

Per utilitzar Entorns grafics utilitzarem el programa Apache Directory Studio i seguirem els següents pasos:

En primer lloc accedim a la pagina oficial de Apache Directory i instal·lem el programam per a linux.
![Comanda](./imatgesSprint3/100.png) 

Es possible que que ens faigue instal·lar el java, jo en el meu cas ja el tinc instal·lat. Accedim a la part superior en `LDAP`
![Comanda](./imatgesSprint3/101.png) 

Posem nova connexió.
![Comanda](./imatgesSprint3/102.png) 

Posem un nom a la connexió i la ip del server, i virifiquem la connectivitat.
![Comanda](./imatgesSprint3/103.png) 

Ara posem el nostre domini i posem a verificar en aquest cas surt que ja esta verificat.
![Comanda](./imatgesSprint3/104.png)

Ara agregarem un usuari per provar si funciona realment.

Entrarem al nostre domini i fem oin posa `New Entry`.
![Comanda](./imatgesSprint3/105.png) 

Posem que utilitzem un esquema existent.
![Comanda](./imatgesSprint3/106.png) 

Posem els següents objectes que voldrem afegir.
![Comanda](./imatgesSprint3/110.png) 


Agreguem les dades del nou usuari.
![Comanda](./imatgesSprint3/107.png) 

Agreguem les següents dades i posem a finalitzar.
![Comanda](./imatgesSprint3/111.png) 

Aqui ja podem veure que ja esta creat
![Comanda](./imatgesSprint3/112.png) 

Ara es poder accedir amb l'usuari creat pero no he pogut.








## Servidors SMB 

### INSTAL·LACIÓ I CONFIGURACIÓ SERVER

En primer lloc, en la maquina server utilitzem la següent comanda per instal·lar samba.
![Comanda](./imatgesSprint3/52.png) 

Creem els següent directori que voldrem compartir amb els permisos necessaris. 
![Comanda](./imatgesSprint3/53.png)

En el arxiu `etc/samba/smb.conf` afegim les següents dades per a que els clients puguin tenir permiso en la carpeta que compartirem.
![Comanda](./imatgesSprint3/54.png)

Sempre que fem algún canvi en aquest arxiu estem obligats (Si volem que funcion) a fer la següent comanda `systemctl restart smbd nmbd`
![Comanda](./imatgesSprint3/55.png)

Utilitzem aquest acomanda per crear els usuaris que puguin accedir a la carpeta.
Seguirem la següent comanda per crear usuaris i grups.
![Comanda](./imatgesSprint3/56.png)

![Comanda](./imatgesSprint3/57.png)

Le posem una contrasenya amb la comanda `smbpasswd -a "blau"`, aquesta contrasenya la necessitarem al voler accedir a la carpeta.
![Comanda](./imatgesSprint3/58.png)

Ara tornem a l'arxiu `etc/samba/smb.conf` i fem els següents canvis, Principalment son els permisos que lis hi donem als usuaris.
![Comanda](./imatgesSprint3/59.png)

### INSTAL·LACIÓ  I PROVES CLIENT

En el client ubuntu fem la instal·lació del smbclient.
![Comanda](./imatgesSprint3/60.png)

Nem a Fitxers, altres ubicacions, i a la barra de baix posem la següent URL: `smb://10.0.2.15/proves` i posem connectar. 
![Comanda](./imatgesSprint3/61.png)

Posem per provar si podem accedir amb permisos d'anonim.
![Comanda](./imatgesSprint3/62.png)

Amb les modificacions que tenim en el fitxer `etc/samba/smb.conf` no seria possible crear o fer modificacions amb els permisos de anonim.
![Comanda](./imatgesSprint3/63.png)

Per arreglar aquest error posem el `read only = yes` en comentaris.
![Comanda](./imatgesSprint3/64.png)

Com he dit abans hem de fer un restart al smbd nmbd
![Comanda](./imatgesSprint3/65.png)

I ara finalment podem crear una carpeta anominada anonim.
![Comanda](./imatgesSprint3/66.png)

Ara provem de entrar amb el usuari blau i la contrasenya que vam posar al crear.
![Comanda](./imatgesSprint3/67.png)

Creem una carpeta per probar si podem crear i com se pot veure hem creat la carpeta anominda blau.
![Comanda](./imatgesSprint3/68.png)

Nem al servidor i podem veure que se han correctament i amb els permisos del seu creador.
![Comanda](./imatgesSprint3/69.png)

Ara porobem en roig i com antes en el fitxer `etc/samba/smb.conf` hem posat que denegem el acces al usuari roig.
![Comanda](./imatgesSprint3/70.png)

Ara probem amb l'usuari groc.
![Comanda](./imatgesSprint3/71.png)

Podem accedir pero nomes podem llegir
![Comanda](./imatgesSprint3/72.png)
No podem crear ni esborrar.



## Servidors NFS

Per a compartir fitxers en NFS en el Servidor hem de instal·lar el nfs-kernel-server.
![Comanda](./imatgesSprint3/74.png)

Fem un `systemctl status nfs-srever` per veure el estat.
![Comanda](./imatgesSprint3/75.png)

### Instal·lació pasrt client ubuntu
Ara nem al client ubutnu i fem la següent comanda per instal·lar 
![Comanda](./imatgesSprint3/76.png)

### Instal·lació pasrt client windows

Per fer la instal·lació en windows necesitem fer diferent pasos per poder activar-ho.
En primer lloc nem al `Programes i caracteristiques`:
![Comanda](./imatgesSprint3/77.png)

A la part esquerra i cliquem sobre `Activar o desactivar las caracteristicas de Windows`:
![Comanda](./imatgesSprint3/78.png)

Ens ubiquem   a la caracteristica de `Servicios para NFS`.
![Comanda](./imatgesSprint3/79.png)

I posem acceptar i se ens actualitzara.
![Comanda](./imatgesSprint3/80.png)

### Compartició carpeta al server i proves en el serverç

Creem la carpeta que volem compartir.
![Comanda](./imatgesSprint3/81.png)

Li assignem els permisos a la carpeta i ho comprovem.
![Comanda](./imatgesSprint3/82.png)

En el arxiu `/etc/exports` afegim el següent codi.
![Comanda](./imatgesSprint3/83.png)

I reiniciem el nfs-kernel-server
![Comanda](./imatgesSprint3/84.png)

Ara nem al client windows i entrem dins de la ip del server 
![Comanda](./imatgesSprint3/85.png)

Com podem veure ja estem dins de la carpeta i creem un arxiu.txt.
![Comanda](./imatgesSprint3/86.png)

Si entrem al server i fem un ls, podem veure que se ha creat.
![Comanda](./imatgesSprint3/87.png)

Si posem en acces directe, cada vegada que iniciem sissió podrem accedir a la carpeta.
![Comanda](./imatgesSprint3/88.png)

Ara accedim al client ubuntu.

Accedim al directori /mnt i creem una carpeta nfs i li assignem permisos adients.
Proximament muntem la carpeta amb la IP del Server i al fer la comanda `df -h` podrem veure el que hem fet.
![Comanda](./imatgesSprint3/89.png)

accedim a /nfs i creem el arxiu `aaaa` 
![Comanda](./imatgesSprint3/90.png)

Accedim al Server i  fem un ls - l podem veure el arxiu creat.
![Comanda](./imatgesSprint3/91.png)

### Perfils mobils (Ubuntu LDAP)

Ara realitzarem els perfils mobils amb el client Ubunt.

Anirem a l'arrel on crearem la carpeta perfils amb els següents permissos.
![Comanda](./imatgesSprint3/92.png)

Accedirem al arxiu `/etc/exports` i afegirem el següent codi.
![Comanda](./imatgesSprint3/98.png)

Fem un reinici del `nfs-kernel-server`
![Comanda](./imatgesSprint3/94.png)

Accedirem al arxiu `usu.ldif` i modifiquem els següents parametres, que basicament son el nom del usuari, on es creara el home del usuari (Quan accedim) i la contrasenya.
![Comanda](./imatgesSprint3/95.png)

Realitzem el `ldapadd` del usuari que hem modificat anteriorment
![Comanda](./imatgesSprint3/96.png)

Accedim al `/etc/fstab` i agreguem el següent codi.
![Comanda](./imatgesSprint3/97.png)

Cal afegir que la correció que vam parlar que fariem ja esta feta pero no hem tingut resultats ja que la mquina(client) hem petaba.

![Comanda](./imatgesSprint3/99.png)



