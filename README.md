# Reto #9 Funciones 2
Espero que se encuentren excelente estimados lectores, en el presente repositorio haremos varios ejemplos de código en Python utilizando lo aprendido acerca de las funciones dentro de nuestra clase de programación de computadores.

## Ejemplo No. 1
De los retos anteriores se debe escoger tres puntos y digitarlas en forma de funciones lamba.
1. Del [Reto #6](https://github.com/Artuu1999/Reto-6-Funciones-) escojeremos el ejemplo número 2, el cual consistía en desarrollar una función matemática que resuelva el área y perímetro de la siguiente figura:

![image](https://user-images.githubusercontent.com/124615034/226773245-eec6d80c-ffae-42c4-ada9-72718c707870.png)
El código solución de dicho problema fue:
```sh
from math import pi, sqrt

def areaFigura(radioCirculo:float, altura:float, base:float) -> float:
    areaCirculo = pi * radioCirculo**2 * 2
    areaRectangulo = base * altura
    return areaCirculo + areaRectangulo

def perimetroFigura(radioCirculo:float, altura:float, base:float) -> float:
    perimetroCirculo = 2 * 2 * pi * radioCirculo
    perimetroRectangulo = (altura * 2) + (base * 2)
    return perimetroCirculo + perimetroRectangulo

if __name__ == "__main__":
  radioCirculo = float(input("Ingrese el radio del círculo en cm:"))
  altura = float(input("Ingrese la altura del rectángulo en cm:"))
  base = float(input("Ingrese la base del rectángulo en cm:"))
  area = areaFigura(radioCirculo, altura, base)
  perimetro = perimetroFigura(radioCirculo, altura, base)
  print ("El area de la figura es "+str(area)+" centímetros")
  print ( "El perímetro de la figura es "+ str(perimetro)+" centímetros")
```
La anterior solución descrita con funciones lambdas se ve de la siguiente manera:
```sh
from math import pi, sqrt #Se importa la función math para utilizar el número pi
#Se hace uso de la función main
if __name__ == "__main__":
  #Se solicita al usuario que ingrese las variables que se usaran dentro de la función
  radioCirculo = float(input("Ingrese el radio del círculo en cm:"))
  altura = float(input("Ingrese la altura del rectángulo en cm:"))
  base = float(input("Ingrese la base del rectángulo en cm:"))
  #Se define la función en una sola línea llamando las variables de uso
  areaFigura = lambda radioCirculo, altura, base: pi * radioCirculo**2 * 2 + base * altura
  area = areaFigura(radioCirculo, altura, base)
  # Se define la función en una sola línea llamando las variables de uso
  perimetroFigura = lambda radioCirculo, altura, base: 2 * 2 * pi * radioCirculo + (altura * 2) + (base * 2)
  perimetro = perimetroFigura(radioCirculo, altura, base)
  #Se imprimen los resultados trabajados en las funciones
  print ("El area de la figura es "+str(area)+" centímetros")
  print ( "El perímetro de la figura es "+ str(perimetro)+" centímetros")
```
2. Del [Reto #8](https://nodejs.org/) escojeremos el punto número 5, el cual consistía en crear un programa que al indicar un número, imprima el resultado de elevar 2 a la aquel número ingresado.

El código solución para dicho prooblema fue el siguiente:
```sh
x : int = 1 #Inicializar la variable
n = int(input("Ingrese numero natural: ")) #Solicitar el ingreso de la potencia
for y in range (n): #Declarar el rango mediante el ciclo for
    x *= 2 #Actualizar la variable
print ("El resultado de 2 elevado a la "+str(n)+" es "+str(2**n)+"") #Imprimir el resultado
```
La anterior solución descrita en funciones lambda se ve de la siguiente manera:
```sh
if __name__ == "__main__":
 n = int(input("Ingrese numero natural: ")) #Solicitar el ingreso de la potencia
 dosElevado = lambda n: 2**n #Se define la función elevando 2 a la n
 potencia = dosElevado (n) #Se  llama la función definida anteriormente
 print ("El resultado de 2 elevado a la "+str(n)+" es "+str(potencia)+"") #Imprimir el resultado
```

3. Del [Reto # 6](https://github.com/Artuu1999/Reto-6-Funciones-) escojeremos el punto número 6, el cual consistía en crear un código relacionado al siguiente problema: 

El crecimiento exponencial es un tipo de crecimiento en el que la tasa de crecimiento aumenta constantemente en función del tamaño actual de una cantidad.
En este caso si el número de contagiados aumenta exponencialmente, duplicandose cada día la cantidad, la función que se usará es la siguiente:
> C x 2^D

El código solución fue el siguiente:
```sh
def totalPersonasContagiadasNuncalandia(C:int, D:int) -> int:
    return C * (2**D)

if __name__ == "__main__":
  C = int(input("Ingrese la cantidad de personas contagiadas actualmente:"))
  D = int(input("Ingrese los días transcurridos:"))
  Total = totalPersonasContagiadasNuncalandia(C, D)
  print("La cantidad de personas contagiadas transcurridos "+str(D)+" días, es de "+ str(Total)+" personas")
```
Ahora bien la solución de dicho proble haciendo uso de las funciones lambda es el siguiente:
```sh
if __name__ == "__main__":
  #Se solicita al usuario el ingreso de las variables tipo entero
  C = int(input("Ingrese la cantidad de personas contagiadas actualmente:"))
  D = int(input("Ingrese los días transcurridos:"))
  #Se define la función en una sola línea de código haciendo uso del lambda
  totalPersonasContagiadasNuncalandia = lambda C, D: C * (2**D)
  Total = totalPersonasContagiadasNuncalandia(C, D)
  #Se imprime el resultado de la función
  print("La cantidad de personas contagiadas transcurridos "+str(D)+" días, es de "+ str(Total)+" personas")
```
## Ejemplo No. 2
De los retos realizados anteriormente se debe escoger tres puntos y digitarlas en forma de funciones con argumentos no definidos (*args).
1. Del [Reto #6](https://github.com/Artuu1999/Reto-6-Funciones-) escojeremos el punto número 4, el cual consistía en crear un código, el cual al ejecutarlo me imprima la solución al siguiente problema:

+ Mi mamá me manda a comprar P panes a 300 cada uno, M bolsas de leche a 3300 cada una y H huevos a 350 cada uno. Cual es el valor de las vueltas (o lo que quedo debiendo) cuando me da un billete de B pesos.

El siguiente pseudocódigo contiene la solución al problema
```sh
def cantidadVueltas(P:int, M:int, H:int, B:float) -> float:
    return B - (P*300 + M*3300 + H*350)

if __name__ == "__main__":
  P = int(input("Ingrese la cantidad de panes:"))
  M = int(input("Ingrese la cantidad de leche:"))
  H = int(input("Ingrese la cantidad de huevos:"))
  B = float(input("Ingrese el valor del billete usado para pagar en pesos :"))
  Vueltas = cantidadVueltas(P, M, H, B)
  print("Las vueltas correspondientes al mandado son de "+ str(Vueltas)+" pesos")
```
A continuación se presenta el anterior código descrito con argumentos
```sh
#Definimos las variables como argumentos
def cantidadVueltas(*args) -> float:
    return B - (P*300 + M*3300 + H*350)

if __name__ == "__main__":
  #Solicitamos el ingreso de las variables
  P = int(input("Ingrese la cantidad de panes:"))
  M = int(input("Ingrese la cantidad de leche:"))
  H = int(input("Ingrese la cantidad de huevos:"))
  B = float(input("Ingrese el valor del billete usado para pagar en pesos :"))
  #Llamamos la función
  Vueltas = cantidadVueltas(P, M, H, B)
  #Imprimimos el resultado
  print("Las vueltas correspondientes al mandado son de "+ str(Vueltas)+" pesos")
```
2. Del [Reto #8](https://github.com/Artuu1999/Reto-8-Bucles-2) escojeremos el punto número el cual consistía en crear un código que al ingresar un número natural x y elevarlo a la potencia de otro número natural ingresado. El código solución fue el siguiente:
```sh
x = int(input("Ingrese numero natural: ")) #Solicitar el ingreso de la base
n = int(input("Ingrese numero natural: ")) #Solicitar el ingreso del exponenete
potencia = 1 #Inicialzar el ciclo
for y in range (n): #Determinar el rango
    potencia *= x #Actualizar el ciclo
print("El resultado de "+str(x)+" elevado a la "+str(n)+" es "+str(x**n)+"") #Imprimir el resultado
```
Colocando las variables como argumentos no definidos se vería de la siguiente manera:
```sh
def potenciaNumero(*args) -> float:
  potencia = 1 #Inicialzar el ciclo
  for y in range(args[0]): #Determinar el rango
    potencia *= args[1] #Actualizar el ciclo
  return potencia

if __name__ == "__main__":
x = int(input("Ingrese numero natural: ")) #Solicitar el ingreso de la base
n = int(input("Ingrese numero natural: ")) #Solicitar el ingreso del exponenete
potencia = potenciaNumero(x,n) #Se llama la función
print("El resultado de "+str(x)+" elevado a la "+str(n)+" es "+str(potencia)+"") #Imprimir el resultado
```
3. Del [Reto #8](https://github.com/Artuu1999/Reto-8-Bucles-) escojeremos el punto número 4, que consiste en Diseñar un código, el cual al correrlo imprima los números hasta determinado número, con su respectivo número factorial
```sh
x : int = 1 #Inicializar la lista
n = int(input("Ingrese número: ")) #Ingresar el fin del rango
for y in range (1, n+1): #Indicar el rango de la lista
    x *= y #Actualizar las variables
print ("El factorial del número "+str(n)+" es "+str(x)+"") #Imprimir el listado finalmente
```
Utilizando argumentos args se vería de la siguiente manera
```sh
#Definimos las variables como argumentos
def factorialNumero(*args) -> float:
 x : int = 1 #Inicializar la lista
 for y in range (1,(args[0]+1)): #Indicar el rango de la lista
    x *= y #Actualizar las variables
 return x

if __name__ == "__main__":
 n = int(input("Ingrese número: ")) #Ingresar el fin del rango
 x = factorialNumero(n) #Llamamos la función definida anteriormente
 print ("El factorial del número "+str(n)+" es "+str(x)+"") #Imprimir el resultado finalmente
```
## Ejemplo No. 3
Usando la función recursiva, se debe diseñar un código, el cual al correrse, calcule la operación de la potencia.
El siguiente es el código solución al ejemplo número 3
```sh
#Definir la función con las variables
def potencia(n: int, x: int) -> int:
    #Usar el caso base del 0
    if x == 0:
        return 1
    #Usar el caso de una base elevada a un número
    elif x == 1:
        return n
    #Declarar el resto de casos
    else:
        return n * potencia(base, x - 1)
if __name__ == "__main__":
    #Se solicita el ingreso de las variables
    base = int(input("Ingrese la base de la potencia: ")) #Solicitar el ingreso de la potencia
    exponente = int(input("ingrese el valor del exponente: "))
    #Se llama la función
    resultado = potencia (base,exponente)
    #Imprimimos el resultado
    print ("la base "+str(base)+" elevada al exponente "+str(exponente)+" da como resultado "+str(resultado)+"")
```
Al ejecutarse en Visual Studio Code, se ve de la siguiente manera:

![image](https://github.com/Artuu1999/Reto-9-Funciones-2/assets/124615034/39062496-b864-421c-bc3b-46bc47d69dee)


## Ejemplo No. 4
Utilizar el siguiente código para contar el tiempo.
```sh
import time

start_time = time.time()
# instrucciones sobre las cuales se quiere medir tiempo de ejecución
end_time = time.time()

timer = end_time - start_time
print(timer)
```
Posteriormente se debe realizar pruebas para calcular Fibonacci mediante el uso ya sea de iteración o de recursión.
```sh
import time #Se importa el módulo del tiempo
# Se define la serie de Fibonacci mediante el mpetodo iterativo
def fibo(n : int )-> int:
  i : int = 1
  # caso base
  n1 : int = 0
  n2 : int = 1
  while(i <= n):
    # Condicion
    sumFibo = n1 + n2
    # Actualizacion
    n1 = n2
    n2 = sumFibo
    i += 1
  return sumFibo

#Se llaman las funciones, se solicita el ingreso de las variable y se importa el tiempo que tarda en realizar la función
if __name__ == "__main__":
  num = int(input("Ingrese numero: "))
  start_time1 = time.time()
  serieFibo = fibo(num)
  end_time1 = time.time()
  timer1 = end_time1 - start_time1
  print("La serie de Fibonacci hasta " + str(num) + " es " + str(serieFibo))
  print("La serie de Fibonacci calculada por el metodo iterativo se demoró: "+str(timer1)+"")

# Se define la serie de Fibonacci mediante el mpetodo recursivo  
def fiboRecursivo(n : int )-> int:
  if n <=1:
    # caso base
    return 1
  else:
    # condicion
    return fiboRecursivo(n-1)+fiboRecursivo(n-2)  

#Se llaman las funciones, se solicita el ingreso de las variable y se importa el tiempo que tarda en realizar la función

if __name__ == "__main__":
  num = int(input("Ingrese numero: "))
  start_time2 = time.time()
  serieFibo = fibo(num)
  end_time2 = time.time()
  timer2 = end_time2 - start_time2
  print("La serie de Fibonacci hasta " + str(num) + " es " + str(serieFibo))
  print("La serie de Fibonacci calculada por el metodo recursivo se demoró: "+str(timer2)+"")
```
Al ejecutarlo se ve de la siguiente manera:

![image](https://github.com/Artuu1999/Reto-9-Funciones-2/assets/124615034/524f9b05-2c33-4780-b56a-ef940af9fa8d)


## Cuenta en Stackoverflow
[Link de cuenta personal de stackoverflow](https://stackoverflow.com/users/21741261/arturo-moreno-covaria?tab=profile)
![image](https://user-images.githubusercontent.com/124615034/234468925-93f1a7c1-3a2e-4873-8f7f-294e0441d6cc.png)

## Cuenta Linkedin
[Link de cuenta personal de Linkedin](https://www.linkedin.com/in/arturo-moreno-covaria-076018274)
![image](https://user-images.githubusercontent.com/124615034/234472037-0bba3f8f-9fd4-46cd-a448-13a91ad51819.png)

## FIN
Hasta acá llega nuestro camino en el presente repo, espero que haya sido de tu interés, si encuentras algún error o alguna inconsistencia, no dudes en contactarme y hacermela saber.
Muchas Gracias por tu atención.

   **"La diferencia entre el poeta y el matemática es que el poeta intenta meter su cabeza en los cielos, mientras que el matemático intenta meter los cielos en su cabeza"**
