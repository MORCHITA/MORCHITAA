import turtle

# Configuración de la ventana
ventana = turtle.Screen()
ventana.bgcolor("lightblue")  # Fondo azul claro para simular el cielo

# Crear la tortuga
flor = turtle.Turtle()
flor.speed(10)
flor.hideturtle()

# Función para dibujar un pétalo
def dibujar_petalo():
    flor.color("yellow")  # Pétalos amarillos
    flor.begin_fill()
    flor.circle(50, 60)  # Primer arco del pétalo
    flor.left(120)
    flor.circle(50, 60)  # Segundo arco del pétalo
    flor.left(120)
    flor.end_fill()

# Función para dibujar el centro de la flor
def dibujar_centro():
    flor.color("orange")
    flor.begin_fill()
    flor.circle(20)  # Centro de la flor
    flor.end_fill()

# Función para dibujar una flor completa
def dibujar_flor():
    for _ in range(6):  # Dibujar 6 pétalos
        dibujar_petalo()
        flor.right(60)  # Rotar para alinear el siguiente pétalo
    dibujar_centro()  # Dibujar el centro de la flor

# Función para dibujar el tallo
def dibujar_tallo():
    flor.color("green")
    flor.pensize(5)
    flor.right(90)
    flor.forward(100)

# Función para dibujar hojas
def dibujar_hojas():
    flor.color("green")
    flor.begin_fill()
    flor.circle(30, 90)  # Primer arco
    flor.left(90)
    flor.circle(30, 90)  # Segundo arco
    flor.left(180)
    flor.end_fill()

# Función para dibujar el florero
def dibujar_florero():
    flor.penup()
    flor.goto(-50, -300)
    flor.pendown()
    flor.color("brown")
    flor.begin_fill()
    flor.forward(100)  # Base del florero
    flor.left(90)
    flor.forward(150)  # Lado izquierdo
    flor.left(45)
    flor.forward(50)
    flor.left(45)
    flor.forward(100)  # Borde superior
    flor.left(45)
    flor.forward(50)
    flor.left(45)
    flor.forward(150)  # Lado derecho
    flor.left(90)
    flor.end_fill()

# Función para colocar flores en diferentes posiciones
def colocar_flor(x, y):
    flor.penup()
    flor.goto(x, y)
    flor.pendown()
    dibujar_flor()

# Función para dibujar tallo y hojas en diferentes posiciones
def colocar_tallo_hojas(x, y):
    flor.penup()
    flor.goto(x, y)
    flor.setheading(90)  # Asegurar que el tallo apunte hacia arriba
    flor.pendown()
    dibujar_tallo()

    # Dibujar las hojas
    flor.penup()
    flor.goto(x - 20, y - 50)
    flor.pendown()
    dibujar_hojas()

    flor.penup()
    flor.goto(x + 20, y - 50)
    flor.pendown()
    dibujar_hojas()

# Dibujar el florero
dibujar_florero()

# Dibujar tres flores con tallos y hojas
colocar_flor(0, -100)
colocar_tallo_hojas(0, -100)

colocar_flor(-100, -50)
colocar_tallo_hojas(-100, -50)

colocar_flor(100, -50)
colocar_tallo_hojas(100, -50)

# Mostrar la ventana hasta que el usuario cierre
ventana.mainloop()
