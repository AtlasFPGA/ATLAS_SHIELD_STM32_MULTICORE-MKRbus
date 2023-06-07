# ATLAS_SHIELD_STM32_MULTICORE-MKRbus

Primera versión del SHIELD MULTICORE STM32 MKRbus para I/O BOARD ATLAS, válido para todas las "I/O BOARD ATLAS" incluidas las "AKA NEPTUNE" se usan las hembras apiladas que normalmente se usan en los shield de arduino, para tener el multicore basado en STM32.

![Hembra apilable](https://github.com/AtlasFPGA/ATLAS_SHIELD_STM32_MULTICORE-MKRbus/blob/main/FOTOS/Pines_hembras_apilables.png)

Enlace cabezales hembra apilable:
https://es.aliexpress.com/item/4000059515638.html?pdp_npi=2%40dis%21EUR%211%2C16%E2%82%AC%211%2C06%E2%82%AC%21%21%21%21%21%40211b440316861499958111903e1e40%2110000000140557195%21btf&_t=pvid%3Af4806f4c-de05-4d23-908d-d920b1f8ac6d&afTraceInfo=4000059515638__pc__pcBridgePPC__xxxxxx__1686149996&spm=a2g0o.ppclist.product.mainProduct&gatewayAdapt=glo2esp


Las STM32 que se han usado son 2 modelos para el presente diseño SHIELD MULTICORE STM32:
Los modelos escogidos son el mismo que se usa en Muticore-II/UnAMIGA, pero en la versión de Victor Trucco, con una sóla SD en modo de acceso SPI 3V3, el modelo de tener microcontroladores o SBCs en el futuro es válido para futuros SHIELD MULTICORE que puedan aparecer con esta interconexión, al incorporar de esta forma la unión FPGA-SD-MICRO FPGA-SD-SBC, estamos en un puro derivado de MiST.

De hecho con el tiempo Victor trucco ha ido agregando más funcionalidad MiST a su versión con bluepill.

En este caso he colocado el mismo diseño que se ha usado en máquinas retro-fpga como,Multicore-II, UnAMIGA, Prototipos PEGASO & CENTAURO, Y las Retrofpga de más capacidad UnAMIGA-Reloaded y NePTUNO, puede que con eL añadido de VGA64 muchos cores de poca profundidad de color sean portables.

Como reservé 2 pines para un modo 4bit en SD, este se puede desarrollar con la BLACKPILL en la opción del chip más avanzado F411.
Hay por ahora tres modelos de BLACKPILL la BLACKPILL que posée SDIO de 1Bit, 4Bit u 8Bits -> SDIO es el STM32F411CEU6.

## Pineado bluepill

bluepill -> stm32f103c8t6

![pineado bluepill](https://github.com/AtlasFPGA/ATLAS_SHIELD_STM32_MULTICORE-MKRbus/blob/main/FOTOS/stm32f103-blue-pill-pinout.png)


## Pineado BLACKPILL

BLACKPILL -> STM32F411CEU6

![PINEADO BLACKPILL](https://github.com/AtlasFPGA/ATLAS_SHIELD_STM32_MULTICORE-MKRbus/blob/main/FOTOS/Pinout-Diagram.png)

Nota: para posicionar correctamente los pines usamos mayúsculas para la BLACKPILL, y minúsculas para la bluepill.

## Dimensiones que compraten las STM32 usadas, a tener en cuenta de la bluepill y la BLACKPILL:
![DIMENSIONES](https://github.com/AtlasFPGA/ATLAS_SHIELD_STM32_MULTICORE-MKRbus/blob/main/FOTOS/Dimesiones_BLUEPILL.jpg)

Avance del esquema multicore STM32:
![Diagrama multicore STM32](https://github.com/AtlasFPGA/ATLAS_SHIELD_STM32_MULTICORE-MKRbus/blob/main/FOTOS/AVANCE_ESQUEM%C3%81TICO_SHIELD_MULTICORE_STM32.png)

# NOTA: PI_TX y PI_RX pasarán as ser lineas de selección del modelo heredado por el Multicore II de Victor trucco.
# La colocación de los STM32, son excluyentes.

![PRIMERA VERSIÓN SHIELD MULTICORE STM32](https://github.com/AtlasFPGA/ATLAS_SHIELD_STM32_MULTICORE-MKRbus/blob/main/FOTOS/SHIELD_IO_BOARD_ATLAS_STM32_BLACKPILL_bluepill_MKR.png)

Al usar la elevación de las hembras apilables, el montaje "I/O BOARD ATLAS y LA SHIELD STM32" nos dá más capas, me queda la duda de si en la bluepill se puedieran cortar los pines asociados en la parte macho de las hembras apilables apoderándose de las señales R14_SD_DATA2 y P14_SD_DATA1 así como el AUDIO_L y T12_LEFT_MKR R11_RIGHT_MKR, agregando 4 señales a esta opción de Multicore con bluepill, estoy planteado en el futuro agregar esta opción de robar pines a la FPGA incorporando 4 señales a un nuevo diseño opcional, lo que permite conectar desde Dispositivos SPI, I2S, 2 canales I2C, TX RX con gestión de bflujo -> Acceso a internet.

Si se guardan los pines cortados iniciando el diseño con el bluepill y en el futuro se desarrollara una opción viable con SDIO 4Bit en BLACKPILL, no es muy dificil volver a soldarlos donde se realizó el corte, o directamente no usar ese tipo de hembras apilables en el conector de audio -> poner simples hembras, y hacer lo mismo en DATA1 y DATA2, y ya se veria como colocar pads normalmente abiertos o cerrados para que una misma placa permita obtener pines de fpga.

Aunque gestionando la compra de placas bien podía costearse una placa para bluepill + 4Señales, y BLACHPILL modelo F411.

Mi opción inicial es que se puedan manejar más componentes hardware, y unificar la placa sin agregar más que conectores cortar o soldar pistas en los pad indicados.

