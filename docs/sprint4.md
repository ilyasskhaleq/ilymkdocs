# RAIDS (Sistemes d’emmagatzematge)

Els RAID serveixen per millorar la seguretat i el rendiment de l’emmagatzematge mitjançant la combinació de diversos discos. Aquests sistemes ofereixen diferents nivells de redundància i velocitat segons la configuració escollida.


## Tipus de RAID

**RAID 0**: Utilitza almenys dos discos i distribueix les dades entre ells per millorar el rendiment. No proporciona redundància: si un disc falla, es perden totes les dades.

**RAID 1**: Consta de dos discos en mirall, on la informació es copia automàticament d’un a l’altre. Ofereix alta seguretat però redueix la capacitat efectiva a la meitat.

**RAID 5**: Necessita almenys tres discos. Distribueix les dades i la informació de paritat entre tots els discos, permetent recuperar les dades en cas de fallada d’un disc. Equilibra seguretat i rendiment.

**RAID 6**: Similar al RAID 5, però amb un nivell addicional de paritat. Requereix un mínim de quatre discos i pot suportar la fallada de dos discos sense pèrdua de dades.

**Per què és millor fer volums?**
Els volums lògics permeten una gestió més flexible de l’espai d’emmagatzematge, facilitant la redimensió i la reorganització de les dades sense necessitat de reformatejar o perdre informació.

## RAID 1
En primer lloc instal·lem el `mdadm`.
![Comanda](./imatgessprint4/1.png)  
Creem les particions del dos discos, primer del dis sdb.
![Comanda](./imatgessprint4/2.png)  
Ar creem la partició en el disc sdc amb els següents parametres.
![Comanda](./imatgessprint4/3.png)  
Com podem observar al fer el `fdisk -l` podrem observar les particions que hem fet.
![Comanda](./imatgessprint4/4.png)  
Creem la carpeta raid1 i fem la següent comanda.
![Comanda](./imatgessprint4/5.png)  
Cambiem el format a `ext4`
![Comanda](./imatgessprint4/6.png)  
Al fer la següent comanda podrem veure que se ha fet be el raid.
![Comanda](./imatgessprint4/7.png)  
Passem els que ens dona el scan al fitxer `/etc/mdadm/mdadm.conf`.
![Comanda](./imatgessprint4/8.png)  
Seguidament modifiquem aquest fitxer i agreguem el següent codi.
![Comanda](./imatgessprint4/9.png)  
En el arxiu `/etc/fstab` agreguem el ultim codi.
![Comanda](./imatgessprint4/10.png)  
Abans de fer un reboot muntem el disc i fem reinicici dels serveis.
![Comanda](./imatgessprint4/11.png)  
Ya ho tenim tot preparat per fer proves.
![Comanda](./imatgessprint4/12.png)  
Com ha primera prova crearem dos fitxers i ho posarem dins del raid.
![Comanda](./imatgessprint4/13.png)  
Borrem un el disc i al fer la comanda per veure els detalls veurem que esta borrada. 
![Comanda](./imatgessprint4/16.png)  
Ara ens posarem a esborrar el raid amb les següents comandes.
![Comanda](./imatgessprint4/18.png)  
com podem veure no ho podem borrar facilment, i utilitzarem la comanda de `zero-superblock`.
![Comanda](./imatgessprint4/19.png)  
Com podem observar ja no tenim el raid.
![Comanda](./imatgessprint4/20.png)  


## RAID 5
En primer lloc creem 4 discos per fer el RAID 5.
![Comanda](./imatgessprint4/RAID5/1.png)
Podem observar el 4 discos que hem afegit.
![Comanda](./imatgessprint4/RAID5/2.png)

Aquest pas ho hem de fer amb els 4 discos.
![Comanda](./imatgessprint4/RAID5/3.png)

Compodem observar el pas anterior ens ha funconat correctament.
![Comanda](./imatgessprint4/RAID5/4.png)

Creem la carpeta que la anomenarem raid 5 i assignarem els permissos següents.
![Comanda](./imatgessprint4/RAID5/5.png)

Ara creem el Raid amb la següent comanda.
![Comanda](./imatgessprint4/RAID5/6.png)

Ara posem el format `ext4`
![Comanda](./imatgessprint4/RAID5/7.png)

Ara fem la comanda següent que mou tot lo de detalls al fitxer següent.
![Comanda](./imatgessprint4/RAID5/8.png)

En el fitxer agreguem les següent dades.
![Comanda](./imatgessprint4/RAID5/9.png)

En el fitxer `/etc/fstab` agregem el que esta subratllat a la següent imatge.
![Comanda](./imatgessprint4/RAID5/10.png)

Com podem veure al fer la següen comanda podem observar que tenim els 4 discos activats.
![Comanda](./imatgessprint4/RAID5/11.png)

Ara ens disposem a fer proves:
Creem arxius per poder fer proves amb funcionabilitat del raid
![Comanda](./imatgessprint4/RAID5/12.png)

Desactivem un disc i comprovem si encara tenim la informació i comprovem que encara tenim la informació.
![Comanda](./imatgessprint4/RAID5/13.png)

Seguiren fent proves fins que ens surtigue error i podem comprovar que el raid no pot funcionar solament amb dos discos.
Igualment ens el descativa pero el sistema ens dona una alerta.
![Comanda](./imatgessprint4/RAID5/14.png)

Creem un nou disc per pasar la informació a aquest.
![Comanda](./imatgessprint4/RAID5/14.png)

Amb la següent comanda traspassem les dades dels discs anteriors a aquest.
En el meu cas em dona un problema de superblock.
![Comanda](./imatgessprint4/RAID5/16.png)

Al fer els detalls podem observar que no tenim el raid ja que segurament se me ha petat.
![Comanda](./imatgessprint4/RAID5/17.png)

Ara finalmet esborrem el RAID 5, com anteriorment he borrat els dos discos manualment se ha petat i al esborrar el raid nomes se me han borrat 2 discos.
![Comanda](./imatgessprint4/19.png) 