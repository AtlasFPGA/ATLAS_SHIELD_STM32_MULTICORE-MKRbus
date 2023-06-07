# ATLAS_SHIELD_STM32_MULTICORE-MKRbus

Primera versión del SHIELD para I/O BOARD ATLAS, válido para todas las atlas se usan los pines usados en los shiedl de arduino para tener el multicore basado en stm32.

Las STM32 que se han usado son 2 modelos para un único recolocador:

## Pineado bluepill

bluepill -> stm32f103c8t6

![pineado bluepill](https://github.com/AtlasFPGA/ATLAS_SHIELD_STM32_MULTICORE-MKRbus/blob/main/FOTOS/stm32f103-blue-pill-pinout.png)


## Pineado BLACKPILL

BLACKPILL -> STM32F411CEU6

![PINEADO BLACKPILL](https://github.com/AtlasFPGA/ATLAS_SHIELD_STM32_MULTICORE-MKRbus/blob/main/FOTOS/Pinout-Diagram.png)

Nota: para posicionar correctamente los pines usamos mayusculas para la blackpill, y minúsculas para la bluepill.

## Dimensiones a tener en cuenta de la bluepill y la BLACKPILL:
![DIMENSIONES](https://github.com/AtlasFPGA/ATLAS_SHIELD_STM32_MULTICORE-MKRbus/blob/main/FOTOS/Dimesiones_BLUEPILL.jpg)


La bluepill esta desarrollada por victor trucco, pero en este caso usaremos una única SD en modo spi.
En la blackpill se plantea el usar el formato SD de 4bit -> SDIO.

Avance del esquema multicore STM32:
![Diagrama multicore STM32](https://github.com/AtlasFPGA/ATLAS_SHIELD_STM32_MULTICORE-MKRbus/blob/main/FOTOS/AVANCE_ESQUEM%C3%81TICO_SHIELD_MULTICORE_STM32.png)

