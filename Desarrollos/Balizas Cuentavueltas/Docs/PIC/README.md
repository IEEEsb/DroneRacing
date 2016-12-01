## ¿En qué consiste?

Las comunicaciones mediante infrarrojos se realizan típicamente modulando en amplitud una portadora,
generalmente en el orden de las decenas de KHz, empleando modulación OOK. En este tipo de modulación
los bits se transmiten como ráfagas de pulsos de portadora o ausencia de señal según el convenio que
se escoja para 1's y 0's como se puede ver en éste [appnote](TB3096 - Pulse Code Modulated (PCM) Infrared Remote Control Using PIC16F1708.pdf) 
de Microchip.

La señal modulada se inyecta a un LED infrarrojo que la convierte en pulsos de luz infrarroja que se propagan por el aire.
Debido al uso masivo de sistemas de transmisión por infrarrojos en electrónica de consumo existen en el mercado
numerosos receptores diseñados para recuperar y demodular la señal enviada, incluyendo internamente todos los elementos
necesarios y cierta inteligencia para luchar contra ruido e interferencias. La mayoría están diseñados para controles
remotos de electrodomésticos, aunque hay modelos especializados para usarse en transmisión de datos. Quitando los transceptores
diseñados para IrDA (aquello que tenían los móviles viejos para pasarse politonos por infrarrojos) los receptores típicos trabajan
a una serie de frecuencias de portadora estandarizadas, siendo la más alta comunmente encontrable de 57,6 kHz en [receptores](../Infrarojos/Receptores/Datasheet Receptores.pdf)
usados para recibir datos en general y no específicamente códigos de mandos a distancia.

Estos demoduladores están preparados para trabajar en entornos ruidosos con fuentes de emisión infrarroja de muchos tipos, y
suelen implementar sistemas para eliminar ruido que, por desgracia, pueden llegar a confundir ráfagas constante de transmisión
de ciertas tramas ([ver appnote](../Infrarojos/Receptores/Appnote Receptores.pdf)(una trama es un bloque de datos transmitido) con ruido, con lo cual en una aplicación como ésta, donde los
drones van a emitir constantemente un mismo patrón, hay que tener cuidado en elegir qué patrones se mandan para evitarlo.

## ¿Cómo se hace?
Los transmisores deben generar la modulación necesaria para transmitir datos por infrarrojos. Como señal moduladora (datos) se pueden emplear
diversos estándares de comunicaciones, siendo uno muy cómodo por su universalidad la señalización típica de puertos serie (UART's) RS232.
Para mejorar la calidad de la transmisión conviene que ésta señal se genere con una temporización lo mas estricta posible, y por ello
debe generarse aprovechando periféricos hardware de microcontroladores.

Se ha sugerido emplear un [PIC12F1501](PIC12F1501 datasheet.pdf) ya que es un microcontrolador muy económico y sencillo de programar que
incorpora dos periféricos que ayudan a la generación muy sencilla de la señal requerida. Por un lado, incluyen un periférico consistente en
un oscilador con control numérico (NCO) que permite generar señales de frecuencias muy precisas. Por otro, tiene un periférico (CLC) que permite
ejecutar funciones lógicas combinacionales independientemente del procesador del microcontrolador. No tiene un puerto serie hardware, pero
eso no es un problema ya que el NCO manda una interrupción en cada transición de la señal que está generando, que puede ser usada para generar
la trama de datos y modularla usando la CLC.

El proceso consiste en configurar el NCO para generar onda cuadrada a 57,6 kHz (o lo más cerca que se pueda) y para que interrumpa en cada flanco.
La salida del NCO se conecta a una de las entradas de la CLC, configurada para realizar una función lógica AND. En la interrupción del
NCO se van contando ciclos y cuando pase un número entero de ellos (mínimo 6, ver detalles de los receptores IR) se va conmutando otra de las
entradas de la AND de la CLC para inhibir o no inhibir la portadora. Finalmente se configura la CLC para sacar la salida por un pin del
micro, y esa señal se utiliza para, mediante una fuente de corriente sencilla, modular el (o los) LED infrarojos.


