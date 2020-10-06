`ssh-keygen`

Pide ingresar ruta y nombre de la llave:
>Si se deja por defecto crea una llave en el directorio raíz del .ssh
llamada _id_rsa_, por conveniencia deberíamos renombrar a una más específica con lo que estamos haciendo.

Pide ingresar una "passphrase"
> **Se puede dejar en blanco**
>
>Si se agrega una, ssh va a pedirla cada vez que usemos la llave, es más segura
>pero si olvidamos la clave, perdemos la llave

Pide re-ingresar la "passphrase"


Normalmente el proveedor del VPS nos pedirá que ingresemos una llave pública, tenemos que ingresar la que 
termina en _.pub_

Si usamos la llave para ingresar a un servidor el comando sería

`ssh user@server -i path-to-key`

Para no estar escribiendo el anterior comando 'todas las veces' creamos un archivo dentro de la carpeta .ssh
llamado **config**, aquí estarán las directivas ssh para el server que configuremos
>
    ServerAliveInterval 120
    ServerAliveCountMax 3

    Host mi_vps_root
        HostName 167.99.230.69
	    User root
	    IdentityFile path-to-key
	    
Se llama al archivo desde el comando ssh pasando el Host indicado
`ssh mi_vps_root`

