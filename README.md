# ==========================================
# PROYECTO FINAL: Sistema de Registro Académico
# Asignatura: Programación Estructurada
# Estudiante: [Moises Haniel Gutierrez Salazar]
# ==========================================

# PASO 1: Estructura de Datos
# Lista vacía para guardar los datos de todos los alumnos
estudiantes = []

print("--- SISTEMA DE REGISTRO DE CALIFICACIONES ---")

# Utilizamos un ciclo for para registrar a 3 estudiantes
for i in range(3):
    print(f"\n--- Ingresando datos del Estudiante {i+1} ---")
    nombre = input("Nombre y Apellido: ")

    # PASO 2: Validaciones con try-except
    # ---> INICIO DE TU CÓDIGO <---
    try:
        # Pedimos las notas y convertimos a número decimal
        nota1 = float(input("Nota del Parcial 1: "))
        nota2 = float(input("Nota del Parcial 2: "))

        # Aseguramos que las notas no sean negativas (opcional pero recomendado)
        if nota1 < 0:
            nota1 = 0.0
        if nota2 < 0:
            nota2 = 0.0

    except ValueError:
        print("Error: Ingresaste un valor no válido. Se asignará 0 a ambas notas.")
        nota1 = 0.0
        nota2 = 0.0
    # ---> FIN DE TU CÓDIGO <---

    # Calculamos la nota final
    nota_final = (nota1 + nota2) / 2

    # Guardamos los datos del estudiante en nuestra lista principal
    estudiantes.append([nombre, nota1, nota2, nota_final])

# PASO 3: Evaluación de Resultados
print("\n==========================================")
print("REPORTE FINAL DE ESTUDIANTES")
print("==========================================")

for alumno in estudiantes:
    # Extraemos los datos de la lista
    nombre_alumno = alumno[0]
    promedio = alumno[3]

    estado = ""
    # PASO 4: Condicionales lógicos
    # < 60 = Reprobado | > 95 = Sobresaliente | El resto = Aprobado
    # ---> INICIO DE TU CÓDIGO <---
    if promedio < 60:
        estado = "Reprobado"
    elif promedio > 95:
        estado = "Sobresaliente"
    else:
        estado = "Aprobado"
    # ---> FIN DE TU CÓDIGO <---

    print(f"Estudiante: {nombre_alumno} | Promedio: {promedio:.2f} | Estado: {estado}")
