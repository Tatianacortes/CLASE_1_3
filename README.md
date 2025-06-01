# CLASE 1 III CORTE

# GEMELOS DIGITALES DE QUANSER

En laboratorio interactivo de Quanse, se ofrece una plataforma única para explorar y aprender sobre sistemas dinámicos y control. Entre los equipos disponibles se encuentran:

- QUBE: Un motor DC equipado con un sensor de corriente, tacómetros y discos de inercia, que permite analizar su comportamiento dinámico. Además, cuenta con un péndulo invertido que requiere un control preciso para equilibrar su movimiento rotacional. Los equipos están diseñados para interactuar entre sí a través de imanes.
- AERO: Un helicóptero aéreo de dos grados de libertad que ofrece dos modos de uso, y que su funciòn principal es equilibrar el helicóptero ajustando la potencia de los dos motores para mantener su estabilidad.
- BALL AND BEAM: Un sistema de bola y viga que consta de una viga larga que se puede inclinar mediante un motor, junto con una bola que rueda hacia adelante y hacia atrás en la parte superior de la viga. Este sistema permite estudiar y controlar el movimiento de la bola en función de la inclinación de la viga, lo que es un desafío clásico en el control de sistemas dinámicos.

En particular, el **QUANSER QUBE** tiene especificaciones físicas detalladas y cuenta con una planta que es precisamente el motor. La tarjeta de adquisición de datos incluye el control de potencia, sensor de corriente y encoders, lo que permite una monitorización precisa del sistema. Además, es compatible con plataformas de programación como Labview y Simulink y cuenta con librerías necesarias para realizar la programación del control de este motor, lo que facilita la implementación de algoritmos de control y análisis de datos.

Sin embargo, si se requiere trabajar con un sistema embebido externo, no hay una librería particular proporcionada para ese propósito, lo que significa que se tendría que desarrollar una solución personalizada utilizando los propios medios y recursos disponibles. 

## PROGRAMACIÓN QUANSER QUBE 2
1. Registro en el portal de Quanser
![Figura de prueba](IMAGES/IMA1.png)
2. Selección de Simulink Users
![Figura de prueba](IMAGES/IMA2.png)
3. Descargar Toolbox
![Figura de prueba](IMAGES/IMA3.png)
4. Instalación Licencia de Quanser Interactive Labs
![Figura de prueba](IMAGES/IMA4.png)
![Figura de prueba](IMAGES/IMA5.png)
![Figura de prueba](IMAGES/IMA6.png)
5. Digitar QLabs.setup para dar inicio a la instalación de Quanser Interactive Labs
![Figura de prueba](IMAGES/IMA7.png)
6. Dar click en instalar
![Figura de prueba](IMAGES/IMA8.png)
7. Loggearse con el usuario del registro del paso 1
![Figura de prueba](IMAGES/IMA9.png)
8. En la interfaz de Quanser Interactive Labs, seleccionar Qube 2 - DC Motor
![Figura de prueba](IMAGES/IMA10.png)
9. Seleccionar Servo Workspace
![Figura de prueba](IMAGES/IMA11.png)
10. En este paso ya se logró el acceso al gemelo digital. 
![Figura de prueba](IMAGES/IMA12.png)

**PARA LA PROGRAMACIÒN**
1. Abrir una ventana de simulink desde la ventana principal de Matlab
![Figura de prueba](IMAGES/IMA13.png)
2. Buscar en la libreria los componentes de QUARC Targets
![Figura de prueba](IMAGES/IMA14.png)
3. Abrir la pestaña 'Data acquisition', luego 'generic', y finalmente 'configuration', y seleccionar HIL Initialize.  
![Figura de prueba](IMAGES/IMA15.png)
4. Cambiar los parametros para realizar la conexión. 
![Figura de prueba](IMAGES/IMA16.png)
5. Observar la banda led superior del cubo en color verde indicando la conexión exitosa. 
![Figura de prueba](IMAGES/IMA18.png)
6. Siguiendo la ruta 'QUARC Targets' > 'Data acquisition' > 'generic' > 'Time bases', seleccionar 'HIL Read Encoder Timebase'
![Figura de prueba](IMAGES/IMA19.png)
7. Configurar los parametros de la pestaña 'main' seleccionando 'Active during normal simulation'  
![Figura de prueba](IMAGES/IMA21.png)
8. Configurar los parametros de la pestaña 'main' seleccionando 'Synchronize'
![Figura de prueba](IMAGES/IMA22.png)
9. Siguiendo la ruta 'QUARC Targets' > 'Data acquisition' > 'generic' > 'Inmediate I/O' seleccionar 'HIL Write Analog'
![Figura de prueba](IMAGES/IMA20.png)
10. Seleccionar 'Active during normal simulation'
![Figura de prueba](IMAGES/IMA23.png)
11. Agregar una constante a la entrada del HIL Write Analog
![Figura de prueba](IMAGES/IMA24.png)
12. Configurar el solver para no tener problemas con la simulación. 
![Figura de prueba](IMAGES/IMA27.png)
13. Observar el movimiento del QUBE con la configuraciòn dada previamente. 
![Figura de prueba](IMAGES/GIF1.gif)
14. Observar los datos en en el display.
![Figura de prueba](IMAGES/IMA29.png)
15. Modificar el valor de la constante
![Figura de prueba](IMAGES/IMA28.png)
16. Observar el cambio de los valores en el display respecto a la anterior simulación. 
![Figura de prueba](IMAGES/IMA30.png)
17. Observar el cambio de movimiento respecto a la velocidad en relaciòn con la anterior simulación.
![Figura de prueba](IMAGES/GIF2.gif)
18. Siguiendo la ruta 'QUARC Targets' > 'Data acquisition' > 'generic' > 'Inmediate I/O' seleccionar 'HIL Read'
![Figura de prueba](IMAGES/IMA32.png)
19. Cambiar los parametros de 'Analog channels', 'Encoder channels', 'Digital channels' y 'Other channels' y seleccionar 'Active during normal simulation'
![Figura de prueba](IMAGES/IMA33.png)
20. Parametros de 'Analog channels', corriente. 
![Figura de prueba](IMAGES/IMA34.png)
21. Parametros de 'Encoder channels', posición y sentido de giro. 
![Figura de prueba](IMAGES/IMA35.png)
22. Parametros de 'Digital channels', para este caso seleccionar Amplitud. 
![Figura de prueba](IMAGES/IMA36.png)
23. Parametros de 'Other channels', tacometro, para este caso no se selecciona ninguno. 
![Figura de prueba](IMAGES/IMA37.png)
24. Los parametros quedarias configurados asi.
![Figura de prueba](IMAGES/IMA38.png)
25. Se agregan osciloscopios y displays para observar datos al modulo HIL Read. 
![Figura de prueba](IMAGES/IMA39.png)
26. Gráficas obtenidas de los osciloscopios del modulo HIL Read con la configuraciòn de la última simulación.
![Figura de prueba](IMAGES/IMA40.png)
![Figura de prueba](IMAGES/IMA41.png)
27. Modulo Stall Monitor
![Figura de prueba](IMAGES/IMA42.png)
28. Configuración de modulo.
![Figura de prueba](IMAGES/IMA43.png)
29. Diagrama de conexión añadiendo el modulo Stall Monitor. 
![Figura de prueba](IMAGES/IMA45.png)
30. Agregar un manual switch y un pulse generation. 
![Figura de prueba](IMAGES/IMA46.png)
31. Configuración del modulo Pulse Generation
![Figura de prueba](IMAGES/IMA47.png)
32. Diagrama final
![Figura de prueba](IMAGES/IMA48.png)
33. Simulaciòn final. 
![Figura de prueba](IMAGES/GIF3.gif)

