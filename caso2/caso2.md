## CASO 2##
Mostrar la lista de vistas a las que tiene acceso un rol, enviar como condicion el nombre del rol [role](name)

-[role] rol (name)
-[module]module (name)
-[view] vista (name)

-- sql
SELECT 
    r.name AS rol,
    m.name AS modulo,
    v.name AS vista
FROM 
    role r
INNER JOIN role_module rm ON r.id = rm.role_id
INNER JOIN module m ON rm.module_id = m.id
INNER JOIN module_view mv ON m.id = mv.module_id
INNER JOIN view v ON mv.view_id = v.id
WHERE 
    r.name = 'nombre_del_rol'; 


## Resultados##


![consulta completa](/caso1/img/completo.png)
![consulta completa](/caso1/img/parcial.png)



Oscar Mauricio Areiza Paramo