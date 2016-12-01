# Simulaciones

Simulaciones en [LTspice](http://www.linear.com/designtools/software/#LTspice) de los componentes hardware del sistema.

## Transmisor

Simula el circuito que alimenta al (los) LED(s) del transmisor. Se emplea una fuente de corriente en lugar de una resistencia en serie con el LED
ya que así se tiene más control sobre la luminosidad del LED y se saca una señal más limpia. Los dos diodos entre base del transistor y masa (D1, D2)
fijan una tensión entre base y masa de 2xVf diodo, siendo Vf típicamente 0,6V, luego 1,2V en total. Esto fuerza a que Vbe + la caída de tensión
en R1 (Vr1) sea de 1,2V también. Vbe en un transistor NPN de silicio es bastante constante y vale unos 0,7V. Por tanto, mientras el transistor pueda
la caída de tensión en R1 será de 0,5V, y fijando su valor podemos decidir la corriente que la atravesará, que será aproximadamente la misma que atraviese
a los LED (en un transisor, Ie = Ib + Ic, con Ib normalmente despreciable frente a Ic en transistores bipolares con betas altas como es
el caso).

R2 está para polarizar la base del transistor. D4 y D5 en serie simulan un LED infrarrojo, ya que no hay modelos de LED infrarrojo en LTspice.
