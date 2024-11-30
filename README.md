## Guia-Tkinter-Pyhton
Guia basica y rapida para hacer aplicaciones graficas con Tkinter

## ¿Qué es Tkinter?

#### Es la biblioteca estándar de Python para crear interfaces gráficas (GUI).
#### Viene preinstalada con Python, no necesitas instalar nada adicional.
##
## Crear tu primera ventana

#### El primer paso es crear la ventana principal de tu app:

    import tkinter as tk

    # Crear la ventana principal
    root = tk.Tk()
    root.title("Mi Primera App")
    root.geometry("400x300")  # Tamaño de la ventana (ancho x alto)

    # Iniciar el loop de la aplicación
    root.mainloop()
##
## Agregar etiquetas (Labels)

#### Para mostrar texto o información en tu ventana:

    tk.Label(root, text="Codigo Cesar", font=("Arial", 14), fg="#17e600", bg="#000000").pack(pady=20) 


#### text: Contenido del texto.
#### font: Fuente y tamaño.
#### fg: Color.
#### bf: Color de fondo.
#### pack(): Posiciona el widget de forma automática.

##
## Botones

#### Los botones ejecutan acciones al hacer clic en ellos:

    def mi_accion():
        print("¡Hiciste clic en el botón!")

    tk.Button(root, text="Clic aquí", command=mi_accion, bg="blue", fg="white").pack(pady=10)

#### command: La función que se ejecuta al hacer clic.
#### bg y fg: Color de fondo y texto.

##
## Entradas de texto

#### Para permitir que el usuario escriba:

    entrada = tk.Entry(root, font=("Arial", 14))
    entrada.pack(pady=10)

    def mostrar_texto():
        texto = entrada.get()  # Obtener el texto escrito
        print(f"Escribiste: {texto}")

    tk.Button(root, text="Mostrar texto", command=mostrar_texto).pack()

##
## Ventanas organizadas (Frames)
#### Para organizar mejor tus widgets:

    frame = tk.Frame(root, bg="lightgray")
    frame.pack(fill="both", expand=True, padx=10, pady=10)

    tk.Label(frame, text="Esto está dentro de un frame").pack()
    tk.Button(frame, text="Botón en el frame").pack()

##
## Crear una app completa

#### Una app básica de suma de dos números:

    import tkinter as tk

    # Función para sumar
    def sumar():
        try:
            num1 = float(entrada1.get())
            num2 = float(entrada2.get())
            resultado.set(f"Resultado: {num1 + num2}")
        except ValueError:
            resultado.set("Por favor ingresa números válidos.")

    # Ventana principal
    root = tk.Tk()
    root.title("Calculadora Básica")
    root.geometry("300x200")

    # Widgets
    tk.Label(root, text="Número 1").pack()
    entrada1 = tk.Entry(root)
    entrada1.pack()

    tk.Label(root, text="Número 2").pack()
    entrada2 = tk.Entry(root)
    entrada2.pack()

    tk.Button(root, text="Sumar", command=sumar, bg="green", fg="white").pack(pady=10)

    resultado = tk.StringVar()  # Variable para mostrar el resultado
    tk.Label(root, textvariable=resultado, font=("Arial", 14)).pack()

    # Iniciar la app
    root.mainloop()

##
## Extras (Opcionales)

#### Colores: Usa códigos hexadecimales (#RRGGBB) para colores personalizados.
#### Fuentes personalizadas: Usa paquetes como tkFont para más opciones.
#### Scrollbars y texto largo:

    from tkinter import scrolledtext

    texto_largo = scrolledtext.ScrolledText(root, wrap="word")
    texto_largo.pack(fill="both", expand=True)

