# HU-02 – Crear Usuario Agente

## Historia de usuario
**Como:** Administrador  
**Quiero:** Crear un nuevo Usuario  
**Para:** Que pueda acceder y operar en el sistema.

---

## Criterios de aceptación

1. Debe visualizarse un botón “Crear usuario”.
2. Al seleccionar “Crear usuario”, debe redirigir al formulario de creación de usuario con los campos:
   - Nombre
   - Apellido
   - Email
   - Contraseña
3. Deben visualizarse los botones:
   - Guardar
   - Cancelar
4. El sistema debe validar los campos obligatorios:
   - Nombre
   - Apellido
   - Email
   - Contraseña
5. El sistema debe impedir la creación de usuarios con email duplicado.
6. El sistema debe solicitar confirmación antes de guardar el usuario.
7. Al confirmar, el usuario debe guardarse en la base de datos con el rol correspondiente (Agente).
8. El sistema debe mostrar el mensaje “Usuario creado” ante una creación exitosa.

---

### CP-01 – Acceso al formulario de creación de usuario

**Tipo:** Funcional  
**Descripción:** Verificar que el botón "Crear Usuario" redirija al formulario de creación de usuario.
**Prioridad:** Alta  
**Criterios cubiertos:** 1, 2

#### Precondiciones
- Usuario autenticado con rol Administrador.

#### Tipo de caso
- Positivo.

#### Datos de entrada
- N/A
   
#### Pasos
1. Iniciar sesión con cuenta de administrador.  
2. Seleccionar "Crear usuario".

#### Resultado esperado
- El botón "Crear Usuario" redirige al formulario de creación de usuario.

---

### CP-02 – Visualizar el formulario de registro

**Tipo:** Funcional  
**Descripción:** Verificar que el formulario de creación de usuario muestre todos los campos requeridos.  
**Prioridad:** Media  
**Criterios cubiertos:**  2  

#### Precondiciones
- Administrador autenticado.

#### Tipo de caso
- Positivo.

#### Datos de entrada
- N/A.

#### Pasos
1. Iniciar sesión con cuenta de administrador.  
2. Seleccionar "Crear usuario".  
3. Visualizar los campos del formulario:
   - Nombre
   - Apellido  
   - Email  
   - Contraseña  

#### Resultado esperado
- El formulario de registro para usuarios muestra todos los campos requeridos.

---

### CP-03 – Creación exitosa de usuario con rol Agente

**Tipo:** Funcional  
**Descripción:** Verificar que el sistema permita crear correctamente un nuevo usuario con rol Agente al completar los campos obligatorios y confirmar la acción.  
**Prioridad:** Alta  
**Criterios cubiertos:**  4, 6, 7, 8    

#### Precondiciones
- Usuario autenticado con rol Administrador.
- No debe existir un usuario con el email a utilizar.
  
#### Tipo de caso
- Positivo.

#### Datos de entrada
- Nombre: Agente
- Apellido: Prueba
- Email: agente@prueba.com
- Contraseña: prueba123

#### Pasos
1. Iniciar sesión con cuenta de administrador.  
2. Seleccionar el botón "Crear usuario".  
3. Llenar el formulario con datos válidos.  
4. Seleccionar el botón "Guardar".  
5. El sistema solicita confirmación.  
6. Seleccionar "Confirmar".  

#### Resultado esperado
- El sistema guarda el nuevo usuario correctamente.
- El usuario se registra en la base de datos con rol Agente.
- El sistema muestra el mensaje “Usuario creado”.
- El nuevo usuario se visualiza en el listado de usuarios.

---

- ### CP-04 – Crear cuenta Agente con datos inválidos

**Tipo:** Funcional  
**Descripción:** Validar que el sistema no permita registrar un nuevo usuario Agente cuando se completan los campos del formulario con datos inválidos.  
**Prioridad:** Alta  
**Criterios cubiertos:**  4

#### Precondiciones
- Usuario autenticado con rol Administrador.

#### Tipo de caso
- Negativo.

#### Datos de entrada
- Nombre: @gente  
- Apellido: Prueb@  
- Email: agenteprueba.com  
- Contraseña: prueba 123  

#### Pasos
1. Iniciar sesión con cuenta de administrador.  
2. Seleccionar "Crear usuario".  
3. Completar el formulario con datos inválidos.  
4. Seleccionar "Guardar".  
5. El sistema solicita confirmación.  
6. Seleccionar "Confirmar".

#### Resultado esperado
- El sistema muestra mensajes de error correspondientes para cada campo inválido.  
- El sistema impide la creación del usuario.

---

### CP-05 – Crear usuario Agente con datos duplicados.

**Tipo:** Funcional  
**Descripción:** Validar que el sistema no permita la creación de un usuario con un email ya registrado.  
**Prioridad:** Alta  
**Criterios cubiertos:**  5    

#### Precondiciones
- Administrador autenticado.  
- Debe existir previamente un usuario registrado con el email a utilizar.
  
#### Tipo de caso
- Negativo.

#### Datos de entrada
- Nombre: Agente
- Apellido: Prueba
- Email: agente@prueba.com (email ya existente)
- Contraseña: prueba123

#### Pasos
1. Iniciar sesión con cuenta de administrador.  
2. Seleccionar "Crear usuario".  
3. Llenar los campos del formulario con datos duplicados.  
4. Seleccionar "Guardar".
5. El sistema solicita confirmación.  
6. Seleccionar "Confirmar". 

#### Resultado esperado
- El sistema muestra mensaje de error.
- El sistema no crea al usuario ni lo muestra en el listado.

---

### CP-06 – Cancelar creación de cuenta Agente

**Tipo:** Funcional  
**Descripción:** Validar que el sistema descarte la operación de creación de usuario cuando se selecciona la opción "Cancelar".  
**Prioridad:** Baja  

#### Precondiciones
- Usuario autenticado con rol Administrador.

#### Tipo de caso
- Alternativo.

#### Datos de entrada
- Datos válidos ingresados en el formulario de creación de usuario.

#### Pasos
1. Iniciar sesión con cuenta de administrador.  
2. Seleccionar "Crear usuario".  
3. Completar el formulario con datos válidos.  
4. Seleccionar "Cancelar".

#### Resultado esperado
- El sistema descarta los datos ingresados.  
- El usuario no es creado ni registrado en el sistema.

--- 

## CP-BE-01 – Creación exitosa de usuario Agente

**Tipo:** Funcional – Backend  
**Descripción:** Verificar que la API permita crear correctamente un usuario con rol Agente cuando se envían datos válidos.  
**Prioridad:** Alta  
**Criterios cubiertos:** 4, 7  

#### Precondiciones
- Usuario autenticado con rol Administrador.  
- Token de sesión válido.  
- No debe existir un usuario con el email informado.  

#### Tipo de caso
- Positivo  

#### Endpoint
- POST /users  

#### Datos de entrada (Body)
{  
  "first_name": "Agente",  
  "last_name": "Prueba",  
  "email": "agente@prueba.com",  
  "password": "prueba123"  
}

#### Pasos
1. Realizar una petición POST al endpoint /users.  
2. Enviar el body con datos válidos.  
3. Observar la respuesta de la API.  

#### Resultado esperado
- Código de respuesta 201 Created.  
- La respuesta incluye un ID de usuario generado.  
- El usuario se guarda correctamente en la base de datos.  
- El rol asignado al usuario es Agente.  

---

## CP-BE-02 – Intento de creación con email duplicado

**Tipo:** Funcional – Backend  
**Descripción:** Verificar que la API impida la creación de un usuario con un email ya registrado.  
**Prioridad:** Alta  
**Criterios cubiertos:** 5  

#### Precondiciones
- Usuario autenticado con rol Administrador.  
- Token de sesión válido.  
- Debe existir previamente un usuario registrado con el email enviado.  

#### Tipo de caso
- Negativo  

#### Endpoint
- POST /users  

#### Datos de entrada (Body)

{  
  "first_name": "Agente Duplicado",  
  "last_name": "Prueba",  
  "email": "agente@prueba.com",  
  "password": "prueba123"  
}

#### Pasos
1. Realizar una petición POST al endpoint /users.  
2. Enviar el body con un email ya existente.  
3. Observar la respuesta de la API.  

#### Resultado esperado
- Código de respuesta 400 Bad Request o 409 Conflict.  
- Mensaje indicando que el email ya se encuentra registrado.  
- El usuario no se guarda en la base de datos.  

---

## CP-BE-03 – Intento de creación con campos obligatorios faltantes

**Tipo:** Funcional – Backend
**Descripción:** Verificar que la API no permita crear un usuario cuando faltan campos obligatorios.  
**Prioridad:** Alta  
**Criterios cubiertos:** 4  

#### Precondiciones
- Usuario autenticado con rol Administrador.  
- Token de sesión válido.  

#### Tipo de caso
- Negativo  

#### Endpoint
- POST /users  

#### Datos de entrada (Body)

{  
  "first_name": "",  
  "last_name": "",  
  "email": "",  
  "password": ""  
}

#### Pasos
1. Realizar una petición POST al endpoint /users.  
2. Enviar el body con campos obligatorios vacíos o nulos.  
3. Observar la respuesta de la API.  

#### Resultado esperado
- Código de respuesta 400 Bad Request.  
- Mensaje indicando los campos obligatorios faltantes.  
- El usuario no se guarda en la base de datos.  
