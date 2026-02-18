# HU-04 – Editar Información de Propiedad

## Historia de usuario
Como: Agente inmobiliario  
Quiero: Editar los datos de una propiedad  
Para: Mantener la información actualizada en la web y en el sistema

---

## Criterios de aceptación

1. El botón “Editar propiedad” debe redirigir al formulario de registro de propiedad.
2. El formulario de registro debe abrirse completado con los datos previamente cargados.
3. Se debe permitir editar los datos del formulario de registro de la propiedad.
4. Se debe permitir agregar nuevas imágenes.
5. Se debe permitir eliminar imágenes existentes.
6. Se debe permitir reemplazar imágenes existentes por otras.
7. El sistema debe solicitar confirmación antes de guardar los cambios.
8. El sistema debe impedir guardar cambios que generen una propiedad duplicada.
9. Si se eliminan todas las imágenes, no debe permitirse la continuidad de la publicación en la web.
10. Los cambios deben verse reflejados en la ficha de la propiedad.
11. Los cambios deben verse reflejados en la publicación del sitio web.

---


## Casos de prueba


### CP-01 – Acceso al formulario de creación de propiedad
**Tipo:** Funcional 
**Descripción:** Verificar que el botón “Editar propiedad” redirija al formulario de registro con los datos de la propiedad precargados.  
**Prioridad:** Alta
**Criterios cubiertos:** 1, 2

#### Precondiciones
- Usuario autenticado con rol Agente.
- Existe una propiedad previamente creada.

#### Tipo de caso
- Positivo

#### Datos de entrada
N/A

#### Pasos
1. Iniciar sesión con cuenta de Agente.
2. Acceder al módulo de Propiedades.
3. Seleccionar una propiedad existente.
4. Seleccionar el botón “Editar propiedad”.

#### Resultado esperado
- El sistema redirige al formulario de edición.
- El formulario se muestra con los datos previamente cargados.

---

### CP-02 – Edición exitosa de datos de una propiedad
**Tipo:** Funcional
**Descripción:**  Verificar que el sistema permita modificar los datos de una propiedad y que los cambios se reflejen en la ficha del sistema y de la página web.  
**Prioridad:** Alta
**Criterios cubiertos:** 3, 7, 10, 11

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

### CP-03 – Editar las imágenes de una propiedad.

**Tipo:** Funcional
**Descripción:** Verificar que el sistema permita agregar, eliminar y reemplazar imágenes de una propiedad existente.  
**Prioridad:** Alta.
**Criterios cubiertos:** 4, 5, 6 

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

### CP-04 – Eliminación total de imágenes en propiedad publicada

**Tipo:** Funcional.
**Descripción:** Verificar que el sistema no permita mantener publicada una propiedad en la web si se eliminan todas sus imágenes.  
**Prioridad:** Alta
**Criterios cubiertos:** 9, 11

#### Precondiciones
- Usuario autenticado con rol Agente.
- Propiedad publicada en la web con imágenes cargadas.

#### Tipo de caso
- Negativo.

#### Datos de entrada
N/A

#### Pasos
1. Acceder al formulario de edición de la propiedad.
2. Eliminar todas las imágenes existentes.
3. Seleccionar “Guardar”.
4. Confirmar la acción.

#### Resultado esperado
- El sistema desactiva la opción "Publicar en la web".
- El sistema deshabilita la opción "Publicar en la web"
- La propiedad deja de mostrarse en la página web.

---

