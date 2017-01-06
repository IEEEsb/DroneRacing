## ¿En qué consiste?

SparkAway es un sistema para evitar chispazos al conectar la batería al dron que poco a poco degradan los conectores de potencia, creando puntos de contacto de alta 
resistencia potencialmente peligrosos además de provocar picos de tensión y someter a estrés eléctrico a algunos componentes. Utiliza el conector de equilibrado de la batería para alimentar al dron a través de un fusible electrónico
con límite de corriente a 3.5 A y control de corriente al arranque, sirviendo también como elemento de seguridad ante cortocircuitos o errores de montaje al alimentar al dron por primera vez.
El diseño actual utiliza un integrado comercial como fusible electrónico y sólo es compatible con baterías de polímero de litio 4S (16,8 V máx). Hay planeada una versión para 3S y, de haber demanda,
una versión para baterías con más celdas.

## ¿Cómo se usa?

El SparkAway debe conectarse soldado en paralelo al conector de potencia principal del dron. Antes de conectar la batería al conector principal de potencia, debe conectarse el conector
de equilibrado de la batería al SparkAway, esperar a que el dron se encienda, conectar el conector de potencia principal de la batería y finalmente desconectar el conector de equilibrado del 
SparkAway (o dejarlo puesto si se desea). Se incluye un supresor de transitorios de alta energía para proteger al SparkAway de picos de tensión inducidos por el frenado regenerativo de los motores.

