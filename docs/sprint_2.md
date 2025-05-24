# Instal·lació, Configuració de Programari de Base i Gestió de Fitxers

## Gestió de Processos

Per poder visualitzar el processos tenim doos maneres que serien en cmd o en part grafica.

La primera és a través de la comanda `tasklist` que mostra els processos en execució.
![Comanda](./Projecte2/Sprint2/1.png) 

Per matar un processos s'usa la comanda `taskkill` amb el nom del processos que volem matar.
![Comanda](./Projecte2/Sprint2/2.png) 

També podem guardar els processos dins d'un arxiu i es fa de la següent forma.
![Comanda](./Projecte2/Sprint2/3.png)

La següent forma es visualitzar els processos de forma gràfica fent botó dret al escriptori i en administraciío de tarees i mes detalls i podriem veure els processos i tot el que comporta.
![Comanda](./Projecte2/Sprint2/4.png)


![Comanda](./Projecte2/Sprint2/5.png)

![Comanda](./Projecte2/Sprint2/6.png)

## Gestió d'usuaris, grups i permisos 

### Usuaris i grups
Per poder gestionar usuaris graficament utilitzem el programa `lusrmgr.msc` que es troba a la carpeta de programari de Windows.

![Comanda](./Projecte2/Sprint2/us1.png)

Accedim a usuaris i per crear es realitzen els següents passos.
![Comanda](./Projecte2/Sprint2/us2.png)

Creem el primer usuari `ilyass` amb la seva contraseña.
![Comanda](./Projecte2/Sprint2/us3.png)

creem el segon usuari `juan` amb la seva contraseña.
![Comanda](./Projecte2/Sprint2/us4.png)

Com podem observar s'han creat correctament.
![Comanda](./Projecte2/Sprint2/us5.png)

Ara ens posarem a crear un grup de usuaris que simulariem els usuaris del institut.
![Comanda](./Projecte2/Sprint2/us6.png)

Com podem observar s'han creat correctament.
![Comanda](./Projecte2/Sprint2/us7.png)

Ara comprovem que podem accedir als usuaris.
![Comanda](./Projecte2/Sprint2/us8.png)

Com podem observar hem accedim correctament als usuaris creats.
![Comanda](./Projecte2/Sprint2/us9.png)

### Permisos

Creem una carpeta ies ebre i per gestionar els permisos accedim a propietats de carpeta.
![Comanda](./Projecte2/Sprint2/perr1.png)

Accedim a seguretat i a `opcions avanzadas` i `deshabilitem hirencia `que vol dir que Deshabilitar herència atura que la carpeta hereti permisos del directori pare. Això ens permet configurar permisos personalitzats només per a aquesta carpeta.

![Comanda](./Projecte2/Sprint2/per1.png)

I esborrem quasi tots menys el administrador i seguidament passem els ppermisos al grup iesbre ja que es l'objectiu de la practica.
![Comanda](./Projecte2/Sprint2/per2.png)

Creem un altre grup i posem un usuari que no pertany al ies ebre.
![Comanda](./Projecte2/Sprint2/per3.png)

Aa finalment en permisos denegem tot tipus de permisos al grup.
![Comanda](./Projecte2/Sprint2/per4.png)

Finalemnt accedim amb el usuari `noalumne` i podem observar que no ens deixa accedir a la carpeta i que no ens deixa crear fitxers.
![Comanda](./Projecte2/Sprint2/per5.png)

I si acceidm desde un usuari que pertany al grup iesbre podem observar que ens deixa accedir a la carpeta i que ens deixa crear fitxers.
![Comanda](./Projecte2/Sprint2/per6.png)


## Còpies de Seguretat i automatizació

Afegim un un nou disc.
![Comanda](./Projecte2/Sprint2/copies1.png)

I fem un apartició en NFTS amb el següent nom
![Comanda](./Projecte2/Sprint2/copies2.png)
Creem el següent script es un paregut que he trobat per internet.

![Comanda](./Projecte2/Sprint2/copies3.png)

Tenim el .bat i l'executem amb permisos admin.
![Comanda](./Projecte2/Sprint2/copies4.png)

Com podem observar ens crea una carepta al disc que hem creat abans
![Comanda](./Projecte2/Sprint2/copies5.png)

Ara per fer-ho automatic accedim a "Editor de directivas de grupo local" i nem a scripts i posem que se executen al iniciar sissió.
![Comanda](./Projecte2/Sprint2/copies6.png)

Accedim en un altre usuari i sens obrira un terminal pero es tancara al segon.
![Comanda](./Projecte2/Sprint2/copies7.png)

Com podem observar ens crea la carpeta del usuauri.
![Comanda](./Projecte2/Sprint2/copies8.png)



## Quotes de disc
En aquset cas crearem un disc de 50gb pero es recomana fer de menys tamañ per fer proves mes exactes.
![Comanda](./Projecte2/Sprint2/qa1.png)

Com hem fet en el anterior crearem les particions i les assignem els següents formats.
![Comanda](./Projecte2/Sprint2/qa2.png)

I per podem comprovar en el cmd fem la comanda `diskpart` i ens obrira una pantalla de la següent forma, i hem de fer la comanda `list volume` per veure les particions.
![Comanda](./Projecte2/Sprint2/qa3.png)

Al fer la partció de formats `NTFS` ens surt a la carpeta de Aquest equip i ja podriem treballar amb la partició.
![Comanda](./Projecte2/Sprint2/q1.png)

Accedim a les propietats del disc i accedim a `Cuota`.
![Comanda](./Projecte2/Sprint2/q2.png)

Fem a mostrar la configuració i posem el limit de l'espai i el nivell d'advertencia
![Comanda](./Projecte2/Sprint2/q3.png)

Al guardar canvis podem veure que la partció de disc ha sigut modificada i que ens surt que esta activa.
![Comanda](./Projecte2/Sprint2/q4.png)

Per fer la prova accedim desde diferents usuari i veiem que ens registra les entrades.
![Comanda](./Projecte2/Sprint2/q22.png)