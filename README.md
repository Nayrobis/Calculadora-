# FinanCalc — Calculadora financiera React

Proyecto educativo **mobile first** usando React, Vite y CSS sin librerías adicionales de interfaz.

## Requisitos
Node.js 20.19+ o 22.12+ y npm.

## Instalación
```bash
npm install
npm run dev
```
Abre la URL local indicada por Vite.

## Construir para producción
```bash
npm run build
npm run preview
```

## Arquitectura
- `src/App.jsx`: componente padre; estado, eventos, validación y coordinación.
- `src/components/Header.jsx`: cabecera.
- `src/components/CalculatorTabs.jsx`: selector de modalidad.
- `src/components/CalculatorForm.jsx`: formulario.
- `src/components/NumberField.jsx`: campo numérico reutilizable.
- `src/components/ResultCard.jsx`: visualización de resultados.
- `src/utils/finance.js`: funciones financieras independientes de React.
- `src/styles.css`: estilos mobile first y media queries.

## Fórmulas
- Interés simple: `I = P * r * t`.
- Interés compuesto mensual: `A = P * (1 + r/12) ** (12*t)`.
- Préstamo con cuotas iguales: `C = P * i / (1 - (1+i)**(-n))`, con `i=r/12`, `n=12*t` (redondeado a meses enteros). Si `i=0`, `C=P/n`.
- Ahorro: proyección de un depósito único inicial con capitalización mensual, **sin aportaciones periódicas**.

La tasa se introduce como porcentaje **anual nominal**. Se convierte a decimal dividiendo por 100. El plazo se expresa en años; para préstamos se redondea a meses enteros. Los cálculos son aproximados y no incluyen cargos, impuestos, seguros ni condiciones particulares de entidades financieras.

## Ejercicios sugeridos
1. Añade una moneda seleccionable.
2. Crea una tabla de amortización para el préstamo.
3. Añade aportes mensuales al simulador de ahorro.
4. Guarda las últimas cinco simulaciones en localStorage.
5. Escribe pruebas para tasa cero y montos inválidos.
