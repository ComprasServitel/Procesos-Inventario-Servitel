# Procesos-Inventario-Servitel
<div align="center">
  <h1>MANUAL DE PROCESOS: GESTIÓN DE INVENTARIO Y COMPRAS</h1>
  <p><strong>Servitel Holding</strong></p>
</div>

---

## 1. Introducción
Este repositorio centraliza la visualización de los flujos de trabajo del área administrativa de **Servitel**. El objetivo es estandarizar los procedimientos de adquisición, almacenamiento y despacho de materiales para optimizar la operatividad de la empresa bajo la supervisión de la Gerencia de Compras e Inventario.

## 2. Flujograma de Operaciones
A continuación, se presenta la estructura lógica del movimiento de activos y suministros:

```mermaid
graph TD
    %% Definición de Nodos
    Inicio((Inicio del Requerimiento)) --> Validar{Validación de Existencias}
    
    Validar -- Stock Disponible --> Despacho[Asignación a Zona/Técnico]
    Validar -- Sin Stock --> Requisicion[Generación de Requisición de Compra]
    
    Requisicion --> Finanzas{Aprobación Finanzas}
    
    Finanzas -- Aprobado --> Orden[Emisión de Orden de Compra]
    Finanzas -- Rechazado --> Revision[Revisión de Presupuesto]
    
    Orden --> Recepcion[Recepción en Almacén Central]
    Recepcion --> Auditoria[Auditoría y Codificación]
    Auditoria --> Despacho
    
    Despacho --> Fin((Fin del Proceso))

    %% Estilos Corporativos
    style Inicio fill:#41d148,stroke:#333,stroke-width:2px,color:#fff
    style Fin fill:#41d148,stroke:#333,stroke-width:2px,color:#fff
    style Despacho fill:#0873a7,stroke:#333,stroke-width:2px,color:#fff
    style Orden fill:#0873a7,stroke:#333,stroke-width:2px,color:#fff
    style Recepcion fill:#0873a7,stroke:#333,stroke-width:2px,color:#fff
