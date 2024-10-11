Práctica3    COMANDO DIG 

1

Se lleva a cabo una consulta de tipo DNS empleando el comando DIG para el dominio específico "danielcastelao.org".
El comando DIG lleva a cabo al acción de resolución de nombres de dominio categorizando la información vinculada .
Se muestran varios campos asociados a la respuesta de la consulta .

- QUERY SECTION .....   nombre de dominio más el tipo de registro (busca la ip asociada la dominio)

- HEADER ..... información sobre la consulta ( identificadores, etc)

- ANSWER SECTION ..... se ofrecen todos los registros encontrados

- AUTHORITY SECTION ..... se hace referencia a los servidores autoritativos del dominio

- ADDITIONAL SECTION ..... datos de carácter adicional

- OPT PSEUDOSECTION .....  información asociada a las extendiones de DNS



2

El tipo de registro asociado a ambas direcciones puede ser una de las diferencias posibles 




3


Obtenemos el nombre IP de los servidores autoritativos para la dirección www.danielcastelao.org

dig NS danielcastelao.org
