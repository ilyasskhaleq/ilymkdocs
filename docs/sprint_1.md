# instal·lació i configuració inicial

## Instal·lació SO (Windows server)

En primer lloc instal·larem la iso que la podrem trobar en el seguent enllaç:

https://software-static.download.prss.microsoft.com/sg/download/888969d5-f34g-4e03-ac9d-1f9786c66749/SERVER_EVAL_x64FRE_es-es.iso

I creem la nova maquina amb la iso.

![Comanda](./Projecte2/Sprint1/111.png) 

Procedim a la configuració de la maquina.
![Comanda](./Projecte2/Sprint1/112.png) 

I installarem el servidor de Windows Server.
![Comanda](./Projecte2/Sprint1/113.png) 

Seleccionarem el sistema operatiu que volem instalar.
![Comanda](./Projecte2/Sprint1/114.png) 

Posem la instal·lació de personalització ja que podem seleccionar la partició on volem instal·lar el sistema operatiu.
![Comanda](./Projecte2/Sprint1/115.png) 

Selccionem la partició.
![Comanda](./Projecte2/Sprint1/116.png)

I esperem fins que s'instal·li el sistema operatiu.
![Comanda](./Projecte2/Sprint1/117.png) 

Al finalitzar la instal·lació, gestionarem la constrasenya de l'administrador del sistema operatiu.
![Comanda](./Projecte2/Sprint1/118.png) 

Finalemt ja el tenim instal·lat. 
Accedim:
![Comanda](./Projecte2/Sprint1/119.png) 

## Xarxa bàsica

Per configurar la xarxa estàtica hem de fer els seguents passos:

Accedim al menú de configuració.
![Comanda](./Projecte2/Sprint1/1110.png) 

Cliquem l'opció de cambiar opcions de red.
![Comanda](./Projecte2/Sprint1/1111.png) 

Al protocol de ipv4 seleccionem propietats.
![Comanda](./Projecte2/Sprint1/1112.png) 

I utilitzem la següent configuració d'IP.
![Comanda](./Projecte2/Sprint1/1113.png) 

Per accedir al terminal de windows fem la combinació de tecles Win + R i escribim: cmd.
![Comanda](./Projecte2/Sprint1/1114.png) 

Finalment realitzxem la següent comanda per poder visualitzar la ip del servidor. 
![Comanda](./Projecte2/Sprint1/1115.png) 


## Instal·lació SO (Windows 10)

Creem la nova maquina virtual i seleccionem la opció de windows 10.
![Comanda](./Projecte2/Sprint1/1.png) 

Seleccionem l'idioma.
![Comanda](./Projecte2/Sprint1/2.png) 

I instal·lem el sistema operatiu.
![Comanda](./Projecte2/Sprint1/3.png) 

Acceptem els termes i condiciones..
![Comanda](./Projecte2/Sprint1/4.png) 

Seleccionem l'opció personalitzada.
![Comanda](./Projecte2/Sprint1/5.png)

Seleccionem la partició.
![Comanda](./Projecte2/Sprint1/6.png) 

I espirem fins que s'instal·li el sistema operatiu.
![Comanda](./Projecte2/Sprint1/7.png)  

Rellenem amb el nostre nom.
![Comanda](./Projecte2/Sprint1/8.png)  

I podem observar que s'ha finalitzar la instal·lació i ja podeu entrar al sistema operatiu.
![Comanda](./Projecte2/Sprint1/9.png)  

## Punts de restauració

Accedim al panel de control de windows.
![Comanda](./Projecte2/Sprint1/10.png) 

Accedim a la ruta en el panel de control. I accedim a la part esquerra i nem a l'opció de protecció  del sistema.
![Comanda](./Projecte2/Sprint1/11.png)  

Com podem observar en surt que aquesta opció esta desactivada per defecte pero nosaltres com volem fer proves l'activarem.
![Comanda](./Projecte2/Sprint1/12.png)  

Seguidament posem en crear i haurem de posar un nom al punt de restauració que he posat la data d'avui.
![Comanda](./Projecte2/Sprint1/13.png)  

## VIRTUALITZACIÓ
En el buscador de windows volem buscar "Caracteristicas de windows".  
![Comanda](./Projecte2/Sprint1/14.png)

I busquem l'opció de Hyper-V
![Comanda](./Projecte2/Sprint1/15.png) 

La seleccionem i acceptem els canvis.
![Comanda](./Projecte2/Sprint1/16.png)  

I com podem veure ja tenim activat el Hyper-V.
![Comanda](./Projecte2/Sprint1/17.png)  

## GESTOR DE ARRENCADA (WINDOWS I UBUNTU)

En primer lloc en el següent programa creem una particio per poder instal·lar Ubuntu.
Cal configurar amb els següents parametres:
![Comanda](./Projecte2/Sprint1/27.png) 

Com podem observar tenim una partició que no esta assignada.
![Comanda](./Projecte2/Sprint1/28.png) 

Procedirem a configurar la partició.
![Comanda](./Projecte2/Sprint1/29.png) 


![Comanda](./Projecte2/Sprint1/30.png) 

Coloquem el tamany de la partició.
![Comanda](./Projecte2/Sprint1/31.png) 

Li assignem una lletra.
![Comanda](./Projecte2/Sprint1/32.png) 

I formateijem ambs les següents configuracions.
![Comanda](./Projecte2/Sprint1/33.png) 

Seguidament reiniciem i abanas de que inicie el windows cilquem la tecla `F12` i la lletra c.
![Comanda](./Projecte2/Sprint1/34.png) 

Seleccionem la primera opció
![Comanda](./Projecte2/Sprint1/35.png) 

I fem els pasos per instal·lar Ubuntu.
![Comanda](./Projecte2/Sprint1/36.png) 

En aquest apartat seleccionem que volem instal·lar Ubuntu amb windows.
![Comanda](./Projecte2/Sprint1/37.png) 

![Comanda](./Projecte2/Sprint1/38.png) 

I instal·lem.
![Comanda](./Projecte2/Sprint1/39.png) 

Cal recordar que es important tenir bona memoria base i tenir al menys 4 nuclis.
![Comanda](./Projecte2/Sprint1/40.png) 

![Comanda](./Projecte2/Sprint1/41.png) 

Finalment ja tenim instal·lat Ubuntu i Reiniciem.
![Comanda](./Projecte2/Sprint1/42.png) 

Al reiniciar podem observar que podem entrar amb ubuntu i windows.
![Comanda](./Projecte2/Sprint1/43.png) 

Com podem observar tenim el meu usuari de ubuntu.
![Comanda](./Projecte2/Sprint1/44.png) 



## COMANDES GENERALS
Accedim al terminal.
![Comanda](./Projecte2/Sprint1/18.png)  

La primera comanda que utilitzare es `dir` que mostra tots els fitxers i directoris de la carpeta actual.
![Comanda](./Projecte2/Sprint1/19.png)  

La següent comanda es `cls` que es per limpiar el terminal.
![Comanda](./Projecte2/Sprint1/20.png)  

La següent comanda es `cd` que es per entrar a un directori.
![Comanda](./Projecte2/Sprint1/21.png)  

La següent comanda es `mkdir` que es per crear un directori i també `rmdir` que es per eliminar un directori.  
![Comanda](./Projecte2/Sprint1/22.png)  


## Instal·lació aplicacions.

Per instal·lar apicacions necessitem instal·lar arxius `exe` que són aplicacions.  
En aquest cas nem a la pagina de Mozilla que tenim la pagina de instal·lació de aplicacions.
![Comanda](./Projecte2/Sprint1/23.png)  

I executem el paquet d'instal·lació.
![Comanda](./Projecte2/Sprint1/24.png)  

Seguim les instruccions fins descarregar l¡aplicació
![Comanda](./Projecte2/Sprint1/25.png) 

Finalement ja podem executar l'aplicació.
![Comanda](./Projecte2/Sprint1/26.png)  

