# HU-3 – Crear Propiedad Inmobiliaria

## Historia de usuario
**Como:** Agente inmobiliario  
**Quiero:** Cargar los datos de una propiedad  
**Para:** Publicarla en la web o registrarla en mi inventario

---

## Criterios de aceptación

1. El usuario debe estar autenticado con rol **Agente**.  
2. Debe visualizarse un botón **“Crear propiedad”**.  
3. Al seleccionar “Crear propiedad”, debe abrirse un formulario con los campos:
   - Título de la propiedad  
   - Provincia  
   - Ciudad  
   - Tipo de propiedad  
   - Dirección  
   - Precio  
   - Imágenes de la propiedad  
   - Estado de publicación  
4. El sistema debe validar los campos obligatorios.  
5. Si faltan campos obligatorios, el sistema debe mostrar un mensaje indicando cuáles faltan.  
6. El botón **“Guardar”** debe estar disponible.  
7. Al seleccionar **“Guardar”**, la propiedad debe guardarse correctamente en el sistema y en la base de datos.  
8. Si no hay imágenes cargadas, la opción **“Publicar en la web”** debe permanecer deshabilitada.  
9. Si se carga al menos una imagen, la opción **“Publicar en la web”** debe habilitarse.  
10. Si se activa la opción **“Publicar en la web”** y se selecciona **"Guardar"**, la propiedad debe ser publicada en el sitio web y debe guardarse en el sistema y en la base de datos.
11. El sistema debe mostrar el mensaje **“Propiedad creada correctamente”**.  
12. El sistema debe redirigir a la ficha de la propiedad recién creada.  
13. Debe visualizarse un botón **“Cancelar”**.  
14. Al seleccionar **“Cancelar”**, el sistema debe descartar la operación y redirigir al módulo de Propiedades.

---

## Casos de prueba

### CP-01 – Acceso al formulario de creación de propiedad
**Tipo:** Funcional  
**Descripción:** Verificar que el botón "Crear Propiedad" redirija al formulario de creación de propiedad con todos sus campos.    
**Prioridad:** Alta  
**Criterios cubiertos:** 2, 3  

#### Precondiciones
- Usuario autenticado con rol Agente.

#### Tipo de caso
- Positivo.

#### Datos de entrada
- N/A

#### Pasos
1. Iniciar sesión con cuenta de Agente.  
2. Seleccionar el botón **“Crear propiedad”**.

#### Resultado esperado
- El botón "Crear Propiedad" redirige al formulario de creación de propiedad.  
- Se visualizan todos los campos del formulario.

---

### CP-02 – Creación existosa de propiedad sin publicar en la web
**Tipo:** Funcional  
**Descripción:** Verificar que la propiedad se guarde en el sistema pero no se publique en la web, si la opción "Publicar en la web" no es seleccionada.   
**Prioridad:** Alta  
**Criterios cubiertos:** 4, 6, 7, 8, 9, 12  

#### Precondiciones
- Usuario autenticado con rol Agente.

#### Tipo de caso
- Positivo.

#### Datos de entrada
- Título: Departamento 2 ambientes  
- Provincia: Buenos Aires  
- Ciudad: La Plata  
- Tipo de propiedad: Departamento  
- Dirección: Calle 12 N°123  
- Precio: 85000  
- Imágenes: No cargadas
  
#### Pasos
1. Acceder al formulario de creación de propiedad.
2. Completar los campos obligatorios.
3. Verificar que la opción **“Publicar en la web”** se encuentre deshabilitada.
4. Seleccionar **“Guardar”**.
   
#### Resultado esperado
- La propiedad se guarda en el sistema.  
- La propiedad no es publicada en la web.  
- El sistema muestra el mensaje **“Propiedad creada correctamente”**.  
- El sistema redirige a la ficha de la propiedad.  

---

### CP-03 - Crear propiedad con campos obligatorios incompletos
**Tipo:** Funcional  
**Descripción:** Verificar que el sistema no permita la creación de una propiedad si los campos obligatorios no fueron llenados.
**Prioridad:** Alta  
**Criterios cubiertos:** 4, 5

#### Precondiciones
- Usuario autenticado con rol Agente.

#### Tipo de caso
- Negativo.

#### Datos de entrada
- N/A
  
#### Pasos
1. Acceder al formulario de creación de propiedad.
2. Completar parcialmente los campos obligatorios.
3. Seleccionar **“Guardar”**.
   
#### Resultado esperado
- El sistema muestra mensajes indicando los campos obligatorios faltantes.
- La propiedad no es creada.

---

### CP-04 - Cancelar creación de propiedad

**Tipo:** Funcional  
**Descripción:** Verificar que al seleccionar la opción "Cancelar", el sistema descarte la información ingresada y redirija al módulo de propiedades.
**Prioridad:** Media   
**Criterios cubiertos:** 10, 11

#### Precondiciones
- Usuario autenticado con rol Agente.

#### Tipo de caso
- Alternativo.

#### Datos de entrada
- N/A
  
#### Pasos
1. Acceder al formulario de creación de propiedad.
2. Completar uno o más campos del formulario.
3. Seleccionar **“Cancelar”**.
   
#### Resultado esperado
- El sistema descarta los datos ingresados.
- El usuario es redirigido al módulo de Propiedades.
- La propiedad no es creada.

---

### CP-05 - Publicación exitosa de propiedad con imágenes

**Tipo:** Funcional  
**Descripción:** Verificar que al activar la opción **"Publicar en la web"**, la propiedad creada se guarde en el sistema y se publique en la web.
**Prioridad:** Ata   
**Criterios cubiertos:** 12, 13, 14

#### Precondiciones
- Usuario autenticado con rol Agente.

#### Tipo de caso
- Positivo.

#### Datos de entrada
- Título: Casa 4 ambientes 
- Provincia: Buenos Aires  
- Ciudad: La Plata  
- Tipo de propiedad: Casa  
- Dirección: Calle 11 N°123  
- Precio: 125000  
- Imágenes: img1.jpg, img2.jpg, img3.jpg
  
#### Pasos
1. Acceder al formulario de creación de propiedad.
2. Completar los campos obligatorios con datos válidos.
3. Cargar al menos una imagen de la propiedad.
4. Activar la opción **“Publicar en la web”**.
5. Seleccionar **“Guardar”**.
   
#### Resultado esperado
- La opción **"Publicar en la web"** se habilita al cargar imágenes.
- La propiedad se guarda en el sistema.
- La propiedad es publicada en el sitio web.
- El sistema muestra el mensaje **“Propiedad creada correctamente”**.
  
---
