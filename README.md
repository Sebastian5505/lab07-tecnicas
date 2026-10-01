# Bitacora de tecnicas avanzadas 
Laboratorio 07: Tecnicas Avanzadas de Prompting. 
Herramienta de IA usada: (escribe aqui cual usaste) 
## Ejercicio 2: Zero-shot, one-shot y few-shot 
| Tipo | Aciertos (de 5) | Formato de la respuesta | Todas con el mismo formato  (Si/No) | 
|------|-----------------|-------------------------|------------------------------------| 
| Zero-shot |   5 |"Me encanto, llego rapido" — Positivo (Expresa satisfacción con el producto y el tiempo de entrega). |Si | 
| One-shot | 5|Me encanto, llego rapido -> Positivo |Si | 
| Few-shot |5 |"Me encanto, llego rapido" -> Positivo |Si |
## Ejercicio 3: Chain of Thought 
| Pedido | Respuesta de la IA | Muestra los pasos (Si/No) | Correcta (Si/No) |
|---|---|---|---|
| Directo |322.20 |No |Si |
| Paso a paso |Para determinar el costo total que paga el cliente, realizaremos los cálculos paso a paso de forma independiente para cada unidad y luego para la cantidad total. |Si |Si |
## Ejercicio 4: Role prompting 
| Version | Vocabulario (sencillo/tecnico) | Usa ejemplos o codigo | A quien le  sirve mas | 
|---------|-------------------------------|-----------------------|----------------------| 
| A. Sin rol |Sencillo |Basicos |Novato| 
| B. Rol docente |Tecnico |Intermedios |Estudiante de carrera| 
| C. Rol senior |Tecnico |Superiores |Profesional |
## Ejercicio 5: Descomposición

|Pasos| Extensa | Sin pasos |
|---|---|---|
| 1. Requisitos |Propuso funciones como registrar, consultar, actualizar, eliminar productos y controlar stock.  |Cumple parcialmente cubre la gestión básica de productos, pero no incluye ventas ni reportes, que estaban en los requisitos iniciales.  |
|2. Clases|Propuso Producto, Inventario y Tienda|Es más sencillo que el diseño anterior, pero faltan Venta, DetalleVenta y Reporte. |
|3. Producto |Incluye id, nombre, precio y stock, con constructor, getters, setters y toString().|Cumple parcialmente el diseño anterior incluía además codigo, categoria y stockMinimo.|
|4. Control de inventario|Inventario permite agregar, buscar, actualizar, mostrar y eliminar productos.|Cumple bien con la administración básica del inventario, pero no controla entradas/salidas de stock de forma específica.|
|5. Validaciones|El código permite establecer cualquier precio o stock mediante los setters.|Es inferior al otro codigo, porque este último incorpora validaciones para evitar valores negativos y métodos para aumentar/disminuir stock.|
|6. Programa principal|Incluye un menú de consola mediante Scanner.|Es una mejora respecto a la clase Producto aislada, porque permite probar el sistema directamente desde consola.|
|7. Ventas|No implementa una clase ni funciones de ventas.|No cumple con uno de los requisitos principales originales.|
|8. Reportes |Solo muestra los productos registrados.| Cumple parcialmente: faltan reportes de ventas, movimientos y productos con bajo stock.|
## Ejercicio 6: Prompt estructurado y autocritica
```text 
Rol
Actúa como analista de pruebas de software.

Contexto
Login web con correo y contraseña. La cuenta se bloquea después de 3 intentos fallidos.

Tarea
Piensa paso a paso qué puede fallar y escribe 6 casos de prueba.

Formato
Tabla con las columnas: ID, escenario, datos de entrada, resultado esperado.

AUTÓCRITICA

La primera tabla cubría principalmente el bloqueo por intentos fallidos,
pero faltaban pruebas de validación de entradas y casos límite.

Se agregaron los siguientes casos:
- CP-07: Campos completamente vacíos.
- CP-08: Correo vacío.
- CP-09: Contraseña vacía.
- CP-10: Correo con formato inválido, sin @.
- CP-11: Contraseña con espacios.
```
[Bitacora de tecnicas avanzadas](prompts/BITACORA.md)

# Tarea: Mi prompt avanzado 
## Tarea elegida 
Generar casos de prueba para un formulario de inicio de sesión (login) de una aplicación web, considerando escenarios positivos, negativos y casos límite.
## Version 1: prompt basico 
Dame casos de prueba para un login.
## Version 2 
Genera casos de prueba para un formulario de login web. Incluye casos positivos, negativos y casos límite. Para cada caso indica el nombre, los datos de entrada, los pasos, el resultado esperado y la prioridad.
## Version 3: prompt final 
Actúa como un ingeniero de QA especializado en pruebas de aplicaciones web. Genera una lista completa de casos de prueba para un formulario de inicio de sesión (login).

Incluye casos positivos, negativos, casos límite y de seguridad. Considera credenciales correctas e incorrectas, campos vacíos, usuario inexistente, contraseña incorrecta, caracteres especiales, espacios, límites de longitud y múltiples intentos fallidos.

Para cada caso indica: ID, nombre del caso, datos de entrada, pasos, resultado esperado y prioridad.

Presenta la información en una tabla clara y ordenada. Clasifica los casos según su categoría y evita inventar funcionalidades que no estén indicadas.

Finalmente, realiza una breve autocrítica para identificar posibles casos que falten y explicar cómo se podría mejorar la cobertura de las pruebas.
## Tecnicas usadas en el prompt final  
|Rol:|Respuesta|
|---|---|
|Asignación de rol:|se indica que la IA actúe como ingeniero QA.|
|Contexto:|se especifica que se probará un formulario de login web.|
|Instrucciones detalladas:|se enumeran los escenarios que deben considerarse.|
|Formato de salida:|se establece una tabla con columnas concretas.|
|Restricciones:|se indica que no se deben inventar funcionalidades.|
|Clasificación:|se solicita establecer prioridades y categorías.|
|Cobertura:|se incluyen casos positivos, negativos, límites y seguridad.|
|Autocrítica:|se pide revisar el resultado y detectar posibles omisiones|
|Criterios de calidad:|se solicita que los casos sean claros, verificables y ejecutables.|
## Evaluacion del resultado 
| Aspecto                               | Prompt básico    | Prompt final       |
| ------------------------------------- | ---------------- | ------------------ |
| Claridad                              | Baja             | Alta               |
| Cantidad de casos                     | Limitada         | Amplia             |
| Casos negativos                       | No especificados | Incluidos          |
| Casos límite                          | No especificados | Incluidos          |
| Seguridad                             | No especificada  | Incluida           |
| Formato                               | Libre            | Tabla estructurada |
| Priorización                          | No               | Sí                 |
| Autocrítica                           | No               | Sí                 |
| Control de funcionalidades inventadas | No               | Sí                 |
| Utilidad para QA                      | Media            | Alta               |

## Por que elegi estas tecnicas
Elegí estas técnicas porque ayudan a que la IA comprenda exactamente qué debe hacer, cómo debe hacerlo y cómo presentar el resultado.

La asignación de un rol de QA permite orientar la respuesta hacia buenas prácticas de pruebas. Las instrucciones específicas aumentan la cobertura de escenarios, mientras que la tabla facilita revisar y ejecutar cada caso.

También incluí restricciones para evitar que la IA suponga funcionalidades que no existen. Finalmente, la autocrítica permite identificar posibles omisiones y mejorar el prompt en futuras versiones.

[Tarea: mi prompt avanzado](prompts/TAREA.md)