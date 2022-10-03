# Instalación de Owncloud en Linux
En aquesta pàgina instal·laràs el servei owncloud al teu propi equip, per això instal·laràs i configuraràs LAMP i Owncloud.


## Instalar Apache
Instal·lem el servidor Apache:

![](OWN1.png)

Desactivem el llistat de directoris del servidor:

![](OWN2.png)

---------------------------------------------------------------------------------------------------------------------------------------------

## Instal·lem MariaDB

Instal·lem MariaDB:

![](OWN3.png)

I configurem la instal·lació:
*Quan fem aquesta comanda haurem de seleccionar aquestes opcions:*

- Deshabilitar usuaris anònims.
- Desactivar accés remot com a root.
- Eliminar les bases de dades de testeig i accedir-hi.
- Actualitzar les taules de privilegis.

![](OWN4.png)

![](OWN5.png)

Finalment reiniciem el servidor MariaDB:

- sudo systemctl restart mariadb.service` o `sudo service mariadb.service restart

---------------------------------------------------------------------------------------------------------------------------------------------
# Crear la base de dades d'owncloud

Entrem a MariaDB:

![](OWN6.png)

Creem la base de dades:

![](OWN7.png)

Creem un usuari anomenat ownclouduser amb una contrasenya que podria ser Admin1234:

![](OWN8.png)

Us donem accés a l'usuari a la base de dades creada:

![](OWN9.png)

Apliquem els canvis i sortim:

![](OWN10.png)

---------------------------------------------------------------------------------------------------------------------------------------------

# Instal·lar PHP i els seus mòduls necessaris

![](OWN11.png)

Actualitzem els paquets amb el repositori afegit:

![](OWN12.png)

Instal·lem PHP i els mòduls necessaris:
*Hem de tenir en compte els requisits d'Owncloud abans d'instal·lar els mòduls.*

![](OWN13.png)

Després de la instal·lació editem el fitxer php.ini i canviarem alguns valors:

![](OWN20.png)

*Els valors que hem de canviar són els següents:*

- file_uploads = On 
- allow_url_fopen = On 
- memory_limit = 256M 
- upload_max_filesize = 100M 
- display_errors = Off 
- date.timezone = Europe/Madrid

![](OWN14.png)

![](OWN15.png)

![](OWN16.png)

![](OWN17.png)

![](OWN18.png)

![](OWN19.png)


---------------------------------------------------------------------------------------------------------------------------------------------

# Instal·lem Owncloud

Descarreguem la darrera versió del programa i descomprimim els fitxers, a més movem els fitxers d'Owncloud a "/var/www/html/owncloud":

![](OWN21.png)

![](OWN22.png)

![](OWN23.png)

![](OWN24.png)

Canviem propietari i permisos dels directoris d'owncloud. www-data perquè els pugui fer servir Apache, 755 perquè els pugui executar i llegir qualsevol usuari de Linux:

![](OWN25.png)

![](OWN26.png)

---------------------------------------------------------------------------------------------------------------------------------------------

# Configura Apache

Configurarem Apache:

![](OWN27.png)

Hem de deixar un fitxer com el següent, però canviant el ServerName i el ServerAlias pels noms i àlies del nostre propi domini.

![](OWN28.png)



Habilitem owncloud i el mòdul rewrite:

![](OWN29.png)

Reiniciem Apache:

`sudo service Apache2 restart`


**A partir d'aquest moment podem accedir a owncloud des del navegador per això hem d'introduir la nostra IP seguida de "/owncloud" al mateix, per exemple si la nostra IP és 172.31.84.197 posarem al navegador 172.31.84.197/owncloud i podrem accedir al servei.**

**Ja al navegador creem un compte d'administració i posem les dades de MariaDB que hem configurat anteriorment.**

En el meu cas per verure quina es la meva IP he intrduït **ip a** i he trobat la meva IP.

![](OWN31.png)

Ara ja podem entra a Owncloud, entrem al nostre navegador i posem la nostra IP seguidament amb /owncloud i haurem de posar les dades que hem introduït a MARIADS

![](OWN32.png)

I finalment una vegada posem les dades haurem de obtindre aixó:

![](OWN33.png)








