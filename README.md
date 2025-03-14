# Adivina-el-numero
Importación de la biblioteca
python
Copiar
Editar
import random
Se importa la biblioteca random, que es una biblioteca estándar de Python.
random permite generar números aleatorios.
2. Definición de la función principal main()
python
Copiar
Editar
def main():
Se define la función main() que contiene la lógica principal del juego.
El código que sigue dentro de la función es el que controla el flujo del juego.
3. Mensaje de bienvenida
python
Copiar
Editar
    print("=== ADIVINA EL NÚMERO ===")
    print("Estoy pensando en un número entre 1 y 100...\n")
Muestra un mensaje inicial para indicar al usuario que el juego ha comenzado.
El número estará entre 1 y 100.
4. Generar el número secreto
python
Copiar
Editar
    numero_secreto = random.randint(1, 100)
    intentos = 0
Usa random.randint(1, 100) para generar un número aleatorio entre 1 y 100.
La variable intentos se inicializa en 0 para contar el número de intentos.
5. Bucle para permitir múltiples intentos
python
Copiar
Editar
    while True:
El bucle while permite que el usuario siga intentando hasta que acierte el número.
El bucle solo se detendrá cuando el usuario adivine correctamente el número.
6. Captura de la entrada del usuario
python
Copiar
Editar
        intento = int(input("Introduce tu suposición: "))
        intentos += 1
input() solicita al usuario que introduzca un número.
int() convierte la entrada de texto a un valor entero.
Si la conversión falla (porque el valor introducido no es numérico), se lanza una excepción ValueError.
Cada intento válido incrementa el contador intentos.
7. Proporcionar pistas al usuario
python
Copiar
Editar
        if intento < numero_secreto:
            print("🔼 El número es mayor. Intenta de nuevo.\n")
        elif intento > numero_secreto:
            print("🔽 El número es menor. Intenta de nuevo.\n")
        else:
            print(f"🎉 ¡Felicidades! Has adivinado el número {numero_secreto} en {intentos} intentos.")
            break
Si el número introducido es menor que el número secreto → muestra una pista indicando que el número es mayor (🔼).
Si el número introducido es mayor que el número secreto → muestra una pista indicando que el número es menor (🔽).
Si el número introducido es igual al número secreto → muestra un mensaje de éxito, indicando el número secreto y la cantidad de intentos realizados.
El juego finaliza cuando el usuario adivina el número (gracias al break).
8. Manejo de errores
python
Copiar
Editar
    except ValueError:
        print("❌ Error: Introduce solo números enteros.\n")
Si el usuario introduce un valor inválido (como letras o símbolos), el programa muestra un mensaje de error.
El juego sigue ejecutándose después de mostrar el mensaje de error.
9. Ejecución directa del script
python
Copiar
Editar
if __name__ == "__main__":
    main()
if __name__ == "__main__": permite que el script se ejecute directamente desde la terminal o desde un entorno de desarrollo.
Llama a la función main() para iniciar el juego.
