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
6. Debe visualizarse un botón **“Guardar”**.  
7. Al seleccionar **“Guardar”**, la propiedad debe guardarse correctamente en el sistema y en la base de datos.  
8. Si no hay imágenes cargadas, la opción **“Publicar en la web”** debe permanecer deshabilitada.  
9. Al cargar al menos una imagen, la opción **“Publicar en la web”** debe habilitarse.  
10. Si se activa la opción **“Publicar en la web”** y se selecciona **"Guardar"**, la propiedad debe ser publicada en el sitio web y debe guardarse en el sistema y en la base de datos.
11. El sistema debe mostrar el mensaje **“Propiedad creada correctamente”**.  
12. El sistema debe redirigir a la ficha de la propiedad recién creada.  
13. Debe visualizarse un botón **“Cancelar”**.  
14. Al seleccionar **“Cancelar”**, el sistema debe descartar la operación y redirigir al módulo de Propiedades.

---

## Casos de prueba

### CP-01 – Acceso al formulario de creación de propiedad
**Tipo:** Funcional  
**Descripción:** Verificar que el usuario pueda acceder al formulario de creación de propiedad y visualizar todos los campos y acciones disponibles.   
**Prioridad:** Alta  
**Criterios cubiertos:** 2, 3, 6, 13  

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
- El botón **"Crear Propiedad"** redirige al formulario de creación de propiedad.  
- Se visualizan correctamente todos los campos del formulario.
- Se visualiza el botón **"Guardar"**
- Se visualiza el botón **"Cancelar"**
  
---

### CP-02 – Creación exitosa de propiedad sin imágenes y sin publicación web
**Tipo:** Funcional  
**Descripción:**  Verificar que, al crear una propiedad sin cargar imágenes, la opción 
**“Publicar en la web”** permanezca deshabilitada y la propiedad se guarde correctamente 
en el sistema sin ser publicada en la web.
**Prioridad:** Alta  
**Criterios cubiertos:** 6, 7, 8, 12  

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
- Imágenes: N/A
  
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

### CP-03 - Creación y publicación en web exitosa de propiedad con imágenes

**Tipo:** Funcional  
**Descripción:** Verificar que, al cargar al menos una imagen y activar la opción 
**“Publicar en la web”**, la propiedad se guarde correctamente en el sistema y sea publicada 
en el sitio web.
**Prioridad:** Alta   
**Criterios cubiertos:** 9, 10

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

### CP-04 - Crear propiedad con campos obligatorios incompletos
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

### CP-05 - Cancelar creación de propiedad

**Tipo:** Funcional  
**Descripción:** Verificar que al seleccionar la opción **"Cancelar"**, el sistema descarte la información ingresada y redirija al módulo de propiedades.
**Prioridad:** Media   
**Criterios cubiertos:** 13, 14

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
