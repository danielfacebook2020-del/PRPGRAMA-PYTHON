# PRPGRAMA-PyTHON
FASE 5- código Python    # =====================================================================
# Curso: Fundamentos de Programación
# Fase 5 - Evaluación Final POA
# Problema 3: Auditoría de Inventarios
# Daniel Ordoñez Sanchez 
# =====================================================================

# REQ-01: Estructura de Datos (Matriz con 5 artículos)
inventario = [
    ["A001", "Filtro de Aceite", 12, 15],
    ["A002", "Pastillas de Freno", 25, 20],
    ["A003", "Bujía Premium", 5, 10],
    ["A004", "Líquido de Frenos", 8, 8],
    ["A005", "Cadena de Transmisión", 3, 7]
]

# REQ-02: Módulo de Cálculo de Pedido
def calcular_cantidad_a_pedir(stock_actual, stock_minimo):
    if stock_actual < stock_minimo:
        return stock_minimo - stock_actual
    else:
        return 0

# REQ-03: Generación de Reporte y Estructura de Repetición
def generar_reporte_auditoria(matriz_inventario):
    print("========================================")
    print("   REPORTE DE AUDITORÍA DE INVENTARIO   ")
    print("========================================")
    print(f"{'ARTÍCULO':<25} | {'CANTIDAD A PEDIR'}")
    print("----------------------------------------")
    
    for articulo in matriz_inventario:
        nombre = articulo[1]
        stock_actual = articulo[2]
        stock_minimo = articulo[3]
        
        pedido_exacto = calcular_cantidad_a_pedir(stock_actual, stock_minimo)
        
        print(f"{nombre:<25} | {pedido_exacto}")
    
    print("========================================")

if __name__ == "__main__":
    generar_reporte_auditoria(inventario)
