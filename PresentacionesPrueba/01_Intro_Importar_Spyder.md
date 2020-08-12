<style>
.small-code pre code {
  font-size: 1em;
}

.reveal .state-background {
   background: white;
   background-image: url(https://nestormontano.github.io/PresentacionesPrueba/Imagenes/Top_Banner_Python.png);
   background-repeat: no-repeat;
   background-position: center 0.5%;
   background-size: 65%;
}
</style>



Importacion y manejo de datos - Bases
========================================================
author: Nestor Montaño
date: Julio.2020
autosize: true
transition: rotate
font-family: 'Helvetica'
css: slides-see.css
<small> 
Manejo de datos y reportería con Python
de Cero a Ninja
</small>





Python - Preeliminares 
========================================================
type: sub-section




Instalar Python
========================================================
<small>
**En windows y Mac**
- Visitar  sitio web de Python
- Elegir la versión que se desea instalar
- Descargar y ejecutar el instalador marcando la casilla "Añadir Python #.# al PATH"
- Ojo: Mac viene con python 2.7, pero se aconseja actualizar a nuevas versiones  


***  

**En Linux (Distribuciones)**
- Python también viene instalado en linux
- Se lo instala usando la consola, ejemplo: 
  - sudo yum install python (en Fedora, Red Hat o derivadas) 
  - sudo apt-get install Python (en Debian, Ubuntu y derivadas)
</small>




Instalar Anaconda
========================================================
<small>
Anaconda es un distribución libre y abierta de Python (y R), viene con utilidades muy usadas como Spyder o Jupyter en python. Es probablemente la distribución más usada para ciencia de datos, ojo que anaconda instala python por default (no se requiere el paso de la diapositiva anterior)

- Visitar  sitio web de Anaconda
- Elegir la versión que se desea instalar
- Descargar y ejecutar el instalador 
</small>



¿Por qué Python?
========================================================
<small>
Python 
- Gratuito
- Software Libre (Open Source)
- Flexible, rápido (para ser interpretado) 
- Simple y por tanto fácil de aprender
- Permite integrarse con otros sistemas u aplicaciones
- Gran cantidad de usuarios y desarrolladores
- Librerías especializadas en Data Science
- Las U enseñan python para carreras de computación o sistemas
</small>




¿Por qué Anaconda?
========================================================
<small>
Anaconda 
- Gratuito
- Software Libre (Open Source)
- Amplia documentación y gran comunidad.
- Permite instalar y administrar paquetes, dependencias y entornos para la ciencias de datos con Python de una manera muy sencilla.
- Integra diversos IDE como Jupyter, JupyterLab, Spyder y RStudio.
- Cuenta con herramientas como Dask, numpy, pandas y Numba para analizar Datos.
- Para visualizar datos integra Bokeh , Datashader , Holoviews o Matplotlib.
- Aplicaciones relacionadas con el aprendizaje de máquina y los modelos de aprendizaje como Orange
- Elimina problemas de dependencia de paquetes y control de versiones.  
</small>





¿Por qué Anaconda?
========================================================
class: small-code
<small>
Anaconda en un gráfico
</small>


<img src="Imagenes/Anaconda-Distribution-Diagram.png" title="plot of chunk unnamed-chunk-1" alt="plot of chunk unnamed-chunk-1" style="display: block; margin: auto;" />



Anaconda
========================================================
<small>
Abrir Anaconda Navigator
</small>

<img src="Imagenes/anaconda_navigator.png" title="plot of chunk unnamed-chunk-2" alt="plot of chunk unnamed-chunk-2" style="display: block; margin: auto;" />




Spyder
========================================================

- The Scientific (S) Python (PY) Development Environment (DER)  
- Jupyter, PyCharm, Spyder son de las 3 IDE más usadas para ciencia de datos en Python



Spyder
========================================================

Abrir Spyder   

<img src="Imagenes/Spyder_01.jpg" title="plot of chunk unnamed-chunk-3" alt="plot of chunk unnamed-chunk-3" style="display: block; margin: auto;" />



Spyder - Primera impresion
========================================================
<small>
1. Editor: Pantalla donde se escriben las líneas de código   
2. Consola: Donde se muestra el código ejecutado y el resultado   
3. Explorador de Archivos, variables, Ayuda: Esta pantalla esta particionada en varias pestañas como:   
   - Explorador de carpetas y archivos  
   - Variables.- Donde se van a mostrar los objetos que vamos a ir creando  
   - Help.- las ayudas internas del sistema  
</small>






Proyectos en Spyder
========================================================




Proyectos en R, RStudio
========================================================

- Un **Proyecto** es una carpeta que contiene todos los scripts y archivos el proyecto
- Permite tener nuestros análisis ordenados,
- Se sugiere tener una estructura interior, por ejemplo:
  - Scripts, Data, Exports, Info



Iniciar un Proyecto en RStudio
========================================================

<small>
- Nuevo Proyecto.-    Proyectos > Nuevo Proyecto  
- Elegir ubicacion y nombre del proyecto  
- En la carpeta del proyecto crear las carpetas: Data, Exports, Scripts, Info (Recomendado)
</small>




Realizar un script en Spyder
========================================================
<small>
- Nuevo script: `ctrl + n`
- Completado de comando: `tab`  
- Ejecutar selección:  `ctrl + enter`,   `shift + enter`
- Comentarios: `ctrl + 1`,en bloque: `ctrl + 4`
</small>

```python
import os
print(f'Hola, {os.getlogin()}!, ¡¿Listo para empezar?!')
```

```
Hola, Nestor!, ¡¿Listo para empezar?!
```







  
Generalidades
========================================================
class: small-code
Python, aparte de objetos, tiene:
 - Expresión.- Se evalúa, se imprime y el valor se pierde (iPython)
 

```python
5+5 # Expresión con output  
```

```
10
```

```python
5+5; # Expresión sin salida
```

```
10
```
 - Asignación.- Evalúa la expresión y guarda el resultado en una variable (no lo imprime)

```python
a = 5+5 # Asigna el valor a la variable "a"
```



Generalidades
========================================================

- Comandos se separan por `;` o `enter`
- Para comentar se usa `#`
- Case sensitivity (`Abc` es diferente de `abc`)

```python
a= 2; b= 1; a + b 
```

```
3
```





Python como calculadora
========================================================
class: small-code


```python
2 + 3*5 # operaciones básicas
```

```
17
```

```python
7 // 3 # division entera
```

```
2
```

```python
7 % 3 # Modular
```

```
1
```

```python
2 ** 3 # 2 elevado al cubo
```

```
8
```

```python
pow(2, 3) # 2 elevado al cubo
```

```
8
```




Python como calculadora
========================================================
class: small-code
<small>
A diferencia de R, para usar operaciones más "complicadas" debemos ya importar una libreria (import en Python es el equivalente de library en R)
</small>


```python
import math
math.floor(2.3) # Funcion piso
```

```
2
```

```python
math.fabs(-5) # valor absoluto
```

```
5.0
```

```python
math.factorial(3) # Factorial
 
```

```
6
```






Python como calculadora
========================================================
class: small-code
<small>
A diferencia de R, para usar operaciones más "complicadas" debemos ya importar una libreria (import en Python es el equivalente de library en R)
</small>


```python
math.exp(3) # e elevado a la x
```

```
20.085536923187668
```

```python
math.sqrt(9) # raiz cuadrada
```

```
3.0
```

```python
math.log(math.exp(2)) # Logaritmo natural
```

```
2.0
```

```python
print(math.floor(2.3))  
```

```
2
```




Asignaciones 
========================================================
class: small-code
- El resultado de una función de un objeto X puede ser asignada al mismo objeto X en la misma sentencia, es decir 

```python
a = 5 # Asignación
a
```

```
5
```

```python
a = 2*a  # Asignación a mismo objeto
a
```

```
10
```





Directorio de trabajo
========================================================
<small>
- El directorio de trabajo es la ruta en la cual se va a empezar todas las rutas que no estén completas (recordar al momento de importar data)  
- Tecnicamente es un conjunto de objetos y un puntero   


```python
import os
os.chdir("D:\SEE\...\Proyeto")
os.getcwd() # Verificar el directorio de trabajo
os.listdir("./")
```

</small>








Manejo de paquetes
========================================================

- Un paquete es simplemente un directorio que contiene otros paquetes y módulos.  
- Instalación: `conda install`,  `pip install`,   `pip3 install` 
- En el navegador de Anaconda, se puede ver los environments creados, en el environments **base** se puede instalar paquetes de forma visual.  

```python
import pandas as pd
import matplotlib . pyplot as plt
```




Paquetes a usar
========================================================
class: small-code

Los paquetes más usados para ciencia de datos son:

```python
import os
import math as mt
import numpy as np
import pandas as pd
import scipy
import matplotlib.pyplot as plt
import seaborn as sns
```








Caso a desarrollar
========================================================
type: sub-section



Ejemplo: Data de transacciones bancarias
========================================================

El Banco del Pacífico requiere mejorar los tiempos de atención al cliente en ventanilla, para ello ha recolectado esta información anónimamente para cada cajero y transacción realizada.   

Le suministran un excel con dos hojas:   

1. Tiene los datos de las transacciones, columnas: Sucursal, Cajero, ID_Transaccion, Transaccion, Tiempo_Servicio_seg, Nivel de satisfacción, Monto de la transaccion. 
2. Otra hoja que indica si en la sucursal se ha puesto o no el nuevo sistema.




Ejemplo: Data de transacciones bancarias
========================================================

**Revisar archivo de excel: Data_Banco.xlsx**   

Crear un proyecto con las carpetas Data, Exports, etc.     

Poner en la carpeta Data, el excel suministrado




Introducción a los análisis estadísticos
========================================================
type: sub-section



Workflow de un análisis estadístico
========================================================

<img src="Imagenes/WorkFlow_dataScience.png" title="plot of chunk unnamed-chunk-15" alt="plot of chunk unnamed-chunk-15" style="display: block; margin: auto;" />
<small>
- Import: Obtener y entender los datos
- Tidy: Ordenar los datos de tal manera que sea sencillo transformarlos, sumarizarlo, visualizarlos o realizar un modelo con ellos
- Transform: Manipular los datos hasta obtener el input que el análisis o técnica estadística necesita
- Visualise: Realizar el análisis exploratorio de datos
- Model: Aplicar técnicas estadísticas para el entendimiento del problema o tomar decisiones
- Comunicate: Tratar de mostrar los resultados de tal forma que el resto del mundo los entienda, usando reportes, gráficos, visualizaciones interactivas, integración con herramientas de BI, web apps, etc. 
</small>



Workflow de un análisis estadístico
========================================================

<img src="Imagenes/WorkFlow_dataScience.png" title="plot of chunk unnamed-chunk-16" alt="plot of chunk unnamed-chunk-16" style="display: block; margin: auto;" />
<small>
- Import
- Tidy  
**Repetir mientras sea necesario**
- **Transform:** Manipular los datos, obtener el input del modelo
- **Visualise:** Realizar el análisis exploratorio de datos
- **Model:** Aplicar técnicas estadísticas   
- Comunicate
</small>





	
Importar
========================================================
type: sub-section





Importar desde csv
========================================================
class: small-code

- Desde Spyder, explorador de archivos
- Usando Pandas:


```python
import pandas as pd
archivo_csv= "Data/Data_Banco_CSV.csv" # Ruta al archivo
data_banco_csv = pd.read_csv(archivo_csv, sep = ";") # Notese el sep= ";"
data_banco_csv.head(5) # Mostrar 5 primeras filas del DataFrame
```

```
   Sucursal  Cajero  ...  Tiempo_Servicio_seg Satisfaccion
0        62    4820  ...                   41    Muy Bueno
1        62    4820  ...                   41         Malo
2        62    4820  ...                   41      Regular
3        62    4820  ...                   41      Regular
4        62    4820  ...                   41    Muy Bueno

[5 rows x 6 columns]
```







Importar desde excel
========================================================
class: small-code
<small>
Importar desde excel
</small>



```python
# Debe estar seteado el chdir
archivo_xlsx = 'Data//Data_Banco.xlsx' # Ruta al archivo
xlsx = pd.ExcelFile(archivo_xlsx) # Carga todo el spreadsheet
print(xlsx.sheet_names) # Ver hojas del archivo
```

```
['Data', 'Data_Sucursal', 'Data_Cajero']
```

```python
data_banco = xlsx.parse('Data')
data_banco.head(5)
```

```
   Sucursal  Cajero  ID_Transaccion  ... Tiempo_Servicio_seg  Satisfaccion    Monto
0        62    4820               2  ...               311.0     Muy Bueno   2889,3
1        62    4820               2  ...               156.0          Malo  1670,69
2        62    4820               2  ...               248.0       Regular  3172,49
3        62    4820               2  ...                99.0       Regular  1764.92
4        62    4820               2  ...               123.0     Muy Bueno  1835.69

[5 rows x 7 columns]
```




Importar desde excel
========================================================
class: small-code
<small>
Importar desde excel
</small>



```python
# OPCION 2
data_banco_xlsx = pd.read_excel(archivo_xlsx, sheet_name = 'Data')
data_banco_xlsx.head(5)
```

```
   Sucursal  Cajero  ID_Transaccion  ... Tiempo_Servicio_seg  Satisfaccion    Monto
0        62    4820               2  ...               311.0     Muy Bueno   2889,3
1        62    4820               2  ...               156.0          Malo  1670,69
2        62    4820               2  ...               248.0       Regular  3172,49
3        62    4820               2  ...                99.0       Regular  1764.92
4        62    4820               2  ...               123.0     Muy Bueno  1835.69

[5 rows x 7 columns]
```





Importar desde otras fuentes
========================================================
class: small-code
<small>
Panda permite importar desde una gran cantidad de fuentes, impora objetos de tipo *pandas.DataFrame*, similar al *data.frame* de R.

- `read_csv` para importar desde csv
- `ExcelFile` & `xl.parse` o `read_excel` para importar desde excel  
- `openpyxl` también permite manipular excels  
- `read_json` para importar desde json
- `read_sql_table` para importar toda una tabla
- más en: https://pandas.pydata.org/docs/reference/io.html  
</small>



¿Qué es Pandas?
========================================================
class: small-code
<small>
Pandas es la gran navaja suiza de Python para Data Science

- Soporta lectura desde una variedad de datos, integrarlos y transformarlos
- Permite realizar estadística descriptiva
- Tiene opciones de gráficos integrados
- Soporta series de tiempo
- Métodos integrados para manejar valores perdidos
- Soporte para procesamiento de imágenes
- Internamente maneja dos tipos de objetos, pandas Series, panda DataFrame
</small>




Ejemplo - Caso Banco: Importar
========================================================
class: small-code


```python
import pandas as pd
data_banco_xlsx = pd.read_excel('Data//Data_Banco.xlsx', sheet_name = 'Data')
data_banco_xlsx.head(3)
```

```
   Sucursal  Cajero  ID_Transaccion  ... Tiempo_Servicio_seg  Satisfaccion    Monto
0        62    4820               2  ...               311.0     Muy Bueno   2889,3
1        62    4820               2  ...               156.0          Malo  1670,69
2        62    4820               2  ...               248.0       Regular  3172,49

[3 rows x 7 columns]
```

```python
data_sucursal = pd.read_excel('Data//Data_Banco.xlsx', sheet_name = 'Data_Sucursal')
data_sucursal.head(3)
```

```
   ID_Sucursal       Sucursal Nuevo_Sistema
0           62  Riocentro Sur            No
1           85         Centro            Si
2          267       Alborada            Si
```



Ejemplo - Caso Banco
========================================================

Bien, se han creado dos objetos en nuestro 'environment', entendamos un poco las estructuras de datos para poder explorar estos objetos




Estructuras de datos | Objetos
========================================================
type: sub-section





Estructuras de datos | Objetos
========================================================

Python (más en: https://docs.python.org/3/tutorial/datastructures.html)
- Listas 
- Matrices  
- Tuples  
- ndarrays  
- pandas Series  
- pandas DataFrames  





Estructuras de datos | Objetos
========================================================
class: small-code
Un string

```python
a= 'Hola Mundo'
a
```

```
'Hola Mundo'
```

```python
a.__class__ 
```

```
<class 'str'>
```




Métodos en Python
========================================================
class: small-code
<small>
Existen lenguajes que a pesar de ser orientados a objetos, se comportan de forma funcionales como **R**, Python es como java/c++, se usan métodos de los objetos creados.  
</small>
> En python para aplicar un método se usa nombre_del_objeto.metodo(parametros)  
<small>
Para entender esto vamos a ver algunos métodos asociados a un objeto de tipo string. Ir a https://docs.python.org/3/library/stdtypes.html#string-methods
</small>


<img src="Imagenes/Python_MetodosString.png" title="plot of chunk unnamed-chunk-22" alt="plot of chunk unnamed-chunk-22" style="display: block; margin: auto;" />





Métodos en Python
========================================================
class: small-code
<small>
En python para aplicar un método se usa nombre_del_objeto.metodo(parametros)   
</small>



```python
z = "hola mundo" # Crear objeto
z.capitalize() # Usar metodo para letra capital (primera mayuscula)
```

```
'Hola mundo'
```

```python
z # Pero z no ha cambiado
```

```
'hola mundo'
```

```python
z= z.capitalize() # Cambiar z
z # mostar z
```

```
'Hola mundo'
```




Métodos en Python
========================================================
class: small-code
<small>
En python para aplicar un método se usa nombre_del_objeto.metodo(parametros)   
</small>



```python
z # mostar z
```

```
'Hola mundo'
```

```python
z.isupper() # TRUE si todos son mayuscula
```

```
False
```

```python
z.upper() # transforma todo a mayuscula
```

```
'HOLA MUNDO'
```

```python
z.upper().isupper() # Concatenar metodos
```

```
True
```



Estructuras de datos | Objetos
========================================================
class: small-code

Un entero

```python
a= 5
a
```

```
5
```

```python
a.__class__ 
```

```
<class 'int'>
```



Estructuras de datos | Objetos
========================================================
class: small-code

Una lista

```python
a= [2, 4]
a
```

```
[2, 4]
```

```python
a.__class__ 
```

```
<class 'list'>
```




Estructuras de datos | Objetos
========================================================
class: small-code

Un pandasSeries

```python
a = pd.Series([2, 4])
a
```

```
0    2
1    4
dtype: int64
```

```python
a.__class__
```

```
<class 'pandas.core.series.Series'>
```

```python
a.values
```

```
array([2, 4], dtype=int64)
```



Estructuras de datos | Objetos
========================================================

En primera instancia vamos a centrarnos en
- **Listas** 
- Matrices  
- Tuples  
- ndarrays  
- **pandas Series**  
- **pandas DataFrames**  





Listas
========================================================

Las listas en Python se crean con []

```python
lista = [10, 20, 30]
lista[1] # Nótese la forma de indexar
```

```
20
```

```python
lista[0] 
# lista[3] # Error
```

```
10
```



Listas
========================================================

Las listas en Python se crean con []

```python
lista[1:3] # Mostrar 2do y 3er elemento
```

```
[20, 30]
```

```python
lista[0:2] # Mostrar 1ro y 2do elemento
```

```
[10, 20]
```

```python
len(lista) # largo del vector
```

```
3
```


Listas
========================================================
class: small-code

Las listas en Python se crean con []

```python
lista2 = ['a', 'b', 'c'] # Un lista de sólo texto
lista2[1:3] # Mostrar 2do y 3er elemento
```

```
['b', 'c']
```

```python
lista3 = ['a', 12, 'c']  # Las listas en Python permiten mezclar tipos de datos
lista3[0] 
```

```
'a'
```

```python
lista3[1] 
```

```
12
```


Listas 
========================================================
class: small-code

<small>Cambiar 2do elemento por 200, notese indexado</small>

```python
# Python
lista[1] = 200
lista
```

```
[10, 200, 30]
```



Listas 
========================================================
class: small-code
<small>Agregar, borrar elementos</small>

```python
lista
```

```
[10, 200, 30]
```

```python
lista.append(400)
lista
```

```
[10, 200, 30, 400]
```

```python
lista.append(400)
lista
```

```
[10, 200, 30, 400, 400]
```


Listas 
========================================================
class: small-code
<small>Agregar, borrar elementos</small>

```python
lista
```

```
[10, 200, 30, 400, 400]
```

```python
lista.pop(1) #Elimina segundo elemento
```

```
200
```

```python
lista
```

```
[10, 30, 400, 400]
```

```python
lista.remove(400) # Elimina el primer 400 que encuentra
lista
```

```
[10, 30, 400]
```


Listas 
========================================================
class: small-code
<small>Agregar, borrar elementos</small>

```python
lista
```

```
[10, 30, 400]
```

```python
del lista[1] #Elimina segundo elemento
lista
```

```
[10, 400]
```


Listas 
========================================================
class: small-code
<small>Agregar, borrar elementos</small>

```python
lista= [10, 2, 30]
lista.sort() # Ordenar valores internos
lista
```

```
[2, 10, 30]
```

```python
lista.reverse() # Cambia la lista de ultimo a primer valor 
lista
```

```
[30, 10, 2]
```



Listas 
========================================================
class: small-code
<small>Concatenar dos listas, en python los tipos de datos pueden ser distintos</small>

```python
lista1 = [10, 20, 30]
lista2 = ['a', 'b', 'c']
lista1 + lista2 # Concatenar: No cambia lista1 ni lista2
```

```
[10, 20, 30, 'a', 'b', 'c']
```

```python
lista1.extend(lista2) # Agregar lista2 a lista1
lista1
```

```
[10, 20, 30, 'a', 'b', 'c']
```


Listas 
========================================================
class: small-code
<small>Concatenar dos listas, en python los tipos de datos pueden ser distintos</small>

```python
for i in lista1:
    print( i, type(i) )
```

```
10 <class 'int'>
20 <class 'int'>
30 <class 'int'>
a <class 'str'>
b <class 'str'>
c <class 'str'>
```



Listas 
========================================================
class: small-code
<small>Trabajar con dos listas en paralelo</small>

```python
lista1 = [10, 20, 30]
lista2 = ['a', 'b', 'c']
zip(lista1, lista2) 
```

```
<zip object at 0x000000002D8EB248>
```

```python
for i, j in zip(lista1, lista2) :
    print( i, j )
## Intenten con listas de diferente largo
## Python coge el menor tamaño
```

```
10 a
20 b
30 c
```




Listas y las referencias (punteros) en Python
========================================================
class: small-code
<small></small>

```python
lista1 = [10, 20, 30]
lista2 = lista1 # nueva variable pero apuntando al mismo objeto
lista1[1] = 200 # Cambiamos la lista1
lista1
```

```
[10, 200, 30]
```

```python
lista2 # Pero tb se ha cambiado la lista2
## Esto es por el manejo de las referencias en python
```

```
[10, 200, 30]
```



Listas y las referencias (punteros) en Python
========================================================
class: small-code
<small></small>

```python
lista1 = [10, 20, 30]
lista2 = list(lista1) # Nuevo objeto
lista1[1] = 200 # Cambiamos la lista1
lista1
```

```
[10, 200, 30]
```

```python
lista2 
```

```
[10, 20, 30]
```




Listas y las referencias (punteros) en Python
========================================================
Es importante saber cuándo hacer copias o simplemente usar la misma referencia, usar la misma referencia es mejor para la memoria pero puede llevar a cometer errores incluso a programadores experimentados, se requiere un análisis detrás de la decisión.






Data.frames
========================================================

- Data.frame es un objeto que cumple:
  - Las columnas son vectores de tipo pandas Series
  - Cada columnas puede ser de un tipo de dato distinto
  - Cada elemento, columna es una variable
  - Las columnas tienen el mismo largo
- Se podría decir que un data.frame es como una tabla en una hoja de excel





Data.frames
========================================================
class: small-code

Crear un data.frame

```python
Nombre = ['Ana', 'Berni', 'Carlos']
Edad = [20,19,20]
Ciudad = ['Gye', 'Uio', 'Cue']
df_1= pd.DataFrame({'Nombre': Nombre, 'Edad': Edad, 'Ciudad': Ciudad})
df_1
```

```
   Nombre  Edad Ciudad
0     Ana    20    Gye
1   Berni    19    Uio
2  Carlos    20    Cue
```




Data.frames
========================================================
class: small-code

Crear un data.frame

```python
df_2= pd.DataFrame({
        'Nombre' : ['Ana', 'Berni', 'Carlos'],
        'Edad' : [20,19,20],
        'Ciudad' : ['Gye', 'Uio', 'Cue']
        })
df_2
```

```
   Nombre  Edad Ciudad
0     Ana    20    Gye
1   Berni    19    Uio
2  Carlos    20    Cue
```




Data.frames
========================================================
class: small-code

Index en un dataframe

```python
df_3= pd.DataFrame({
        'Nombre' : ['Ana', 'Berni', 'Carlos'],
        'Edad' : [20,19,20],
        'Ciudad' : ['Gye', 'Uio', 'Cue']
        }, index= ['a', 'b', 'c'])
df_3
```

```
   Nombre  Edad Ciudad
a     Ana    20    Gye
b   Berni    19    Uio
c  Carlos    20    Cue
```





Data.frames
========================================================
class: small-code

Visualizar primeras filas

```python
df_3.head(2)
```

```
  Nombre  Edad Ciudad
a    Ana    20    Gye
b  Berni    19    Uio
```



Data.frames
========================================================
class: small-code

Visualizar últimas filas

```python
df_3.head(2)
```

```
  Nombre  Edad Ciudad
a    Ana    20    Gye
b  Berni    19    Uio
```




Data.frames
========================================================
class: small-code

 `.info()` permite ver la estructura de cualquier objeto en R.


```python
## Visualizar la estructura   
df_3.info()
```

```
<class 'pandas.core.frame.DataFrame'>
Index: 3 entries, a to c
Data columns (total 3 columns):
Nombre    3 non-null object
Edad      3 non-null int64
Ciudad    3 non-null object
dtypes: int64(1), object(2)
memory usage: 96.0+ bytes
```




Data.frames
========================================================
class: small-code

Modificar nombre de las variables

```python
df_3.rename( columns= {'Nombre':'Name', 'Edad':'Age', 'Ciudad':'City'}) # No cambia el objeto
```

```
     Name  Age City
a     Ana   20  Gye
b   Berni   19  Uio
c  Carlos   20  Cue
```

```python
df_3
```

```
   Nombre  Edad Ciudad
a     Ana    20    Gye
b   Berni    19    Uio
c  Carlos    20    Cue
```

```python
df_3.rename( columns= {'Nombre':'Name', 'Edad':'Age', 'Ciudad':'City'}, inplace= True) # Cambia el objeto
df_3
```

```
     Name  Age City
a     Ana   20  Gye
b   Berni   19  Uio
c  Carlos   20  Cue
```






Ejemplo: Transacciones bancarias
========================================================
class: small-code

Entonces, ¿qué tipo de estructura hemos importado?   
R. Un data.frame

```python
data_banco_xlsx.info()
```

```
<class 'pandas.core.frame.DataFrame'>
RangeIndex: 24299 entries, 0 to 24298
Data columns (total 7 columns):
Sucursal               24299 non-null int64
Cajero                 24299 non-null int64
ID_Transaccion         24299 non-null int64
Transaccion            24299 non-null object
Tiempo_Servicio_seg    24299 non-null float64
Satisfaccion           24299 non-null object
Monto                  24299 non-null object
dtypes: float64(1), int64(3), object(3)
memory usage: 1.3+ MB
```






Entender los datos
========================================================
type: sub-section



Entender los datos
========================================================
<small>
Luego de importar se debe entender los datos   
- ¿Qué representa cada columna?
- ¿Qué tipo de dato debería tener cada columna?
- ¿Qué granularidad o atomicidad tiene la data?
- Si es que se tiene varios conjuntos de datos ¿Cómo se relacionan los datos?
- A qué periodo de tiempo corresponde la data
- Muchas veces se obtiene la información desde una base de datos y por tanto toca entender la base y el query que genera los datos
</small>




Ejemplo - Entender los datos
========================================================
class: small-code

Podríamos ver las primeras filas

```python
# ver las primeras 5 filas
data_sucursal.head( 5)
```

```
   ID_Sucursal       Sucursal Nuevo_Sistema
0           62  Riocentro Sur            No
1           85         Centro            Si
2          267       Alborada            Si
3          443   Mall del Sol            Si
4          586      Via Daule            No
```





Ejemplo - Entender los datos
========================================================
class: small-code

Listar los nombres de las columnas 

```python
# Listar los nombres de las columnas 
data_banco_xlsx.info()
```

```
<class 'pandas.core.frame.DataFrame'>
RangeIndex: 24299 entries, 0 to 24298
Data columns (total 7 columns):
Sucursal               24299 non-null int64
Cajero                 24299 non-null int64
ID_Transaccion         24299 non-null int64
Transaccion            24299 non-null object
Tiempo_Servicio_seg    24299 non-null float64
Satisfaccion           24299 non-null object
Monto                  24299 non-null object
dtypes: float64(1), int64(3), object(3)
memory usage: 1.3+ MB
```

```python
data_sucursal.info()
```

```
<class 'pandas.core.frame.DataFrame'>
RangeIndex: 5 entries, 0 to 4
Data columns (total 3 columns):
ID_Sucursal      5 non-null int64
Sucursal         5 non-null object
Nuevo_Sistema    5 non-null object
dtypes: int64(1), object(2)
memory usage: 248.0+ bytes
```





Tipos de datos
========================================================
class: small-code

Tipos datos en Python


```python
a= 1
a.__class__
```

```
<class 'int'>
```

```python
type(a)
```

```
<class 'int'>
```

```python
a= 1.3
a.__class__
```

```
<class 'float'>
```

```python
type(a)
```

```
<class 'float'>
```




Tipos de datos
========================================================
class: small-code

Tipos datos en Python


```python
a= 1 + 2j
a.__class__
```

```
<class 'complex'>
```

```python
type(a)
```

```
<class 'complex'>
```

```python
a= 'texto'
a.__class__
```

```
<class 'str'>
```

```python
type(a)
```

```
<class 'str'>
```



Tipos de datos
========================================================
class: small-code


```python
from datetime import date
a= date.fromisoformat('2019-12-04')
a.__class__
```

```
<class 'datetime.date'>
```

```python
type(a)

```

```
<class 'datetime.date'>
```

```python
b= date(2019, 12, 4)
b.__class__
```

```
<class 'datetime.date'>
```

```python
type(b)
```

```
<class 'datetime.date'>
```





Tipos de datos - factor
========================================================
class: small-code
<small>
Util para tipos de datos ordinales
- Primero se agrega el vector de información 
- Categories: los niveles del factor labels: nombre de los niveles 
- El factor puede tener un orden específico
</small>

```python
# Crear un factor ordenado
a = pd.Categorical( ['alto', 'bajo', 'alto', 'alto'],
                   categories= ['bajo', 'mediano', 'alto'], 
                   ordered=True)
a.__class__
```

```
<class 'pandas.core.arrays.categorical.Categorical'>
```

```python
a # Mostrar el factor
```

```
[alto, bajo, alto, alto]
Categories (3, object): [bajo < mediano < alto]
```




Tipos de datos
========================================================
class: small-code

Datos lógicos 

```python
b= True
b.__class__
```

```
<class 'bool'>
```

```python
type(b)
```

```
<class 'bool'>
```

```python
b
```

```
True
```

```python
b= False
```




Tipos de datos
========================================================
class: small-code

Casos especiales


```python
1.797e308 # maximo float posible
```

```
1.797e+308
```

```python
1.797e308 # Resulta en infinito
```

```
1.797e+308
```

```python
pos_inf = math.inf     # Constante desde la libreria math
neg_inf = float('-inf')    # Declarar un float Inf, tb permite nan
```


Tipos de datos
========================================================
class: small-code

Casos especiales: Not a Number

```python
c= math.nan 
type(c)
```

```
<class 'float'>
```

```python
d= float('nan')
type(d)
```

```
<class 'float'>
```


Tipos de datos
========================================================

Casos especiales: Not a Number

```python
0.0 * neg_inf
```

```
nan
```




Tipos de variables 
========================================================
Tipos de variables y su correspondencia con el tipo de dato en Python

<img src="Imagenes/tipos_variables_python.png" title="plot of chunk unnamed-chunk-59" alt="plot of chunk unnamed-chunk-59" style="display: block; margin: auto;" />







FIN 
========================================================
type: sub-section


