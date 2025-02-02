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
## Servidors SMB 
## Servidors NFS
