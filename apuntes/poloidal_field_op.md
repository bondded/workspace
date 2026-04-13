# Optimization of the Poloidal Magnetic System of the MEPHIST-0 Tokamak

## Abstract

El artículo se centra en el calculo de las confiuraciones de quilibrio de MEPHIST-0 mediante el uso del codigo *DINA*. Se obtuvieron los parámetros del campo magnético poloidal necesarios para la formación de equilibrio inicial luego de la ruptura de descarga.

El análisis de las configuraciones de equilibrio estacionario del plasma permite determinar los parámetros de las fuentes de alimentación del campo poloidal necesarias para su formación.

*¿Qué se hace?*: 
* Enfoque en la fase incial: El estudio se centra en analizar las configuraciones de equilibrio justo después del breakdown

* Modelador del sistema eléctrico: Se hacer un modelo inicial para determinar como el sistema eléctrico debe suministrar las corrientes necesarias para alcanzar los valores teóricos calculados. Para validar este modelo se resuelve el problema del equilibrio dinámico.

* Optimización del campo magnético: Se seleccionan valores de corriente y número de vueltas en las bobinas del sistema poloidal con el objetivo de minimizar el campo magnético vertical.

## Sistema poloidal de MEPHIST-0

consiste en un solenoide central de aire el cual es la fuente principal de flujo magnético.

Bobinas poloidales, que son las encargadsa de compensar el campo magnético desviado y otras bobinas poloidales que se encargan de controlar la posición del filamento de plasma.

Cada bobina tiene vueltas de compensación y de control. Las bobinas de compensación se encargan de compensar el campo magnético vertical del inductor en el área central del volumen de vacío. Estas son las que están conectadas con el solenoiden central. CS y las vueltas de compensación son el inductor de la instalación

las vueltas de control son las responsables de controlar la posición del filamento de plasma y tienen fuentes de poder independientes.

El modelo poloidal utilizado fue el siguiente:

Se considerarosn 24 conductores toroidales que modelan la cámara de vacío. 17 bobinas poloidales (CS + 8control + 8compensación) 

Con DINA se calcula numéricamente la configuración del plasma. El modelo subyacente es la ecuación de GRad-Shafranov. En el caso de Equilibrio estacionario solo se consideran 17 conductores, en el caso dinámico se consideran lso 24 elementos de la camara.

Los efectos de inducción mutua son considerables pero el modelo se ajuste almenos temporalmente a los experimentos. esto se observa en la Figura 5. 



