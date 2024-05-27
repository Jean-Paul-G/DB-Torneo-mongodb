Documento de Requerimientos No Funcionales
1.	Requerimientos No Funcionales para la Base de Datos de un Torneo Deportivo de futbol
1.1.	Redundancia
Descripción: La redundancia asegura que los datos estén disponibles y consistentes incluso en caso de fallas de hardware o software. Para el torneo deportivo de futbol, se implementará una estrategia de replicación para mantener múltiples copias de los datos.
Requerimientos: Replicación de Datos: Los datos de la base de datos deben ser replicados en al menos 3 nodos diferentes.
Consistencia de Datos: Todas las réplicas deben mantenerse consistentes. Las actualizaciones deben propagarse a todas las réplicas de manera oportuna.
Failover Automático: En caso de que un nodo falle, la base de datos debe ser capaz de redirigir automáticamente las solicitudes a otro nodo funcional sin pérdida de datos.
1.2.	Disponibilidad 24x7
Descripción: La disponibilidad 24x7 asegura que la base de datos esté accesible en todo momento, sin interrupciones. Esto es crucial para gestionar el torneo de manera continua y efectiva.
Requerimientos: Alta Disponibilidad: La base de datos debe estar disponible el 99.99% del tiempo.
Mantenimiento Sin Interrupciones: Se deben poder realizar tareas de mantenimiento sin causar tiempo de inactividad.
Monitoreo y Alertas: Debe haber un sistema de monitoreo que alerte automáticamente sobre cualquier problema de disponibilidad o rendimiento.

Estrategia de Replicación y Comandos
2.	Estrategia de Replicación
2.1.	Estrategia de Replicación: Para cumplir con los requisitos de redundancia y disponibilidad, se utilizará una configuración de replicación en MongoDB llamada Replica Set. Un Replica Set es un grupo de procesos de mongod que mantienen el mismo conjunto de datos. Los Replica Sets proporcionan redundancia y alta disponibilidad.
Componentes del Replica Set:
Primary: Nodo principal que recibe todas las operaciones de escritura.
Secondary: Nodos secundarios que replican los datos del nodo primario y pueden servir operaciones de lectura.
Arbiter (opcional): Nodo que participa en la elección de un nuevo nodo primario en caso de fallos, sin mantener una copia de los datos.

