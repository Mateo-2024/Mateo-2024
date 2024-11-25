Título: Generador de Contraseñas Seguras

Descripción: Este proyecto genera contraseñas seguras personalizables en longitud y tipos de caracteres.

Objetivos:
Implementar una herramienta segura para generar contraseñas.
Facilitar el uso mediante una interfaz básica.
![image](https://github.com/user-attachments/assets/782bdd7f-e68f-4fb9-9f60-7168c3a0a1bf)

import random
import string

def generar_contraseña(longitud, incluir_mayusculas, incluir_numeros, incluir_simbolos):
    caracteres = string.ascii_lowercase  # Minúsculas
    
    if incluir_mayusculas:
        caracteres += string.ascii_uppercase
        
    if incluir_numeros:
        caracteres += string.digits
        
    if incluir_simbolos:
        caracteres += string.punctuation

    if len(caracteres) == 0:
        return "Error: Selecciona al menos un tipo de carácter."
    
    contraseña = ''.join(random.choice(caracteres) for _ in range(longitud))
    return contraseña

# Interfaz en consola
def main():
    print("Bienvenido al Generador de Contraseñas Seguras")
    try:
        longitud = int(input("Introduce la longitud de la contraseña (mínimo 8): "))
        if longitud < 8:
            print("La longitud debe ser al menos 8 caracteres.")
            return
        
        incluir_mayusculas = input("¿Incluir letras mayúsculas? (s/n): ").lower() == 's'
        incluir_numeros = input("¿Incluir números? (s/n): ").lower() == 's'
        incluir_simbolos = input("¿Incluir símbolos especiales? (s/n): ").lower() == 's'
        
        contraseña = generar_contraseña(longitud, incluir_mayusculas, incluir_numeros, incluir_simbolos)
        print(f"Tu contraseña generada es: {contraseña}")
    except ValueError:
        print("Error: Por favor, introduce valores válidos.")

if __name__ == "__main__":![Uploading image.png…]()

    main()

