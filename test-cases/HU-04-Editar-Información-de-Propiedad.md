# HU-04 – Editar Información de Propiedad

## Historia de usuario
**Como:** Agente inmobiliario  
**Quiero:** Editar los datos de una propiedad  
**Para:** Mantener la información actualizada en la web y en el sistema

---

## Criterios de aceptación

1. Debe visualizarse un botón **“Editar”** en la ficha de la propiedad.
2. El botón “Editar propiedad” debe redirigir al formulario de registro de propiedad.
3. El formulario de registro debe abrirse completado con los datos previamente cargados.
4. Se debe permitir editar los datos del formulario de registro de la propiedad.
5. Se debe permitir agregar nuevas imágenes.
6. Se debe permitir eliminar imágenes existentes.
7. Se debe permitir reemplazar imágenes existentes por otras.
8. El sistema debe solicitar confirmación antes de guardar los cambios.
9. El sistema debe impedir guardar cambios que generen una propiedad duplicada.
10. Si se eliminan todas las imágenes, no debe permitirse la continuidad de la publicación en la web.
11. Los cambios deben verse reflejados en la ficha de la propiedad.
12. Los cambios deben verse reflejados en la publicación del sitio web.

---

## Casos de prueba

### CP-01 – Visualizar botón Editar

**Tipo:** Funcional  
**Descripción:** Verificar que el botón "Editar" se muestre en la ficha de propiedad.
**Prioridad:** Media  
**Criterios cubiertos:** 1  

#### Precondiciones
- Usuario autenticado con rol Agente.
- Propiedad existente.

#### Tipo de caso
- Positivo

#### Datos de entrada
- N/A

#### Pasos
1. Acceder a la ficha de una propiedad existente.
2. Visualizar las acciones disponibles.

#### Resultado esperado
- Se visualiza el botón **“Editar”** en la ficha.

---

### CP-02 – Acceso al formulario de creación de propiedad
**Tipo:** Funcional  
**Descripción:** Verificar que el botón “Editar propiedad” redirija al formulario de registro con los datos de la propiedad precargados.  
**Prioridad:** Alta  
**Criterios cubiertos:** 2, 3

#### Precondiciones
- Usuario autenticado con rol Agente.  
- Existe una propiedad previamente creada.  

#### Tipo de caso
- Positivo

#### Datos de entrada
- N/A

#### Pasos
1. Iniciar sesión con cuenta de Agente.
2. Acceder al módulo de Propiedades.
3. Seleccionar una propiedad existente.
4. Seleccionar el botón “Editar propiedad”.

#### Resultado esperado
- El sistema redirige al formulario de edición.
- El formulario se muestra con los datos previamente cargados.

---

### CP-03 – Edición exitosa de datos de una propiedad
**Tipo:** Funcional  
**Descripción:**  Verificar que el sistema permita modificar los datos de una propiedad y que los cambios se reflejen en la ficha del sistema y de la página web.  
**Prioridad:** Alta  
**Criterios cubiertos:** 4, 8, 11, 12

#### Precondiciones
- Usuario autenticado con rol Agente.
- Existe una propiedad previamente creada.

#### Tipo de caso
- Positivo

#### Datos de entrada
- Título: Departamento Editado 1.
- Precio: 120000

#### Pasos
1. Acceder al formulario de edición de la propiedad.
2. Modificar uno o más campos del formulario.
3. Seleccionar “Guardar”.
4. Confirmar la acción.

#### Resultado esperado
- El sistema solicita confirmación antes de guardar los cambios.
- El sistema guarda los cambios correctamente.
- Los cambios se reflejan en la ficha de la propiedad.
- Los cambios se reflejan en la página web.

---

### CP-04 – Editar las imágenes de una propiedad.

**Tipo:** Funcional  
**Descripción:** Verificar que el sistema permita agregar, eliminar y reemplazar imágenes de una propiedad existente.  
**Prioridad:** Alta.  
**Criterios cubiertos:** 5, 6, 7 

#### Precondiciones
- Agente autenticado con rol Agente.
- Propiedad existente con imágenes cargadas.
  
#### Tipo de caso
- Positivo.
  
#### Datos de entrada
- Nueva imagen: nueva_img.jpg
- Imagen a eliminar: img1.jpg.
- Imagen de reemplazo: img2.jpg -> reemplazo_img.jpg

#### Pasos
1. Acceder al formulario de edición de la propiedad.  
2. Agregar una nueva imagen.  
3. Eliminar una imagen existente.  
4. Reemplazar una imagen por otra.  
5. Seleccionar “Guardar”.  
6. Confirmar la acción.  

#### Resultado esperado
- Las imágenes se actualizan correctamente.
- Los cambios se reflejan en la ficha de la propiedad.
- Los cambios se reflejan en la página web.

---

### CP-05 – Eliminar totdas las imágenes en propiedad publicada

**Tipo:** Funcional.  
**Descripción:** Verificar que el sistema no permita mantener publicada una propiedad en la web si se eliminan todas sus imágenes.  
**Prioridad:** Alta  
**Criterios cubiertos:** 10, 12

#### Precondiciones
- Usuario autenticado con rol Agente. 
- Propiedad publicada en la web con imágenes cargadas.

#### Tipo de caso
- Alternativo.

#### Datos de entrada
- N/A

#### Pasos
1. Acceder al formulario de edición de la propiedad.
2. Eliminar todas las imágenes existentes.
3. Seleccionar “Guardar”.
4. Confirmar la acción.

#### Resultado esperado
- El sistema desactiva la opción "Publicar en la web".
- El sistema deshabilita la opción "Publicar en la web"
- La propiedad deja de estar publicada en la página web.
- Los cambios se reflejan en la ficha de la propedad.

