## Práctica3    COMANDO DIG 


*******


### 1


Se lleva a cabo una consulta de tipo DNS empleando el comando DIG para el dominio específico "danielcastelao.org".
El comando DIG lleva a cabo la acción de resolución de nombres de dominio categorizando la información vinculada .
Se muestran varios campos asociados a la respuesta de la consulta .


- _**QUERY SECTION**_ .....   nombre de dominio más el tipo de registro (busca la ip asociada la dominio)

- _**HEADER**_ ..... información sobre la consulta ( identificadores, etc)

- _**ANSWER SECTION**_ ..... se ofrecen todos los registros encontrados

- _**AUTHORITY SECTION**_ ..... se hace referencia a los servidores autoritativos del dominio

- _**ADDITIONAL SECTION**_ ..... datos de carácter adicional

- _**OPT PSEUDOSECTION**_ .....  información asociada a las extendiones de DNS




### 2



El tipo de registro asociado a ambas direcciones puede ser una de las diferencias posibles 




### 3



Obtenemos el nombre IP de los servidores autoritativos para la dirección www.danielcastelao.org.


```**dig NS danielcastelao.org**```


En la sección de AUTHORITY SECTION se puede obtener la informnación de los DNS autoritativos vinculados .
Lo habitual es que sean varios los que aparecen ya que se intenta siempre generar distribución  de carga y redundancia 



### 4



Con la opción -x , el comando dig permite realizar la operación de resolución de una IP particular a un nombre de dominio . Para el caso particular. 


```**dig -x  130.206.164.68**```


Otras IPs que se pueden ulizar para ejemplificar la acción asociada al parámetro del comando son.

```**dig -x 8.8.8.1**```
```**dig -x 8.8.4.3**```



### 5



Para obtener el nombre del servidor al que se está haciendo consultas 


```**cat /etc/resolv.conf**```


En este archivo se puede obtener los nombres de los servidores DNS asociados al sistema 




### 6



EL registro SOA ofrece información sobre la zona DNS y el servidor principal 


Para el caso de _danielcastelao.org_

```**dig NS danielcastelao.org**```

Se emplea posteriormente uno de los servidores autoritativos que se ofrecen 

```**dig @<nombre_servidor autoritativo> SOA moodle.danielcastelao.org**```


Para consultar el servidor de Google 


```**dig @8.8.8.8 SOA moodle.danielcastelao.org**```




### 7



Empleamos 


```**dig www.elpais.com**```


En el apartado de ANSWER SECTION se encuentra el campo TTL , que hacer referencia al tiempo que el registro determinado estará almacenado en la caché del servidor DNS (medido en unidades de segundos)

El TTL va cambiando su valor dependiendo del instante en el que se haga la consulta , siempre con carácter decreciente



### 8


La diferencia que puede existir en el valor TTL de difentes dominios pueden deberse a la implementación de diferentes políticas de cacheo. Las consultas se hacen con el comando dig 



### 9



Sin pasar por cachés intermedias , se puede consultar el valor de   TTL vinculado a un registro .


```**dig @<nombre_servidorautoritativo> dominio.com**```




### 10



Para ver las IPs del dominio solicitado 


```**dig www.google.es**``` 

Las múltiples IPs se deben a una intención de generar un balanceo de carga , pudiendo variar en función de la localización del equipo local , momento del dia , etc





### 11



La realización de una consulta a un servidor raiz 


```**dig   @j.root-server.net www.google.es**```





### 12



Con el objeto de ver todas las consultas del servidor DNS 



```**dig +trace www.timesonline.co.uk**```





### 13




Se obtiene los registros _MX_  el cual aporta información asociada a los servidores de correo de un dominio en específico


```**dig MX danielcastelao.org**```





### 14



Se obtienen los registros de IPv6 de _www.facebook.com_




```**dig AAAA www.facebook.com**``` 











