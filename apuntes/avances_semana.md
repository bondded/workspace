# Resumen semanal de avances

## Procesos estocasticos en el plasma
* Las particulas obedecen una distribución de Maxwell tanto en sus velocidades como energías. Esto es asumiento equilibrio termodinámico.

* La resistividad de Spitzer nace de este comportamiento estocástico. Su dependencia $T^{3/2}$ nace a partir de que la resistividad es proporcional a la frecuencia de colisión en el plasma, la cual es proporcional a $v^{-3}$, la velocidad de las partículas. Aquí no se aclara demasiado en el capítulo ya que es una deducción preliminar, pero sea cual sea la velocidad utilizada, esta es proporcional (térmica, rms o característica) a $T^{1/2}$

* Se estudió el nuclear reaction rate y se intentó derivar la ventana de gamow aplicando aproximación WKB al pozo de potencial nuclear fuerte. Aquí se entiende que el la cross section del proceso de fusión tiene 4 contribuciones; una geométrica, una de Maxwell, una por aproximación WKB y una función S(E) (paper Bosch-Hale)

## Magnetohidrodinámica
* Me encontré con un muro al estudiar Zohm ya que el autor le da gran profundidad a los temas sobre MHD. En un principio pensé en enfrentarlo, pero avanzaba tan lento que decidí priorizar el entendiemiento operacional de mi trabajo. Cambié a utilizar "Tokamaks" de J. Wesson. Las secciones relevantes de este libro son:

- Capítulos 1 - 3: Estudio de fisica de plasma general aplicado a tokamaks. Importante discusión sobre el safety factor (3.4)
- Capítulos 6 - 7: Estudio de la estabilidad MHD e inestabilidades y su caracterización.
- Capítulo 10: Habla un poco sobre diagnósticos magnéticos.

*Observaciones:* Me he enredado bastante con los contenidos y con las rutas que debo seguir, por eso he avanzado muy lento con la familiarización con los modos MHD.

## Papers
### Optimization of the Poloidal Magnetic System of the MEPHIST-0 Tokamak. D. L. Ulasevich

Se estudió este paper en búsqueda de la configuración de las bobinas Mirnov del Tokamak MEPHIST-0. (No se encontró, enviaré un correo)

* *Contexto:* MEPHIST-0 es un tokamak esférico pequeño y simple. Permite formar investigadores

* *Objetivos:* Se buscaba calcular las cofiguraciones de quilibrio para el campo magnético poloidal justo desdpues de la ruptura del gas. Optimizar el inductor para minimizar el campo magnético vertical del CS. Resolver problemas de equilibrio dinámico ara considerar la evolución del plasma.

* *Metodología:* Se utiliza el código DINA que se basa en la resolución de la ecuación de Grad-Shafranov. Con SIMULINK se simulan los incrementos de corriente y flujos magnéticos. Se hicieron pruebas con fuentes de corriente pulsada y sensores Hall para medir el campo magnético vertical. Uso de planes experimentales de dos y tres niveles junto con análisis de regresión para encontrar el número optimo de vueltas en las bobinas del sistema poloidal.

* *Hallazgos:* La configuración oprima de vueltas en el inductor (75 en el solenoide central y variaciones en las bobinas poloidales) Esto genera un punto de campo cero en el mayor. Se valida el modelo utilizado, teniendo desviaciones de amplitud de entre el 15% y 18%. Esta variacion se debe a impreciciones en la ubicación de sensores y la impedancia del sistema. El sistema de potencia actual tiene reserva suficiente para proporcionar las corrientes necesarias. La cámara de vacío genera un shift temporal debido a efectos de inducción mutua.


## Código
* Se procesó el shot N°2507
* Se estudio la documentación de Mephistdatakit y se analizaron pequeños bugs en el código.
* Se realizaron 5 figuras:

- Figura 1: Sincronización de señales: Corriente Ip, emisión H-alpha, bobinas Mirnov. *Comentarios:* Se encuentra un comportamiento "ruidoso" en el flat top de Ip. Durante la subida de corriente se experimenta una caída en la intensidad en H_alpha. Además durante el flat top aparece una perturbación en las bobinas Mirnov.

- Figura 2: Bobinas Mirnov + fft. *Comentarios:* Se encuentran prncipalmente dos contribuciones de frecuencia: tenemos una perturabacion de alta frecuencia (18.5 kHz) y perturbaciones de aun mayor amplitud a bajas freciencias (0 - 5 kHz). 

- Figura 3: Análisis de fase (demo). *Comentarios:* Se intentó buscar un desfase en las señales de las bobinas Mirnov para entender la rotación de la perturbación. Sin embargo, aún no se sabe la dispsición espacial de las bobinas utilizadas (Solo hay esquemas en la página web)

- Figura 4: Análisis del safety factor - q. *Comentarios:* Alanalizar el valor de q vemos que este aumenta a medida que la corriente baja y disminuye a medida que la corriente aumenta. Entre 7 y 10 ms el comportamiento se estabiliza en un valor q ~ 5 lo que significa que claramente hay una inestabilidad MHD presente en ese tiempo.

- Figura 5: Espectrograma (demo). *Comentarios:* Al realizar el espectrograma de la señal de 2507 se encuentra que las contribuciones de 18.5 kHz son relevantes al inicio y al final de operación del tokamak. Además se observa gran actividad concentrada entre los 7 y 10 ms, lo cual se condice con nuestro análisis de q. Se conjetura que las inestabilidades de baja frencuencia estén relacionadas con q ~ 5. 