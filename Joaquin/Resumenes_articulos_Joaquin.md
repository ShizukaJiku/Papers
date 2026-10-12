# Resúmenes de los 12 artículos de Joaquín

Proyecto: *Sistema de detección de operaciones inusuales para la priorización de alertas de cumplimiento en una casa de cambio usando técnicas de Machine Learning* (PERUMONEY).

La numeración coincide con los PDF (`01_…pdf` a `12_…pdf`) y con el N.° de `Matriz_Joaquin.xlsx`. La fila de Excel es N.° + 4.

**Preguntas de investigación**
- **P1:** aportes existentes
- **P2:** componentes
- **P3:** técnicas
- **P4:** mejores técnicas
- **P5:** validación

| N.° | Artículo | Revista | Cuartil | País | Preguntas |
|---|---|---|---|---|---|
| 01 | Ajagbe et al. (2025) | Discover Artificial Intelligence | Q1 | Sudáfrica | P3, P4 |
| 02 | Bakry et al. (2024) | The Journal of Supercomputing | Q2 | Egipto | P1, P2, P3, P5 |
| 03 | Kungu et al. (2026) | Machine Learning with Applications | Q1 | Kenia | P2, P3, P4, P5 |
| 04 | Luo et al. (2024) | IEEE Trans. Information Forensics and Security | Q1 | China | P3, P4, P5 |
| 05 | Reite et al. (2025) | Journal of Money Laundering Control | Q1 | Noruega | P2, P3, P4 |
| 06 | Irshad et al. (2024) | IEEE Access | Q1 | Pakistán | P1, P2, P3, P5 |
| 07 | Alexandre y Balsa (2023) | Expert Systems with Applications | Q1 | Portugal | P1, P2, P3, P5 |
| 08 | Shih et al. (2025) | Expert Systems with Applications | Q1 | Taiwán | P2, P3, P4, P5 |
| 09 | Ejime et al. (2026) | IEEE Access | Q1 | Reino Unido | P1, P2, P4 |
| 10 | Hayble-Gomes (2023) | Journal of Money Laundering Control | Q2 | EE. UU. | P2, P3 |
| 11 | Gige et al. (2026) | Royal Society Open Science | Q1 | Dinamarca | P4, P5 |
| 12 | Lokanan (2024) | Journal of Applied Security Research | Q2 | Canadá | P2, P3, P4 |

---

## 01. Ajagbe, Majola y Mudali (2025)

**Comparative analysis of machine learning algorithms for money laundering detection.** *Discover Artificial Intelligence*, 5, 144. https://doi.org/10.1007/s44163-025-00397-4

- **Problema:** los métodos tradicionales no detectan bien el lavado de activos en transacciones financieras.
- **Aporte:** compara cinco algoritmos (XGBoost, KNN, Random Forest, Isolation Forest y SVM). También propone el diseño de un sistema con panel de alertas, que no llega a implementar.
- **Datos:** dataset de IBM AML publicado en Kaggle. Es **sintético**, aunque el artículo lo presenta como real y como "balanceado".
- **Validación y resultados:** partición 80/20.
  - XGBoost obtiene accuracy, precisión, recall y F1 de 1,00, y AUC de 0,94 (en otra parte del texto el AUC aparece como 0,62).
  - Isolation Forest logra accuracy de 0,96, pero AUC de 0,62.
- **Limitaciones:**
  - Las métricas perfectas sugieren fuga de información.
  - **No compara contra sistemas de reglas.**
  - Varias referencias del artículo no tienen relación con el tema.
- **Utilidad para la tesis:** sirve como referencia de comparación entre algoritmos (P3 y P4). **Ojo:** no respalda la afirmación del Cap. 1 de que "la detección de anomalías supera a las reglas simples"; hay que corregirla.

## 02. Bakry, Alsharkawy, Farag y Raslan (2024)

**Automatic suppression of false positive alerts in anti-money laundering systems using machine learning.** *The Journal of Supercomputing*, 80(5), 6264-6284. https://doi.org/10.1007/s11227-023-05708-z

- **Problema:** los sistemas de reglas generan muchísimos falsos positivos, lo que consume tiempo del área de cumplimiento.
- **Aporte:** ASXAML, un modelo XGBoost que recibe las alertas del sistema de reglas y suprime las de bajo riesgo. Selecciona variables con RFECV y ajusta hiperparámetros con Optuna.
- **Datos:** reales, de un banco de Egipto. Son 46 escenarios de reglas y 210 996 clientes con alertas en 6 meses, de los cuales 6 420 fueron clientes "importantes".
- **Validación y resultados:**
  - Partición 70/30 y validación cruzada de 2 a 10 particiones.
  - Métrica principal F-beta, que da más peso al recall.
  - F-beta de 0,86, recall de 0,92 y **73 % menos falsos positivos**.
  - Supera a SVM, RF, KNN, NB y árbol de decisión en recall.
- **Limitaciones:**
  - Es supervisado: necesita la decisión del analista como etiqueta.
  - Depende de que ya exista un sistema de reglas.
- **Utilidad para la tesis:** muestra cómo priorizar y suprimir alertas (P1, P2, P5). La idea de usar F-beta para no perder casos sospechosos es aplicable.

## 03. Kungu, Senagi y Omondi (2026)

**Hybrid deep learning for anti-money laundering: Unsupervised detection of emerging schemes via feature fusion and explainable artificial intelligence.** *Machine Learning with Applications*, 23, 100856. https://doi.org/10.1016/j.mlwa.2026.100856

- **Problema:** las reglas tienen muchos falsos positivos y no hay casos sospechosos confirmados para entrenar un modelo.
- **Aporte:**
  - Combina variables de reglas con representaciones aprendidas por un autoencoder variacional (VAE) y una red de grafos (GNN).
  - Detecta anomalías con One-Class SVM, entrenado solo con operaciones no marcadas.
  - Explica los resultados con SHAP.
- **Datos:** 54 258 pagos SWIFT **reales** de un banco de África Oriental, de 9 meses de 2024.
- **Variables:** días desde la operación anterior, antigüedad del cliente, log del monto, desvío del monto respecto al promedio del cliente, volatilidad, país de alto riesgo y bandera de fraccionamiento (< USD 10 000).
- **Validación y resultados:**
  - Precision@5 % de **99,26 %** en test, contra 83,99 % de Isolation Forest.
  - AP de 0,85 y ROC-AUC de 0,85.
  - Validación operativa en otra entidad de Kenia, a 1 000 transacciones por segundo.
- **Limitaciones:** la "verdad" para evaluar son las propias reglas, no reportes de operaciones sospechosas confirmados. Los autores lo reconocen.
- **Utilidad para la tesis:** **muy alta.** No necesita etiquetas, prioriza alertas y sus variables son reutilizables (IE5, IE10). Responde P2 a P5.

## 04. Luo, Han, Zuo, Wu y Liu (2024)

**MLaD2: A semi-supervised money laundering detection framework based on decoupling training.** *IEEE Transactions on Information Forensics and Security*, 19, 4518-4533. https://doi.org/10.1109/TIFS.2024.3380262

- **Problema:** los métodos supervisados necesitan muchas etiquetas, y las redes de grafos suponen que las cuentas vecinas se parecen, lo que no se cumple en el lavado.
- **Aporte:** MLaD2 arma una red de cuentas ponderada por similitud y la procesa con una GNN. Primero entrena sin etiquetas (aprendizaje contrastivo) y luego se ajusta con pocas etiquetas.
- **Datos:** **reales**, de una agencia policial china (un caso de juego ilegal): 51 326 transacciones.
- **Validación y resultados:**
  - Partición 70/10/20.
  - Con solo 10 % de etiquetas supera a XGBoost (+2,7 % de F1), a GAT y a EvolveGCN, y a los métodos no supervisados FlowScope y MonLAD (+24,8 % de F1).
  - Es robusto ante datos alterados.
- **Limitaciones:**
  - Un solo dataset, pequeño y antiguo.
  - Poca interpretabilidad.
  - Necesita un grafo de transferencias entre cuentas.
- **Utilidad para la tesis:** respalda los enfoques que dependen poco de etiquetas (P3, P4, P5), como se cita en el Cap. 1.

## 05. Reite, Karlsen y Westgaard (2025)

**Improving client risk classification with machine learning to increase anti-money laundering detection efficiency.** *Journal of Money Laundering Control*, 28(1), 93-107. https://doi.org/10.1108/JMLC-03-2024-0040

- **Problema:** el monitoreo basado en reglas genera falsos positivos, y la clasificación del riesgo del cliente suele usar solo datos internos del banco.
- **Aporte:** un modelo de riesgo del cliente que predice qué clientes tendrán alertas que terminan en reporte. Combina datos bancarios, puntaje de crédito y datos contables, y fija umbrales con el índice de Youden y la distancia mínima.
- **Datos:** **reales**, de BN Bank (Noruega): 500 767 observaciones de PYMES y 9 831 alertas, entre 2021 y 2023.
- **Validación y resultados:**
  - Validación cruzada estratificada que respeta el orden temporal.
  - AUC de **0,94** combinando las tres fuentes, contra 0,81–0,85 con solo datos bancarios.
  - Permite reducir hasta 95 % de los falsos positivos, a costa de perder un tercio de los casos reportados.
- **Limitaciones:** usa datos contables y de crédito de empresas, que una casa de cambio no tiene de personas naturales.
- **Utilidad para la tesis:** el componente de **riesgo del cliente** complementa el monitoreo de operaciones (P2, P3, P4).

## 06. Irshad, Alkhalifah, Alturise y Khan (2024)

**GCF-MLD: Integrated approach for money laundering detection using machine learning and graph network analysis.** *IEEE Access*, 12, 183961-183974. https://doi.org/10.1109/ACCESS.2024.3510115

- **Problema:** las reglas no se adaptan a nuevas tácticas de lavado.
- **Aporte:** combina centralidades del grafo de transacciones (grado, intermediación, PageRank) con variables de la cuenta y de sus transacciones, y agrupa con k-means y clustering jerárquico. Es **no supervisado**.
- **Datos:** **reales**, de un banco de Pakistán: 1,77 millones de transacciones de 9 925 cuentas alertadas por reglas, de las cuales 75 fueron sospechosas.
- **Variables:** totales de débito y crédito, monto, número de transacciones, intervalo promedio entre transacciones, tipos de transacción, contrapartes, estado, tipo y riesgo de la cuenta, y fuente de ingresos.
- **Validación y resultados:** las etiquetas se usan solo para evaluar. El clustering jerárquico logra precisión de **0,87**, recall de 0,83, F1 de 0,85, AUC de 0,91 y FPR menor a 0,001.
- **Limitaciones:**
  - Solo 75 casos positivos.
  - No compara contra reglas ni contra otros modelos.
- **Utilidad para la tesis:** ejemplo de un enfoque no supervisado evaluado con casos reales (P1, P2, P3, P5).

## 07. Alexandre y Balsa (2023)

**Incorporating machine learning and a risk-based strategy in an anti-money laundering multiagent system.** *Expert Systems with Applications*, 217, 119500. https://doi.org/10.1016/j.eswa.2023.119500

- **Problema:** la detección de clientes sospechosos es subjetiva y los sistemas vigentes se basan en el registro del cliente.
- **Aporte:** un sistema multiagente.
  - Construye perfiles de comportamiento transaccional y los agrupa con k-means en 5 perfiles: bajo uso, estándar, riesgo bajo, medio y alto.
  - Genera reglas con J48 y suma reglas legales y de analistas.
  - **Prioriza** con un Índice de Sospecha.
- **Datos:** **reales**, de un banco de Brasil. Usa 30,5 millones de transacciones (2,4 millones de perfiles) para construir el modelo y 17,1 millones de transacciones de 3,2 millones de clientes para probarlo.
- **Validación y resultados:** los analistas del banco revisaron 189 clientes señalados y **confirmaron 89 como sospechosos (47 %)**, incluidos casos que el sistema vigente nunca detectó.
- **Limitaciones:** es de 2023, en el límite del criterio de antigüedad. Hay poco detalle de métricas cuantitativas clásicas.
- **Utilidad para la tesis:** **muy alta.** No necesita etiquetas, prioriza con un índice y valida con expertos, lo que es análogo al IE10 (P1, P2, P3, P5).

## 08. Shih, Dai, Chen, Ti, Wang y Kuo (2025)

**Fund transfer fraud detection: Analyzing irregular transactions and customer relationships with self-attention and graph neural networks.** *Expert Systems with Applications*, 259, 125211. https://doi.org/10.1016/j.eswa.2024.125211

- **Problema:** predecir qué alertas del monitoreo terminan en reporte de operación sospechosa, con transacciones irregulares en el tiempo y relaciones entre clientes. Aunque el título dice "fraud", **es lavado de activos**.
- **Aporte:**
  - Convierte las transacciones de los 15 días hábiles previos en series regulares.
  - Combina un autoencoder variacional con self-attention, una GNN de relaciones entre clientes y generadores de casos (CVAE y WGAN) para compensar el desbalance.
  - Entrena todo de extremo a extremo.
- **Datos:** **reales**, de un banco de Taiwán (alertas según la tipología del regulador y la decisión del área legal) y de un segundo banco.
- **Validación y resultados:** AUPRC de **27 %**, contra 0,66–22,15 % de XGBoost y otras redes, con estudio de ablación.
- **Limitaciones:**
  - Supervisado.
  - Necesita relaciones entre clientes.
  - Valores absolutos de AUPRC bajos.
- **Utilidad para la tesis:** muestra cómo transformar la historia de cada cliente en **variables por ventana de tiempo** (P2, P3, P4, P5).

## 09. Ejime, Kosemani y Onyeorueka (2026)

**Machine learning and network analysis for cross-border suspicious transaction detection: Evidence from the FinCEN Files.** *IEEE Access*, 14, 62234-62247. https://doi.org/10.1109/ACCESS.2026.3685103

- **Problema:** los sistemas de reglas generan más alertas de las que se pueden investigar.
- **Aporte:** un marco integrado:
  - estadística descriptiva;
  - series de tiempo (ARIMA);
  - análisis geográfico y de red;
  - puntaje de riesgo;
  - comparación de modelos supervisados (regresión logística, RF, XGBoost) contra no supervisados (Isolation Forest, One-Class SVM).
- **Datos:** **reales** (FinCEN Files, reportes filtrados entre 1999 y 2017): 4 507 grupos con más de 200 000 transacciones.
- **Validación y resultados:**
  - Validación cruzada estratificada de 5 particiones y análisis de sensibilidad.
  - Los supervisados logran AUC de ~0,97–0,98 y los no supervisados quedan bajo 0,75.
  - Las variables más importantes son la centralidad de red y los corredores de alto riesgo.
- **Limitaciones:**
  - La etiqueta la construyen los autores con su propio puntaje de riesgo.
  - El test tiene solo 41 casos.
  - Son transacciones entre bancos.
- **Utilidad para la tesis:** comparación entre modelos supervisados y no supervisados (P4) y uso de un puntaje de riesgo (P2).

## 10. Hayble-Gomes (2023)

**The use of predictive modeling to identify relevant features for suspicious activity reporting.** *Journal of Money Laundering Control*, 26(4), 806-820. https://doi.org/10.1108/JMLC-02-2022-0034

- **Problema:** identificar qué atributos determinan que una alerta termine en reporte de operación sospechosa.
- **Aporte:** regresión logística y árbol de decisión. El árbol produce **reglas interpretables**, comparables a las reglas de negocio.
- **Datos:** **sintéticos**, a partir de transacciones públicas modificadas para imitar banca minorista de EE. UU. Incluyen un solo escenario y el riesgo de país de KnowYourCountry, con un umbral de USD 20 000.
- **Variables:** puntaje de alerta, regla, región, riesgo del país, antigüedad del cliente y de la cuenta, edad, monto, número de transacciones y reporte previo.
- **Validación y resultados:**
  - Partición 60/40 con balanceo ROSE.
  - La regresión logística logra accuracy de 98 %, AUC de 0,97 y recall de 0,91.
  - Las variables clave son reporte previo, edad, antigüedad, monto y puntaje de alerta.
- **Limitaciones:** datos sintéticos, un solo escenario y año 2023.
- **Utilidad para la tesis:** lista de variables candidatas para el perfil de riesgo y reglas interpretables (P2, P3).

## 11. Gige, Buschmann Alsbirk y Coscia (2026)

**Evaluating fraud detection algorithms in a decentralized scenario.** *Royal Society Open Science*, 13, 251922. https://doi.org/10.1098/rsos.251922

- **Problema:** los modelos de punta se evalúan como si una autoridad viera todas las transacciones de todos los bancos, lo que no es realista.
- **Aporte:** propone una evaluación en dos pasos: primero cada banco marca sus propias operaciones y después la autoridad analiza solo lo marcado.
- **Datos:** **sintéticos** (IBM-AML), con modelos de grafos (FraudGT y GatedGCN).
- **Validación y resultados:**
  - El F1 cae de 0,32/0,71 a 0,12/0,56 en el escenario realista.
  - Usando un modelo más simple en uno de los pasos sube a 0,49/0,85.
- **Limitaciones:** solo datos sintéticos, contexto de múltiples bancos y revista multidisciplinaria.
- **Utilidad para la tesis:** argumento para que la validación refleje lo que la entidad realmente ve, y evidencia de que **los modelos más simples pueden rendir mejor** (P4, P5).

## 12. Lokanan (2024)

**Predicting money laundering using machine learning and artificial neural networks algorithms in banks.** *Journal of Applied Security Research*, 19(1), 20-44. https://doi.org/10.1080/19361610.2022.2114744

- **Problema:** predecir qué transacciones bancarias son lavado de activos y qué variables lo explican.
- **Aporte:** compara Naive Bayes, Random Forest, regresión logística, CatBoost y una red neuronal.
- **Datos:** **simulados** a partir de transacciones de bancos de Medio Oriente: 2 340 observaciones.
- **Variables:** tipo de operación (ingreso de efectivo o transferencia de salida), nivel del implicado, monto, fecha, hora y etapa del lavado (colocación, estratificación, integración).
- **Validación y resultados:**
  - Partición 60/40.
  - Naive Bayes y Random Forest logran ~77 % de accuracy y la red neuronal 80 %.
  - Random Forest tiene precisión de 0,87 y recall de 0,72.
  - El lavado se concentra en las horas de la mañana.
- **Limitaciones:** datos simulados, muestra pequeña y evaluación basada sobre todo en accuracy.
- **Utilidad para la tesis:** variables temporales (hora, día) y de tipo de operación, aplicables a una casa de cambio (P2, P3, P4).

---

## Síntesis para la tesis

- **Enfoques sin etiquetas** (el caso de Perumoney): 03 Kungu, 06 Irshad, 07 Alexandre y Balsa, y 04 Luo (semisupervisado).
- **Priorización de alertas:** 02 Bakry, 03 Kungu y 07 Alexandre y Balsa.
- **Validación con expertos o en operación real:** 07 Alexandre y Balsa (analistas) y 03 Kungu (otra entidad).
- **Variables de comportamiento:**
  - 03 Kungu: recencia, desvío del monto y fraccionamiento.
  - 06 Irshad: intervalos entre transacciones y contrapartes.
  - 08 Shih: ventanas de 15 días.
  - 12 Lokanan: hora y día.
  - 10 Hayble-Gomes: antigüedad y reporte previo.
- **Comparaciones de técnicas (P4):** 01 Ajagbe, 09 Ejime y 11 Gige.
- **Brecha:** ninguno trata casas de cambio ni remesas. Todos los estudios son de bancos, y eso debe señalarse en la Discusión.
