# lenguaje-m-editor-avanzado

1) ¿Qué hace exactamente el bloque let...in en lenguaje M? ¿Por qué cada paso puede referenciar al anterior?
El bloque permite verificar y registrar el paso a paso de los ajustes hechos en la tabla realizado en Power Query, desde los realizados mediante botones de acción como aquellos comandos que no tienen botones propios y se deben realizar mediante funciones específicas. Cada paso puede referenciar al anterior porque el script se comporta como una cadena de pasos, en los que si no son mencionados de esta forma, el código puede no funcionar y arrojar diversos errores. 

2) ¿Por qué M es Case Sensitive y qué consecuencia práctica tiene? Dá un ejemplo de un error que esto puede causar.
Porque es un lenguaje sensible que puede interpretar diversas funciones según si fue escrito con mayúscula o minúscula. Además, las funciones nativas siempre comienzan con mayúscula. Un ejemplo de esto es que se genera un error al llamar mis propios pasos.
Ejemplo:
El código que falla:
LimpiarEspacios = table.transformcolumns(PromoverEncabezados, {{"nombre_producto", Text.Trim, type text}})

El error que genera:
[Expression.Error] El nombre 'table.transformcolumns' no se reconoce. Asegúrese de que se haya escrito correctamente.

4) ¿Cuál es la diferencia entre usar Text.Trim y Text.Clean en M?
- Text.Trim elimina espacios solo al inicio y al final del texto.
- Text.Clean elimina caracteres de control o no imprimibles.

4) ¿Por qué filtraste los registros "PRUEBA" después de estandarizar la categoría y no antes?
Porque habría dejado pasar registros que dijeran "prueba" o "PRUEBA", debido a que Power Query es case-sensitive (sensible a mayúsculas).
