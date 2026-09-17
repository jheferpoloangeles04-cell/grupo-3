def mostrar_menu():
    print("\n" + "=" * 45)
    print("   SISTEMA DE SOPORTE ACADÉMICO")
    print("=" * 45)
    print("1. Registrar nueva solicitud")
    print("2. Mostrar resumen de solicitudes")
    print("3. Salir")
    print("=" * 45)

# --- FUNCIONES DE VALIDACIÓN FALTANTES ---

def validar_codigo(codigo):
    if not codigo.strip():
        print("  ❌ Error: El código no puede estar vacío.")
        return False
    return True

def validar_texto(texto, nombre_campo):
    if not texto.strip():
        print(f"  ❌ Error: El campo '{nombre_campo}' no puede estar vacío.")
        return False
    return True

def validar_tipo_consulta(tipo):
    tipos_validos = ["matrícula", "matricula", "pagos", "constancia", "plataforma", "otro"]
    if tipo.lower().strip() not in tipos_validos:
        print("  ❌ Error: Tipo de consulta no válido. (Use: matrícula/pagos/constancia/plataforma/otro)")
        return False
    return True

def calcular_prioridad(tipo):
    tipo_normalizado = tipo.lower().strip()
    if tipo_normalizado in ["plataforma", "pagos"]:
        return "Alta"
    elif tipo_normalizado in ["matrícula", "matricula"]:
        return "Media"
    else:
        return "Baja"

# --- FUNCIONES DE VISUALIZACIÓN FALTANTES ---

def mostrar_resumen(solicitud):
    print("\n--- RESUMEN DE LA SOLICITUD RECIENTE ---")
    print(f"Estudiante: {solicitud['nombre']} ({solicitud['codigo']})")
    print(f"Asunto: {solicitud['tipo'].capitalize()} | Prioridad: {solicitud['prioridad']}")

def mostrar_todas_las_solicitudes(solicitudes):
    if not solicitudes:
        print("\n  📂 No hay solicitudes registradas actualmente.")
        return
    
    print("\n" + "=" * 45)
    print("   LISTADO DE SOLICITUDES REGISTRADAS")
    print("=" * 45)
    for i, sol in enumerate(solicitudes, 1):
        print(f"{i}. [{sol['prioridad'].upper()}] {sol['codigo']} - {sol['nombre']} ({sol['tipo']})")
        print(f"   Desc: {sol['descripcion']}")
    print("=" * 45)

# --- CÓDIGO ORIGINAL ---

def registrar_solicitud():
    print("\n--- REGISTRO DE NUEVA SOLICITUD ---")
    codigo = input("Ingrese código de estudiante: ")
    if not validar_codigo(codigo):
        return None
    
    nombre = input("Ingrese nombre del estudiante: ")
    if not validar_texto(nombre, "nombre"):
        return None
    
    tipo = input("Ingrese tipo de consulta (matrícula/pagos/constancia/plataforma/otro): ")
    if not validar_tipo_consulta(tipo):
        return None
    
    descripcion = input("Ingrese descripción breve: ")
    if not validar_texto(descripcion, "descripción"):
        return None
    
    prioridad = calcular_prioridad(tipo)
    solicitud = {
        "codigo": codigo.strip(),
        "nombre": nombre.strip(),
        "tipo": tipo.lower().strip(),
        "descripcion": descripcion.strip(),
        "prioridad": prioridad
    }
    print(f"\n  ✅ Solicitud registrada con prioridad {prioridad}.")
    return solicitud

# Archivo principal del sistema
# Orlando correa Flores
def main():
    solicitudes = []
    opcion = ""
    while opcion != "3":
        mostrar_menu()
        opcion = input("Seleccione una opción: ").strip()
        
        if opcion == "1":
            if len(solicitudes) >= 3:
                print("\n  ⚠ Ya se registraron 3 solicitudes (límite de la práctica).")
                continue
            nueva = registrar_solicitud()
            if nueva is not None:
                solicitudes.append(nueva)
                mostrar_resumen(nueva)
                
        elif opcion == "2":
            mostrar_todas_las_solicitudes(solicitudes)
            
        elif opcion == "3":
            print("\n  👋 Saliendo del sistema. ¡Hasta luego!")
            
        else:
            print("\n  ❌ Opción inválida. Intente de nuevo.")

if __name__ == "__main__":
    main()﻿print("¡Hola, mundo desde mi rama de funcionalidad!")
