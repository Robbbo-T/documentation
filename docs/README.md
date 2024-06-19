
Primera Forma Normal (1NF):

Cada columna debe ser atómica, es decir, no puede tener un conjunto de valores.

Los valores en cada columna de una fila deben ser únicos.

Segunda Forma Normal (2NF):

Cumple con 1NF.

Cada campo no clave debe ser funcionalmente dependiente de la clave completa (es decir, los campos no clave deben depender de todos los campos clave).

Tercera Forma Normal (3NF):

Cumple con 2NF.

No hay dependencias transitivas de campos no clave (es decir, si un campo no clave depende de otro campo no clave, entonces ese otro campo debe ser una clave).

Cuarta Forma Normal (4NF):

Cumple con 3NF.

No existen dependencias multivaluadas (es decir, un campo no clave no puede depender de un conjunto de campos clave).

Por favor, ten en cuenta que estos son principios básicos y existen formas normales más avanzadas como la Quinta Forma Normal (5NF), Sexta Forma Normal (6NF), etc. Además, normalizar una base de datos puede tener pros y contras dependiendo del contexto, por lo que es importante entender bien sus implicaciones antes de aplicarla.

Espero que esto te ayude a comenzar con la normalización de la base de datos
