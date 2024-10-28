## Caso 3
Mostar la lista roles a los que tiene una persona tiene acceso. Recordar que cada rol tiene una lista de modulos asociados, y a su vez, un modulo puede tener varias vistas.  Para mostrar dicha información, se requiere enviar [user](username, password). En caso que el usuario y la contraseña no coinsida, no se muestra la información.

[user] usuario(username)
[role] rol(name)
[module] modulo(name)
[view] vista[name]


--sql
SELECT 
    r.name AS rol,
    m.name AS modulo,
    v.name AS vista
FROM 
    user u
INNER JOIN person p ON u.person_id = p.id
INNER JOIN user_role ur ON u.id = ur.user_id
INNER JOIN role r ON ur.role_id = r.id
INNER JOIN role_module rm ON r.id = rm.role_id
INNER JOIN module m ON rm.module_id = m.id
INNER JOIN module_view mv ON m.id = mv.module_id
INNER JOIN view v ON mv.view_id = v.id
WHERE 
    u.username = 'nombre_de_usuario'  -- Reemplaza con el nombre de usuario
    AND u.password = 'contraseña';     -- Reemplaza con la contraseña correcta


## Resultados


Oscar Mauricio Areiza Paramo