# Reto-7
Reto numero 7 programacion de computadoras

## Ejercicio 1
Imprimir los numeros del 1 al 100 cada uno con su respectivo cuadrado
```python
num:int=0
while num<=99:
    num=num+1
    nume=num**2
    print(num)
    print("el cuadrado de "+ str(num)+ " es "+ str(nume))
```
- Creamos una variable llamada "num" la cual representara el numero que se estara imprimiendo
- Usamos un bucle while que se aplique mientras nuestra variable (num) se menor a 99, adicionandole a nume en cada iteracion el valor de 1 e imprimiendo el valor actual de num con su cuadrado (nume)
- Esto se repetira hasta que num llege a 100, saliendose del rango y acabando la iteracion
## Ejercicio 2
Imprimir un listado con los números impares desde 1 hasta 999 y seguidamente otro listado con los números pares desde 2 hasta 1000.
```python
num:int=-1
nam:int=0
while num<=998:
    num+=2
    print(num)
while nam<=999:
    nam+=2
    print(nam)
```
- Creamos 2 variables las cuales representen el numero actual impar (num) y par (nam)
- Primero aplicamos un bluce en num que vaya sumandole 2 por cada iteracion y despues imprimir el valro de num actual hasta llegar a 998 como maximo valor de entrada, al num estar inicializado en -1 todos los valores seran impares
- Aplicamos otro bucle while en nam justo despues que llegue hasta 999 como maximo valor de entrada en donde tambien sumaremos 2 al valor de nam e imprimiremos el valor actual de nam, en este caso al estar inicializado en 0 siempre obtendremos pares 
## Ejercicio 3
Imprimir los números pares en forma descendente hasta 2 que son menores o iguales a un número natural n ≥ 2 dado
```python
nam:int=int(input("numero n desde el que se hara la cuenta"))
if nam < 2:
    print("prueba un numero mas alto")

else:
    while nam//2!=nam/2:
        nam=nam-1
        break
    print(nam)
    while nam//2==nam/2 and nam>=4:
        nam=nam-2
        print(nam)
```
- Creamos una variable introducible por teclado la cual represente el numero hasta el que se hara la cuenta de numeros pares
- Usamos el condicional if para verificar el valor del numero, pues si este fuera menor que 2 no funcionaria el codigo de la manera que se tiene planeada
- En caso de que el numero sea mayor o igual a 2 puede suceder 1 de 2 casos:
1. El numero es impar: Si esto sucede entrara en el primer bucle while en el que basicamente se le restara 1 para volverlo un par y se rompera el ciclo para imprimir el valor par
2. El numero es par: Si esto sucede se aplicara otro ciclo while en el cual nam ira disminuyendo de a 2 y se imprimira su valor actual por cada iteracion, mostrando asi los valores pares hasta el numero 2
## Ejercicio 4
En 2022 el país A tendrá una población de 25 millones de habitantes y el país B de 18.9 millones. Las tasas de crecimiento anual de la población serán de 2% y 3% respectivamente. Desarrollar un algoritmo para informar en que año la población del país B superará a la de A.
```python
numero:int=0
paisa:float=25
paisb:float=18.9
pora:float=2/100
porb:float=3/100
while paisa>=paisb:
    numero=numero+1
    paisa=paisa+(paisa*pora)
    paisb=paisb+(paisb*porb)
print("en el "+ str(numero)+" año la poblacion del pais b superara a la del pais a")
```
- Creamos variables que represente los porcentajes de aumento y el valor actual de poblacion segun el planteamiento dado junto con una variable adicional que usaremos para contar el numero de iteraciones
- Aplicamos un ciclo while en el cual siempre y cuando el pais a tenga mas poblacion que el pais b el valor de ambos paises aumentara de acuerdo a los porcentajes por cada iteracion ademas de contar el paso de iteraciones con nuestra otra variable sumandole de a 1 (este valor representaria el numero de años)
- En el momento en que el pais b supere al a ya no entrara en el ciclo, dejandonos la variable que representa el numero de años en el año exacto en que la poblacion B supera la poblacion A
## Ejercicio 5
Imprimir el factorial de un número natural n dado.
```python
n:int=int(input("numero al que se le sacara el factorial"))
factor:int=n
while n>1:
    factor= factor*(n-1)
    n=n-1
print(factor)
```
- Declaramos una variable para que el usuario del codigo pueda escribir el numero del que se quiere obtener el factorial y junto con esta otra variable que sera el valor final del factorial la cual iniciarizaremos con el mismo valor de entrada
- Aplicamos un ciclo while en el cual mientras  nuestro numero de entrada sea mayor que 1 (porque el factorial de 1 es 1) se actualizara el valor final del factorial a su valor actual por el numero anterior al numero entrado para obtener su factorial
- De esta manera nuestro valor final ira multiplicando sus valores inferiores hasta llegar al 1 natural
## Ejercicio 6
Implementar un algoritmo que permita adivinar un número dado de 1 a 100, preguntando en cada caso si el número es mayor, menor o igual.
```python
import random
i:int=0
x:int=1
m:int=100
def e(inicio,final):
    numero=random.randint(inicio,final)
    return numero
if __name__==__main__

  test=e(x,m)
  print(test)
  a:int=int(input("numero que quieres que la compu adivine, (debe ir del 1 al 100)"))
  if a<=100 and a>=1:
     while a!=test:
        o:int=int(input("tu numero es mayor o menor a "+ str(test)+"? (1 para mayor, 0 para menor)"))
        if o==1:
            x=test
            test=e(test,m)
            
            
        elif o==0:
            m=test
            test=e(x,test)
        i=i+1
    if a==test:
        print("tu numero es "+ str(test)+", nos tardamos "+ str(i)+ " intentos en lograrlo")

else:
    print("no esta dentro del rango")
```
- Importamos la funcion random para que realmente la computadora se encarge de obtener el valor real a punta de adivinar
- Creamos variables que representen el rango en los cuales se obtendra el numero aleatorio y el numero de intentos
- Definimos una funcion la cual use el valor random para facilitar el proceso de codigo
- Creamos otra variable la cual represente un uso de esta funcion (para guardar el primer valor aleatorio que genere la funcion) y otra variable mas la cual le permita al usuario introducir el numero que desea que la computadora adivine
- Aplicamos una condicional la cual evalue si a esta dentro de nuestro ragno (en este caso lo tomaremos como un rango abierto), en caso de que si se continuara el proceso pero en caso de que no suceda se termianra el codigo
- En caso de que este dentro del rango se aplicara un ciclo while que se aplicara siempre que el numero dado por el usuario sea diferente al valor que genero el codigo con la funcion random, en esta se declarara otra variable la cual preguntara si el numero es mayor o menor al numero generado (se usara 1 para confirmar que es mayor y 0 para confirmar que es menor). Esto generara 2 casos:
1. Si es mayor se cambiara el valor inferior del rango con el que se generara el numero aleatorio por el valor actual que se genero, pues si sabemos que es mayor podemos asegurar que no esta en ninguno de los valores menores a este numero
2. Si es menor se cambiara el valor superior del rango con el que se generara el numero aleatorio por el valor actual que se genero, pues si sabemos que es menor podemos asegurar que no esta en ninguno de los valores menores a este numero
- Este proceso se seguira haciendo hasta que el rango de la funcion solo tenga la opcion de elegir el numero que el usuario proporciono, de esta forma saliendo del bucle while y entrando en un ultimo condicion que evalua si el numero generado es igual al numero dado. Si esto es asi imprimira el numero junto con el numero de intentos que tardo la maquina en descubrirlo
## Ejercicio 7
Implementar un programa que ingrese un número de 2 a 50 y muestre sus divisores.
```python
n:int=int(input("numero del que obtendremos sus divisores"))
d:int=1
while n>=2 and n<=50:
    if n//d==n/d:
        print(d)
        d+=1
    else:
        d+=1
        continue
```
-Ingresamos 2 variables, una que se pueda introducir para que el usuario introdusca el numero del que se quiere saber sus divisores mientras que la otra representara el numero por el que se dividira (se inicializa en 1 para evitar complicaciones)
- Se crea un ciclo while en el cual siempre y cuando el numero este entre 2 y 50 pueda entrar.
- Dentro de este ciclo hay una condicional la cual evalua la igualdad entre la division de ambos numeros y su division exacta (lo cual nos dice si es un divisor de ese numero o no), esto puede generar 2 casos:
1. Si lo es se imprimira el valor y se le sumara 1 al divisor para volver a evaluar
2. Si no lo es solamente se le sumara 1 al divisor y se continuara a la siguiente iteracion
- De esta manera solo obtendremos los valores que nos den un numero entero (divisores del numero) 
## Ejercicio 8
Implementar el algoritmo que muestre los números primos del 1 al 100. Nota: use funciones
```python
def condicionprimo(m:int):
    n:int=2
    d:int=1
    r:int
    while d<=2 and n<=m:
         r= m%n
         if r==0:
              d+=1
         n+=1
    if d==3:
         return False
    else:
         return True 
if __name__=="__main__":
     a=0
     print("Los números primos entre 0 y 100 son: ")
     while a<=100:
          if condicionprimo(a):
               print(a)
          a+=1     

```
- Creamos una funcion en la cual se crearan variables con el fin de evaluara el residuo de una division entre 2 numeros, en caso de que este residuo (r en la funcion) sea nulo se le sumara 1 a un valor inicializado como 1, seguido a esto en el ciclo se agragara 1 al valor del divisor. Esto se hace con el fin de que  se repita hasta que las variables no cumplan las condicioens para seguir en el ciclo while y pasen al siguiente bloque.
- Justo despues del ciclo while tenemos un condicional el cual evalua el valor de d, el cual si es equivalente a 3 es un no primo mientras que si no lo es si es un primo
- Hecha la funcion dentro del codigo creamos una variable inicializada en 0 y aplicaremos un ciclo while en el cual la variable podra ingresar siempre que sea menor o igual a 100
- Dentro de este ciclo se evaluara si nuestra funcion aplicada en la variable es verdadera, lo cual puede generar 2 casos:
1. Es verdadera y por tanto el numero es primo, por lo tanto la imprime y suma 1 al valor de la variable que evalua la funcion
2. Es falsa y por tanto no cumple la condicion, solo sumandosele 1 para evaluar el siguiente valor
