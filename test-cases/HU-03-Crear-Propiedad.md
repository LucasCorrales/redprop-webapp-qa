# HU-03 – Crear Propiedad Inmobiliaria

## Historia de usuario
**Como:** Agente inmobiliario  
**Quiero:** Cargar los datos de una propiedad  
**Para:** Publicarla en la web o registrarla en mi inventario

---

## Criterios de aceptación

1. Debe visualizarse un botón **“Crear Propiedad”** en el menú de navegación.  
2. Al seleccionar “Crear propiedad”, debe abrirse un formulario con los campos:
   - Título de la propiedad  
   - Provincia  
   - Ciudad  
   - Tipo de propiedad  
   - Dirección  
   - Precio  
   - Imágenes de la propiedad  
   - Estado de publicación  
3. El sistema debe validar los campos obligatorios.  
4. Si faltan campos obligatorios, el sistema debe mostrar un mensaje indicando cuáles faltan.  
5. Debe visualizarse un botón **“Guardar”**.  
6. Al seleccionar **“Guardar”**, la propiedad debe guardarse correctamente en el sistema y en la base de datos.  
7. Si no hay imágenes cargadas, la opción **“Publicar en la web”** debe permanecer deshabilitada.  
8. Al cargar al menos una imagen, la opción **“Publicar en la web”** debe habilitarse.  
9. Si se activa la opción **“Publicar en la web”** y se selecciona **"Guardar"**, la propiedad debe ser publicada en el sitio web y debe guardarse en el sistema y en la base de datos.
10. El sistema debe mostrar el mensaje **“Propiedad creada correctamente”**.  
11. El sistema debe redirigir a la ficha de la propiedad recién creada.  
12. Debe visualizarse un botón **“Cancelar”**.  
13. Al seleccionar **“Cancelar”**, el sistema debe descartar la operación y redirigir al módulo de Propiedades.

---

## Casos de prueba

### CP-01 – Visualizar botón Crear Propiedad

**Tipo:** Funcional  
**Descripción:** Verificar que el botón "Crear Propiedad" se muestre en el menú de navegación.
**Prioridad:** Media  
**Criterios cubiertos:** 1  

#### Precondiciones
- Usuario autenticado con rol Agente.

#### Tipo de caso
- Positivo

#### Datos de entrada
- N/A

#### Pasos
1. Acceder al sistema.
2. Visualizar las acciones disponibles del menú de navegación.

#### Resultado esperado
- Se visualiza el botón **“Crear Propiedad”**.

---

### CP-02 – Acceso al formulario de creación de propiedad
**Tipo:** Funcional  
**Descripción:** Verificar que el usuario pueda acceder al formulario de creación de propiedad y visualizar todos los campos y acciones disponibles.   
**Prioridad:** Alta  
**Criterios cubiertos:** 2, 5, 12 

#### Precondiciones
- Usuario autenticado con rol Agente.

#### Tipo de caso
- Positivo.

#### Datos de entrada
- N/A

#### Pasos
1. Iniciar sesión con cuenta de Agente.  
2. Seleccionar el botón **“Crear propiedad”** del menú de navegación.

#### Resultado esperado
- El botón **"Crear Propiedad"** redirige al formulario de creación de propiedad.  
- Se visualizan correctamente todos los campos del formulario.
- Se visualiza el botón **"Guardar"**
- Se visualiza el botón **"Cancelar"**
  
---

### CP-03 – Creación exitosa de propiedad sin imágenes y sin publicación web
**Tipo:** Funcional  
**Descripción:**  Verificar que, al crear una propiedad sin cargar imágenes, la opción 
**“Publicar en la web”** permanezca deshabilitada y la propiedad se guarde correctamente 
en el sistema sin ser publicada en la web.
**Prioridad:** Alta  
**Criterios cubiertos:** 5, 6, 7, 11  

#### Precondiciones
- Usuario autenticado con rol Agente.

#### Tipo de caso
- Positivo.

#### Datos de entrada
- Título: Departamento 2 ambientes  
- Provincia: Buenos Aires  
- Ciudad: La Plata  
- Tipo: Departamento  
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

### CP-04 - Creación y publicación en web exitosa de propiedad con imágenes

**Tipo:** Funcional  
**Descripción:** Verificar que, al cargar al menos una imagen y activar la opción 
**“Publicar en la web”**, la propiedad se guarde correctamente en el sistema y sea publicada 
en el sitio web.
**Prioridad:** Alta   
**Criterios cubiertos:** 8, 9

#### Precondiciones
- Usuario autenticado con rol Agente.

#### Tipo de caso
- Positivo.

#### Datos de entrada
- Título: Casa 4 ambientes 
- Provincia: Buenos Aires  
- Ciudad: La Plata  
- Tipo: Casa  
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

### CP-05 - Crear propiedad con campos obligatorios incompletos
**Tipo:** Funcional  
**Descripción:** Verificar que el sistema no permita la creación de una propiedad si los campos obligatorios no fueron llenados.
**Prioridad:** Alta  
**Criterios cubiertos:** 3, 4

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

### CP-06 - Cancelar creación de propiedad

**Tipo:** Funcional  
**Descripción:** Verificar que al seleccionar la opción **"Cancelar"**, el sistema descarte la información ingresada y redirija al módulo de propiedades.
**Prioridad:** Media   
**Criterios cubiertos:** 12, 13

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

## Casos de prueba Backend (API)

### CP-BE-01 – Creación exitosa de propiedad no publicada

**Tipo:** Funcional – Backend (API)  
**Descripción:**  
**Prioridad:** Alta  

#### Precondiciones
- Usuario autenticado con rol Agente.
- Token de sesión válido.

#### Tipo de caso
- Positivo

#### Endpoint
- POST /properties

#### Datos de entrada (Body)
{
  "title": "Departamento Sin Imágenes",  
  "province": "Ciudad Autónoma de Buenos Aires",  
  "city": "CABA",  
  "property_type": "Departamento",  
  "street": "Avenida de Prueba 12345",  
  "price": 75000,  
  "images": [],  
  "featured_web": false  
}

#### Pasos
1. Realizar una petición POST al endpoint /properties.
2. Enviar el body con todos los campos obligatorios completos.
3. No enviar imágenes.
4. Enviar la opción publicar en web como false.
5. Observar la respuesta de la API.

#### Resultado esperado
- Código de respuesta 201 Created.
- La respuesta incluye un ID de propiedad generado.
- La propiedad se guarda en la base de datos.
- El estado de publicación queda como no publicada.
- No se genera publicación en el sitio web.
  
---

### CP-BE-02 – Creación y publicación exitosa de propiedad con imágenes

**Tipo:** Funcional – Backend  
**Descripción:**   
**Prioridad:** Alta  

#### Precondiciones
- Usuario autenticado con rol Agente.
- Token de sesión válido.

#### Tipo de caso
- Positivo

#### Endpoint
- POST /properties
 
#### Datos de entrada (Body)
{
  "title": "Departamento Con Imágenes",  
  "province": "Ciudad Autónoma de Buenos Aires",  
  "city": "CABA",  
  "property_type": "Departamento",  
  "street": "Avenida Testing 12345",  
  "price": 95000,  
  "images": ["img1.jpg"],  
  "featured_web": true  
}

#### Pasos
1. Realizar una petición POST al endpoint /properties.
2. Enviar el body con datos válidos.
3. Adjuntar al menos una imagen.
4. Enviar la opción publicar en web como true.
5. Observar la respuesta de la API.

#### Resultado esperado
- Código de respuesta 201 Created.
- La respuesta incluye el ID de la propiedad.
- La propiedad se guarda en la base de datos.
- La propiedad queda marcada como publicada.
- La publicación queda disponible en el sitio web.

---

### CP-BE-03 – Intento de crear propiedad con campos obligatorios faltantes

**Tipo:** Funcional - BackEnd  
**Descripción:**   
**Prioridad:** Alta  

#### Precondiciones
- Usuario autenticado con rol Agente.  
- Token de sesión válido.  

#### Tipo de caso
- Negativo

#### Endpoint
- POST /properties

#### Datos de entrada (Body)
{
  "title": "",  
  "province": "",  
  "city": "",  
  "property_type": "",  
  "street": "",  
  "price":,  
  "images": [],  
  "featured_web":  
}

#### Pasos
1. Realizar una petición POST al endpoint /properties.
2. Enviar el body con uno o más campos obligatorios faltantes.
3. Observar la respuesta de la API.

#### Resultado esperado
- Código de respuesta 400 Bad Request.
- Mensaje indicando los campos obligatorios faltantes.
- La propiedad no se guarda en la base de datos.

---

### CP-BE-04 – Intento de publicar propiedad sin imágenes

**Tipo:** Funcional - BackEnd  
**Descripción:**  
**Prioridad:** Media

#### Precondiciones
- Usuario autenticado con rol Agente.
- Token de sesión válido.

#### Tipo de caso
- Negativo

#### Endpoint
- POST /properties

#### Datos de entrada (Body)
{
  "title": "Casa Publicada Sin Imágen",  
  "province": "Ciudad Autónoma de Buenos Aires",  
  "city": "CABA",  
  "property_type": "Casa",  
  "street": "Prueba 123456",  
  "price": 150000,  
  "images": [],  
  "featured_web": true  
}

#### Pasos
1. Realizar una petición POST al endpoint **/properties**.
2. Enviar el body solicitando publicación sin imágenes.
3. Observar la respuesta de la API.

#### Resultado esperado
- Código de respuesta 400 Bad Request o 422 Unprocessable Entity.
- Mensaje indicando que no se puede publicar una propiedad sin imágenes.
- La propiedad no se publica en la web.
