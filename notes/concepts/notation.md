# Notación

Referencia: sección 4 y tabla 3 del apéndice C del paper.

| Símbolo | Significado |
| --- | --- |
| a, A | Índice y cantidad de anunciantes |
| s, S | Índice y cantidad de slots |
| t, T | Índice y cantidad de segmentos |
| p_t | Probabilidad del segmento t |
| v_a | Vector de valoraciones del anunciante a |
| F_a | Distribución a priori del vector v_a |
| b_a | Vector de ofertas del anunciante a |
| α_s, β_t, γ_a | Factores de slot, segmento y anunciante en el CTR |
| x_ast | Probabilidad de asignar el slot s al anunciante a en el segmento t |
| m_a | Pago esperado del anunciante a |
| q | Cota ex ante sobre la probabilidad de asignación en el problema de un anunciante |
| M_a(q) | Mecanismo de un anunciante asociado a esa cota |
| Φ_a(q) | Curva de ingreso normalizada |
| R_as(q) | Curva de ingreso del anunciante a para el slot s: α_s γ_a Φ_a(q) |
| Q_at(v_a) | Mapeo del vector de valoraciones a un cuantil, condicionado al segmento |
| Ω_at(q) | Región de asignación del caso determinista |

**Nota:** q es un cuantil, no necesariamente un cuartil. Registrar por separado la cota q y la probabilidad de asignación efectivamente alcanzada; una restricción «a lo sumo q» no exige igualdad en general.
