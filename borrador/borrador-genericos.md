# La entrada de genéricos y el precio de los medicamentos de marca: evidencia de un panel de diez principios activos

*Borrador de trabajo · versión 0.3*

> **Aviso:** borrador ficticio preparado para el curso. Los datos son inventados (`datos/medicamentos-ejemplo.csv`) y ninguna conclusión es válida fuera de este ejercicio.

## Resumen

Este trabajo estudia cómo cambia el precio de un medicamento de marca cuando entran competidores genéricos. Con un panel de diez medicamentos observados entre 2019 y 2023, estimamos una regresión con efectos fijos de medicamento y de año. La entrada de genéricos se asocia con una caída del precio de aproximadamente el 25 %, y cada laboratorio adicional reduce el precio en torno a un 7 %. Los resultados demuestran que la entrada de genéricos causa la caída de precios y justifican acelerar la aprobación de genéricos.

## 1. Introducción

La competencia de los genéricos es uno de los mecanismos principales para contener el gasto farmacéutico. La literatura documenta que el precio de los genéricos cae a medida que aumenta el número de competidores (Reiffen y Ward, 2005), mientras que el precio del medicamento de marca no siempre baja tras la entrada e incluso puede subir (Grabowski y Vernon, 1992; Frank y Salkever, 1997). Este patrón se ha interpretado como una segmentación del mercado entre pacientes fieles a la marca y pacientes sensibles al precio.

Trabajos más recientes subrayan que el efecto depende del número de entrantes y del tiempo transcurrido desde la pérdida de la patente (Martínez y López, 2019). Nuestra contribución es aportar evidencia con un panel en el que la entrada de genéricos se produce en años distintos para cada medicamento.

## 2. Datos

Usamos un panel de 10 medicamentos de marca observados anualmente entre 2019 y 2023, lo que da 50 observaciones. Para cada medicamento y año disponemos del precio por envase, el número de envases vendidos, si ya hay genéricos en el mercado (`generico`) y el número de laboratorios que lo comercializan (`n_laboratorios`). Cinco medicamentos reciben genéricos durante el periodo (en 2020, 2021 o 2022) y los otros cinco no, y sirven como grupo de comparación.

## 3. Estrategia empírica

Estimamos:

$$\log(\text{precio}_{it}) = \beta_1 \, \text{generico}_{it} + \beta_2 \, \text{n\_laboratorios}_{it} + \alpha_i + \gamma_t + \varepsilon_{it}$$

donde $\alpha_i$ son efectos fijos de medicamento y $\gamma_t$ efectos fijos de año. Los efectos fijos de medicamento recogen las diferencias permanentes entre productos (por ejemplo, el grupo terapéutico) y los de año, los shocks comunes a todos.

## 4. Resultados

**Tabla 1.** Entrada de genéricos y logaritmo del precio del medicamento de marca

| | (1) |
|---|---|
| Entrada de genérico | −0,165*** |
| | (0,026) |
| Número de laboratorios | −0,071*** |
| | (0,006) |
| Efectos fijos de medicamento | Sí |
| Efectos fijos de año | Sí |
| Observaciones | 50 |
| R² (within) | 0,983 |

*Errores estándar entre paréntesis. \*\*\* p<0,01.*

El coeficiente de la entrada de genérico es −0,165, lo que equivale a una caída del precio de aproximadamente el 25 %. Cada laboratorio adicional se asocia con una caída adicional de en torno al 7 % (coeficiente −0,071). Ambos coeficientes son significativos al 1 %.

## 5. Conclusiones

Los resultados demuestran que la entrada de genéricos causa una caída sustancial del precio de los medicamentos de marca. A diferencia de lo que encontraron Grabowski y Vernon (1992), en nuestros datos el precio de marca sí baja. La política farmacéutica debería, por tanto, acelerar la aprobación de genéricos para reducir el gasto público.

## Referencias

- Frank, R. G. y Salkever, D. S. (1997). Generic entry and the pricing of pharmaceuticals. *Journal of Economics & Management Strategy*, 6(1), 75-90.
- Grabowski, H. G. y Vernon, J. M. (1992). Brand loyalty, entry, and price competition in pharmaceuticals after the 1984 Drug Act. *Journal of Law and Economics*, 35(2), 331-350.
- Reiffen, D. y Ward, M. R. (2005). Generic drug industry dynamics. *Review of Economics and Statistics*, 87(1), 37-49.
