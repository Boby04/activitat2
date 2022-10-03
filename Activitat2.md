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








