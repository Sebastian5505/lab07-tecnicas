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

