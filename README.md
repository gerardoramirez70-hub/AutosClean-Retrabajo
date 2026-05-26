# AutosClean&Go - Generador de Flujos de Retrabajo

## Proceso de solución del problema

Para resolver el problema primero identificamos que el proyecto no pedía solamente un flujo normal, sino un flujo que pudiera cambiar cuando apareciera un error. Por eso elegimos el proceso de lavado de autos, ya que es fácil encontrar situaciones donde se necesita retrabajo, como manchas visibles, interior sucio o marcas de agua.

Primero definimos el flujo principal: recibir el auto, lavar exterior, limpiar interior, secar, revisar y entregar. Después identificamos las razones que podían provocar un retrabajo. Cada razón se relacionó con un flujo alterno que contiene los pasos necesarios para corregir el error.

La lógica fue que el usuario escribiera una razón. Si esa razón existe, el sistema muestra el retrabajo correspondiente, explica qué pasos se deben realizar y señala a qué parte del flujo principal debe regresar. Si la razón no existe, el usuario puede agregar una nueva razón con sus pasos, cumpliendo con la idea de poder añadir N razones.


El requerimiento pedía generar un texto de salida compuesto por tres partes principales:

- GoToFlowPath[Retrabajo/Paso de Retrabajo]
- ReturnStep[Paso de retorno del flujo principal]
- Reason[Razón para retrabajar el producto]

En nuestra solución, cada vez que se detecta una razón de retrabajo, el sistema genera ese formato.

Ejemplo:

GoToFlowPath[Relavado Exterior/Aplicar espuma nuevamente]  
ReturnStep[Secar Auto]  
Reason[Manchas visibles];

Esto significa que, si durante el flujo principal se detecta la razón "Manchas visibles", el auto cambia al flujo de retrabajo "Relavado Exterior", inicia en el paso "Aplicar espuma nuevamente" y después regresa al paso "Secar Auto" del flujo principal.


La solución cumple con el requerimiento porque muestra un flujo principal, permite detectar razones de error, cambia al flujo de retrabajo correspondiente y genera el output solicitado. Además, permite agregar nuevas razones, por lo que el sistema puede manejar N razones de cambio de flujo.