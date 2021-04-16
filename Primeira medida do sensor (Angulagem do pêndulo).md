## Primeira medida do sensor (Angulagem do pêndulo)

##### Programa

```python
from mpu6050 import mpu6050
import numpy as np 
import math
import time

mpu = mpu6050

while True:
    accel_data = mpu.get_accel_data()
    x_val = (accel_data['x'])
    y_val = (accel_data['y'])
    z_val = (accel_data['z'])
    
    #Quadrados
    x2 = x_val*x_val
    y2 = y_val*y_val
    z2 = z_val*z_val

    #Eixo y
    result = np.sqrt(y2+z2)
    result = x_val/result
    accel_angle_x = math.atan(result)*180/math.pi
    print("x: ", accel_angle_x)
```

Os dados do sensor são trabalhados de acordo com a seguinte expressão:
$$
y = arctan(\dfrac{Y}{\sqrt{X^2+Z^2}})
$$
E após isso é feita a conversão de radianos para graus 
$$
\theta = rad \cdot \dfrac{180}{\pi}
$$
Encontram se valores que vão de 0 a 90° e de 0 a -90°

