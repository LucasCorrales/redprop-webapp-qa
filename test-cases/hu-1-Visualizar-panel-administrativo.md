# HU-1 – Visualizar Panel Administrativo

## Historia de usuario
**Como:** Administrador  
**Quiero:** Acceder a un panel para la gestión de usuarios agentes  
**Para:** Gestionar a los usuarios agentes del sistema

---

## Criterios de aceptación

1. Al acceder con credenciales de Administrador, el sistema debe redirigir al Panel Administrativo.
2. Debe visualizarse la pestaña “Usuarios”.
3. Debe visualizarse la imagen de la Inmobiliaria.
4. Debe visualizarse el listado de Usuarios.
5. Las tarjetas de usuario deben mostrar la información:
   - Nombre
   - Mail
6. Debe visualizarse la barra de búsqueda.
7. Deben visualizarse los botones:
   - Crear usuario
   - Eliminar usuario
   - Editar usuario
8. Se debe poder navegar por el listado de usuarios mediante paginación numérica.
---

## Casos de prueba

### CP-01 – Visualización correcta del Panel Administrativo

**Tipo:** Funcional / Frontend  
**Descripción:** Verificar la correcta visualización y navegación del listado de usuarios en el Panel Administrativo.  
**Prioridad:** Alta  
**Criterios cubiertos:** 1, 2, 3, 4, 5, 6, 7, 8  

#### Precondiciones
- Usuario autenticado con rol Administrador.
- Existen usuarios cargados en el sistema.
  
#### Tipo de caso
- Positivo.

#### Datos de entrada
- Credenciales de usuario administrador válidas.
   
#### Pasos
1. Ingresar al sistema con una cuenta de administrador.
2. Seleccionar un número de página en la paginación del listado de usuarios.

#### Resultado esperado
- Se visualiza la pestaña "Usuarios".
- Se visualiza la imagen de Inmobiliaria.
- Se visualizan las tarjetas de usuario con la información:
   -Nombre
   -Mail
- Se visualiza la barra de búsqueda.
- Se visualizan los botones: 
   - Crear usuario  
   - Eliminar usuario  
   - Editar usuario  
- Al seleccionar un número de página, el sistema muestra el listado de usuarios correspondiente a la página seleccionada.

---

### CP-02 – Acceso al Panel Administrativo con usuario no autorizado
**Tipo:** Funcional / Seguridad  
**Tipo de caso:** Negativo  
**Prioridad:** Alta  
**Criterios cubiertos:** 1  

#### Precondiciones
- Usuario autenticado sin rol Administrador.

#### Tipo de caso
- Negativo.

#### Datos de entrada
- Credenciales válidas de un usuario sin permisos administrativos.

#### Pasos
1. Ingresar al sistema con una cuenta de rol Usuario.
2. Intentar acceder al Panel Administrativo.

#### Resultado esperado
- El sistema impide el acceso al Panel Administrativo.  
- El usuario es redirigido al sistema permitido según su rol.  
- No se visualiza la pestaña "Usuarios" ni las funcionalidades del rol administrador.  

