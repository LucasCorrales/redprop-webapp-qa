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
**Descripción:** Verificar que se visualicen todas las funciones e información del Panel Administrativo.
**Prioridad:** Alta  
**Criterios cubiertos:** 1, 2, 3, 4, 5, 6, 7, 8

#### Precondiciones
- Usuario autenticado con rol Administrador.
  
**Tipo de caso** 
- Positivo

#### Datos de entrada
-Credenciales de usuario administrador válidas.

#### Pasos
1. Ingresar al sistema con una cuenta de administrador.

#### Resultado esperado
- Se visualiza la pestaña "Usuarios".
- Se visualiza la imagen de Inmobiliaria.
- Se visualizan las tarjetas de usuario con la información:
   -Nombre
   -Mail
-Se visualiza la barra de búsqueda
- Se visualizan los botones: 
   -Crear usuario
   -Eliminar usuario
   -Editar usuario
