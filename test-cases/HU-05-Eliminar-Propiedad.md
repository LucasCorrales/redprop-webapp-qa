# HU-05 – Eliminar Propiedad Inmobiliaria

## Historia de usuario
**Como:** Agente inmobiliario  
**Quiero:** Eliminar una propiedad  
**Para:** Quitarla del sistema y del sitio web cuando ya no esté disponible

---

## Criterios de aceptación

1. Debe visualizarse un botón **“Eliminar propiedad”** en la ficha de la propiedad.
2. Al seleccionar **“Eliminar propiedad”**, el sistema debe solicitar confirmación.
3. Si el usuario confirma la acción, la propiedad debe eliminarse del sistema y de la base de datos.
4. Si la propiedad estaba publicada, debe eliminarse también del sitio web.
5. El sistema debe mostrar el mensaje **“Propiedad eliminada correctamente”**.
6. El sistema debe redirigir al módulo de **Propiedades**.
7. Si el usuario cancela la acción, la propiedad no debe eliminarse.

---

## Casos de prueba

### CP-01 – Visualizar botón Eliminar propiedad

**Tipo:** Funcional  
**Descripción:** Verificar que el botón "Eliminar propiedad" se muestre en la ficha de propiedad.
**Prioridad:** Media  
**Criterios cubiertos:** 1  

#### Precondiciones
- Usuario autenticado con rol Agente.
- Propiedad existente no publicada en la web.

#### Tipo de caso
- Positivo

#### Datos de entrada
- N/A

#### Pasos
1. Acceder a la ficha de una propiedad existente.
2. Visualizar las acciones disponibles.

#### Resultado esperado
- Se visualiza el botón **“Eliminar propiedad”** en la ficha.

---

### CP-02 – Eliminación propiedad no publicada

**Tipo:** Funcional  
**Descripción:**  Verificar que el sistema permita eliminar correctamente una propiedad no publicada mediante el botón “Eliminar propiedad”.
**Prioridad:** Alta  
**Criterios cubiertos:** 2, 3, 5, 6

#### Precondiciones
- Usuario autenticado con rol Agente.
- Propiedad existente y publicada en la web.

#### Tipo de caso
- Positivo

#### Datos de entrada
- N/A

#### Pasos
1. Acceder al listado de propiedades. 
2. Seleccionar la ficha de una propiedad que no esté publicada en la página web.
3. Seleccionar **“Eliminar propiedad”**.
4. Confirmar la acción.

#### Resultado esperado
- El sistema solicita confirmación al seleccionar "Eliminar propiedad".
- El sistema elimina la propiedad del listado de propiedades.
- El usuario es redirigido al módulo de Propiedades.
- La propiedad deja de mostrarse en el listado de propiedades.
- El sistema muestra el mensaje **“Propiedad eliminada correctamente”**.
- La propiedad no se visualiza más en listados ni búsquedas.

---

### CP-03 – Eliminación de propiedad publicada

**Tipo:** Funcional  
**Descripción:**  Verificar que al seleccionar el botón "Eliminar propiedad" desde la ficha de una propiedad publicada en la página web, se elimine del sitio y del sistema.
**Prioridad:** Alta  
**Criterios cubiertos:** 3, 4, 5, 6, 7, 9  

#### Precondiciones
- Usuario autenticado con rol Agente.
- Propiedad existente y publicada en la web.

#### Tipo de caso
- Positivo

#### Datos de entrada
- N/A

#### Pasos
1. Acceder al listado de propiedades. 
2. Seleccionar la ficha de una propiedad que esté publicada en la página web.
3. Seleccionar **“Eliminar propiedad”**.
4. Confirmar la acción.

#### Resultado esperado
- El sistema solicita confirmación al seleccionar "Eliminar propiedad".
- El usuario es redirigido al módulo de Propiedades.
- El sistema elimina la propiedad del listado de propiedades.
- La propiedad deja de estar publicada en el sitio web.
- El sistema muestra el mensaje **“Propiedad eliminada correctamente”**.
- La propiedad no se visualiza más en listados ni búsquedas.

---

### CP-04 – Cancelar eliminación de propiedad

**Tipo:** Funcional  
**Descripción:**   
**Prioridad:** Baja 
**Criterios cubiertos:** 3, 8  

#### Precondiciones
- Usuario autenticado con rol Agente.
- Propiedad existente.

#### Tipo de caso
- Alternativo.

#### Datos de entrada
- N/A

#### Pasos
1. Acceder al listado de propiedades. 
2. Seleccionar la ficha de una propiedad.
3. Seleccionar **“Eliminar propiedad”**.
4. Cancelar la acción.

#### Resultado esperado
- El sistema cancela la operación.
- La propiedad no se elimina.
- El usuario permanece en la ficha de la propiedad.
