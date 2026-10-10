# Notas de lectura: artículos de Joaquín (revisión 07-10-2026)

Notas para que Carlos complete la parte gris de `Matriz_Joaquin.xlsx`. Solo se cambió la parte amarilla de los Excel. Los criterios usados son los de la Tabla 10 del documento SIA (CI1–CI5 y CE1–CE4) y las rondas de la guía de Joaquín.

**Cuartiles:** ninguno está verificado. Scimago bloquea el acceso automático, así que hay que revisarlos a mano y guardar la captura.

## Preseleccionados (Matriz, filas 5–9)

| # | Artículo | PDF | País | Lectura |
|---|---|---|---|---|
| 1 | Ajagbe et al. (2025), *Discover Artificial Intelligence* | Sí | Sudáfrica | **Se mantiene con nota.** Compara XGBoost, KNN, RF, Isolation Forest y SVM con el dataset IBM AML de Kaggle, que es sintético aunque el artículo lo llama "real". Gana XGBoost, un modelo supervisado, con accuracy 1,00. Isolation Forest tiene AUC 0,62. **No compara contra sistemas de reglas.** El AUC de XGBoost aparece como 0,94 en un lugar y 0,62 en otro. Hay que corregir el Cap. 1, que en Antecedentes y en Formulación le atribuye que "la detección de anomalías supera a las reglas simples". |
| 2 | Bakry et al. (2024), *J. Supercomputing* | Sí | Egipto | ASXAML: XGBoost + RFECV + Optuna para suprimir alertas falsas de un sistema de reglas. Datos reales de un banco: 46 escenarios y 210 996 clientes con alerta en 6 meses. Resultados: F-beta 0,86, recall 0,92 y 73 % menos falsos positivos. Es supervisado (usa la decisión del analista como etiqueta). Responde P1, P2, P3, P5. |
| 3 | Kungu et al. (2026), *ML with Applications* | **Falta** | Kenia (afiliación en Scopus) | No se pudo descargar. DOI corregido a 10.1016/j.mlwa.2026.100856. |
| 4 | Luo et al. (2024), *IEEE TIFS* | **Falta** | Pendiente | Es de pago. Hay que bajarlo de la biblioteca UPC. |
| 5 | Reite et al. (2025), *J. Money Laundering Control* | Sí (versión aceptada del autor) | Noruega | Clasificación de riesgo del cliente con datos reales de BN Bank: PYMES, 500 767 observaciones, 2021–2023. Prueba XGBoost, LGBM y HistGB. El AUC es 0,94 combinando datos bancarios, de crédito y contables, y baja a 0,81–0,85 con solo datos bancarios. **Limitación para Perumoney:** una casa de cambio no tiene datos contables ni de crédito de personas naturales. Responde P2, P3, P4. |

## Candidatos (Candidatos_Joaquin.xlsx)

- **Ronda 1 (título):** 17 siguen y 9 salen. Salen un survey, un review, uno de blockchain, cinco de leyes, ética o gobernanza, y Kungu porque está duplicado.
- **Ronda 2 (resumen):** 16 siguen. Sale "Predicting money laundering sanctions" porque predice sanciones a países, no operaciones.
- **Ronda 4, por lectura del PDF:** salen Ouf (fila 4) y Ruchay (fila 6). Los dos son fraude de tarjetas de crédito con datasets de Kaggle, no lavado de activos.

### Leídos y pendientes de cuartil

| Fila | Artículo | Revista | Lectura |
|---|---|---|---|
| 19 | Irshad et al. (2024), GCF-MLD | IEEE Access | **Muy relevante.** Usa datos reales de un banco de Pakistán: 1,77 M transacciones y 9 925 cuentas. El método es **no supervisado** (clustering + centralidad de grafos) y las etiquetas solo se usan para evaluar, que es justo el caso de P5. Con clustering jerárquico: precisión 0,87, recall 0,83, AUC 0,91. Debilidades: solo 75 cuentas sospechosas y no compara contra reglas. Si es Q1 o Q2, pasa las rondas 4 y 5. |
| 55 | Ejime et al. (2026), FinCEN Files | IEEE Access | Útil para P4: RF y XGBoost llegan a AUC ~0,97, mientras Isolation Forest y One-Class SVM quedan bajo 0,75. Debilidades: la etiqueta la construyen los autores con su propio score de riesgo, el test es de solo 41 casos y son transacciones entre bancos. **Dudoso.** |
| 31 | Asomura et al. (2023) | J. Information Processing | Datos reales de un banco de Japón: RF con FPR 0,000 y FNR 0,005. Pero detecta transferencias no autorizadas (robo de cuentas), no lavado. **Probablemente Sale.** |

### Faltan PDF (de pago o bloqueados): filas 8, 21, 25, 27, 29, 37, 39, 41, 43, 52, 81

Los de más prioridad por tema:
- **Fila 21** (sistema multiagente con datos reales de banco y riesgo)
- **Fila 39** (transferencias fraudulentas con GNN y datos reales)
- **Fila 8** (Anti-TrustRank)
- **Fila 43** (atributos para reportar SAR)
- **Fila 52** (evaluación descentralizada)

Avisos para la ronda 4:
- La fila 37 parece fraude de tarjetas.
- Las filas 25 y 27 usan datos sintéticos o simulados.

## Pre-evaluación de los de acceso abierto (10-10-2026)

Estos 4 son de acceso abierto, pero los sitios bloquean la descarga automática. La evaluación se hizo con el resumen y los metadatos de Crossref, y falta confirmarla con el PDF.

En los 4, Crossref confirma que son artículos de revista en inglés, de 2025–2026 y sin retractaciones. Por lo tanto, ninguno cae en CE1, CE2 ni CE3.

| Archivo / fila | Artículo | Pre-evaluación |
|---|---|---|
| Matriz fila 7 | Kungu et al. (2026) | **Fuerte.** Aporte propio: VAE + GNN + reglas. Usa 54 258 transacciones reales de un banco de África Oriental y tiene una validación independiente en otra entidad de Kenia. Es no supervisado: One-Class SVM supera a Isolation Forest y LOF, con precisión 99,63 % en el 5 % superior de alertas, un análogo directo del IE10 del proyecto. Cumple CI1, CI3, CI4 y CI5. Responde P2, P3, P4 y P5. |
| Candidatos fila 52 | Evaluating fraud detection algorithms in a decentralized scenario (2026) | **Media.** Útil para P5 porque propone un escenario de evaluación realista. No dice qué datos usa. Ojo con el cuartil: la revista es multidisciplinaria. |
| Candidatos fila 29 | Comparative analysis… fraudulent banking transactions (2025) | **Baja-media.** Usa datos reales, pero trata de fraude y no de lavado de activos. Además, reporta "accuracy 100 %". Probablemente sale en la ronda 4. |
| Candidatos fila 81 | SF-DynFinGC (2026) | **Baja.** Usa GNN sobre grafos de cuentas, que Perumoney no tiene, y sus datasets no están identificados. Hay que revisar si son de cripto (CE4). |

**Corrección:** la fila 37 de Candidatos **no** es de acceso abierto. Pasa a la lista de pago.

## Lectura completa de los 4 de acceso abierto (10-10-2026)

| Archivo / fila | Artículo | Veredicto |
|---|---|---|
| Matriz fila 7 | Kungu et al. (2026), Kenia | **Cumple, aunque falta el cuartil.** Usa 54 258 pagos SWIFT reales. Entrena One-Class SVM solo con operaciones normales, sin etiquetas, y obtiene P@5 % de 99,26 % en el test, frente a 83,99 % de Isolation Forest. Tiene validación operativa en otra entidad. **Ojo:** la "verdad" con la que evalúan son las mismas reglas (un proxy), no reportes de operaciones sospechosas confirmados. Sus variables son reutilizables para Perumoney: tiempo desde la operación anterior, antigüedad del cliente, desvío del monto, volatilidad y bandera de fraccionamiento. Responde P2–P5. |
| Candidatos fila 52 | Gige et al. (2026), Dinamarca | **Reserva.** Usa solo datos sintéticos (IBM-AML) y grafos entre muchos bancos. Aporta a P5 que, si cada entidad ve solo sus datos, el rendimiento cae y los modelos simples rinden mejor. |
| Candidatos fila 29 | Preciado et al. (2025), España | **Sale (ronda 4).** Trata de fraude en transferencias, no de lavado. Reporta 0 falsos positivos con solo 95 fraudes en el test, lo que es poco creíble. |
| Candidatos fila 81 | SF-DynFinGC (2026), Malasia/China | **Sale recomendado (ronda 4).** Es un método genérico de grafos dinámicos para GNN y necesita un grafo entre cuentas. No es de cripto. |

## PDF de pago recibidos (10-10-2026)

| Archivo / fila | Artículo | Veredicto |
|---|---|---|
| Matriz fila 8 | Luo et al. (2024), China | **Cumple, aunque falta el cuartil.** MLaD2 es una GNN semisupervisada sobre la red entre cuentas, con pre-entrenamiento contrastivo. Usa datos reales de una agencia policial china. Con solo 10 % de etiquetas supera a XGBoost, a GAT y a los métodos no supervisados. Respalda lo que el Cap. 1 le atribuye. **Limitaciones:** un solo dataset pequeño, necesita un grafo entre cuentas que Perumoney no tiene, y algunas etiquetas. Responde P3, P4, P5. |
| Candidatos fila 21 | Alexandre y Balsa (2023), Portugal/Brasil | **Cumple y es muy relevante, aunque falta el cuartil.** Arma perfiles de comportamiento de 2,4 M clientes y los agrupa en 5 perfiles con k-means. Suma reglas J48 y reglas legales, y ordena los casos con un Índice de Sospecha. **Validación con analistas:** 89 de 189 clientes fueron confirmados como sospechosos, incluidos casos que el sistema vigente no veía. No necesita etiquetas. Responde P1, P2, P3, P5. **Ojo con CE2:** es de 2023. |

## Búsqueda propia (10-10-2026): candidatos nuevos, no presentes en Candidatos_Joaquin.xlsx

| Artículo | Revista | DOI | Estado |
|---|---|---|---|
| Ramadhan (2025), *Harnessing ML for money laundering detection: a criminological theory-centric approach* | J. Money Laundering Control 28(1) | 10.1108/JMLC-04-2024-0083 | Falta el PDF (pago, Emerald) |
| Shadrooh y Nørvåg (2024), *SMoTeF: Smurf money laundering detection using temporal order and flow analysis* | Applied Intelligence | Por confirmar | Falta el PDF. Trata del fraccionamiento ("pitufeo"), relevante para Perumoney |
| Andreescu et al. (2025), *AML Compliance Using Feature Engineering with SQL Analytics, TF-IDF and Oversampling: CTGAN* (Rumania) | Informatica (Vilnius) 36(3) | 10.15388/25-INFOR598 | **Leído. Reserva.** Cumple en lo formal, pero usa datos **sintéticos** (demo de DataRobot, alertas de tarjeta de crédito). Su ingeniería de variables (sumas acumuladas, promedios móviles, diferencias entre filas) sirve para P2 e IE5. Con RF: AUC 0,95, recall 0,99, F1 0,53 |
| *PageRank-Based Unsupervised Deep Vertex Representations for AML Detection* (2025) | IEEE Access | 10.1109/ACCESS.2025.3634197 | Falta el PDF (IEEE; la descarga automática fue bloqueada) |
| *Complex networks-based anomaly detection for financial transactions in AML* (2025) | Forensic Science International: Digital Investigation | 10.1016/j.fsidi.2025.302005 | Falta el PDF (ScienceDirect) |
