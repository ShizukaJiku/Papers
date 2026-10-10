# Revisión del documento "Trabajo_de_Investigacion_SIA" (versión recibida el 10-10-2026)

Alcance: capítulos 1 y 2 (lo avanzado), estructura de la plantilla, tablas y figuras, citas y referencias (APA 7). También se cruza el documento con la Matriz y la lista de Candidatos.

Prioridad: **A** = bloquea o contradice el contenido · **B** = consistencia interna · **C** = formato o estilo.

---

## A. Problemas de contenido que contradicen otras partes

| # | Dónde | Problema | Corrección sugerida |
|---|---|---|---|
| A1 | Tabla 10, CI6 y su nota | **El nuevo criterio CI6 (solo acceso abierto) contradice la selección actual.** Luo et al. (2024), citado en Antecedentes y en Formulación, es de pago. También lo son Alexandre y Balsa (2023) y 9 candidatos que se están bajando por la biblioteca UPC. Reite (2025) solo tiene libre la versión aceptada del autor. Además, la nota justifica CI6 por el costo, pero la UPC da acceso sin costo para el alumno. | **Eliminar CI6**, o reformularlo como "texto completo accesible (acceso abierto o vía biblioteca institucional)". Si se mantiene tal cual, Luo y Alexandre y Balsa salen de la Matriz y hay que reescribir Antecedentes. |
| A2 | 1.1 Antecedentes (párr. 5) y 1.2.4 Formulación | **Lo que se atribuye a Ajagbe et al. (2025) no está en el artículo.** No compara contra reglas: gana XGBoost, que es supervisado, e Isolation Forest tiene AUC 0,62. Además usa un dataset sintético (IBM). | Quitar la frase "superan a los esquemas de reglas simples". Para sostener esa idea usar Kungu et al. (2026), Bakry et al. (2024) o Alexandre y Balsa (2023), que sí lo muestran con datos reales. |
| A3 | Figura 2 (Ishikawa) frente a Tabla 3 y texto | **El diagrama y la tabla no coinciden.** (a) El texto dice "seis categorías" y la figura tiene seis (incluye ENTORNO), pero la Tabla 3 usa cinco (Método aparece dos veces) y ninguna causa es de Entorno. (b) La C5 "revisión quincenal" está en Proceso en la tabla y en Método en la figura. (c) La figura tiene causas que no están en la tabla ("Sin realimentación", "Sin trazabilidad", "Análisis en Excel", "Histórico sin explotar", los tres de Entorno). (d) "Cobertura parcial" aparece como causa en la figura, pero el texto la trata como síntoma. | Alinear figura y tabla: mismas categorías, mismas causas y mismos códigos C1–C6. Lo mejor es rotular cada espina de la figura con su código. |
| A4 | 2.3 Conducción de la revisión | **La sección quedó vacía.** Se eliminó la Tabla 11 y el aviso de la Figura 3, y no quedó nada en su lugar. Los artículos que se citan en el Cap. 1 (Bakry, Luo, Ajagbe, Oztas) no aparecen en el Cap. 2. | Agregar: la Figura 3 (diagrama de flujo de selección tipo PRISMA, con los números de la hoja Conteo), la tabla de artículos seleccionados y sus estadísticas (base de datos, revista, año, país, cuartil). |
| A5 | 2.2.4 Cadenas frente a la Matriz y Candidatos | **El documento cambió la búsqueda, pero la lista de candidatos se armó con la anterior.** Ahora hay dos rondas (casas de cambio primero) y ScienceDirect dejó de ser base de datos. La lista de Candidatos viene de las cadenas antiguas y su columna "Base de origen" incluye ScienceDirect. | Re-ejecutar la ronda 1 (casas de cambio y remesas) en Scopus, WoS e IEEE y registrar los números por ronda. O bien dejar dicho en el documento que la lista inicial se obtuvo con la versión anterior. Hay que reclasificar el origen de lo que vino de ScienceDirect como Scopus. |

## B. Consistencia interna

| # | Dónde | Problema | Corrección sugerida |
|---|---|---|---|
| B1 | Vester frente a Diagnóstico | Ahora C2 (umbral fijo) también es causa activa, pero el párrafo de Diagnóstico sigue redactado sobre C1 y C4. | Nombrar las tres causas activas en el Diagnóstico. |
| B2 | C4 frente a objetivos e indicadores | C4 (cliente no consolidado entre agencias) es causa activa y "la solución actúa sobre" ella, pero ningún OE ni indicador mide esa consolidación. | Mencionar la consolidación de la identidad del cliente en OE2 y OE3, y agregar un indicador (por ejemplo, % de operaciones asociadas a un cliente consolidado). |
| B3 | OE3 | El "indicador de inusualidad consultable desde la ventanilla" no tiene indicador en la Tabla 5 ni sustento en el problema, porque C3 (el cajero) es causa pasiva. | Justificarlo en el problema y agregarle un indicador, o sacarlo del alcance. |
| B4 | Tabla 8 frente a Tabla 9 | Las cadenas usan términos que no están en la tabla de palabras clave: "money exchange", "exchange house", "bureau de change", "money service business", "data mining", "artificial intelligence", "unsupervised" y la exclusión de cripto. Y al revés: la tabla tiene "AML", "transaction monitoring" y "risk scoring", que no se usan en ninguna cadena. | Hacer que las dos tablas coincidan. |
| B5 | Tabla 6 (P5) frente a Formulación | P5 pasó de "validar sin casos etiquetados" a "validar en escenario real", y se borró el párrafo que explicaba la falta de etiquetas. La Formulación sigue apoyándose en esa falta de etiquetas. | Recuperar en P5 o en su párrafo la condición de no tener casos etiquetados, que es el diferencial del escenario. |
| B6 | 2.2.5 Periodo frente a CE2 | "2023–2026" junto con "no mayor a tres años" es ambiguo en octubre de 2026. Afecta a Bakry (2023/24) y a Alexandre y Balsa (2023). | Fijar la regla de forma explícita, por ejemplo: "publicados desde el 1 de enero de 2023". |
| B7 | 1.2.3 Análisis del problema | Dice que el análisis "se realiza sobre el registro transaccional", pero no se muestra ningún dato del registro (distribuciones, % bajo el umbral, fraccionamiento). Y el IE1 indica que esa caracterización todavía está pendiente. | Agregar 2 o 3 cifras del histórico, o cambiar la redacción a "sobre la caracterización del proceso". |
| B8 | Portada | Fecha "Lima, 15 de septiembre de 2026". | Actualizar a la fecha de entrega. |
| B9 | Figura 1, nota "Tomado de la documentación institucional" | Es una fuente que no figura en las Referencias. | Agregarla como referencia, o poner "Adaptado de PERUMONEY (2026)" con su entrada en la lista. |

## C. Formato y estilo

| # | Dónde | Problema | Corrección |
|---|---|---|---|
| C1 | Tabla de contenido | Está desactualizada: no figuran 2.4.5 ni 2.5.5 (Pregunta 5) y la numeración de páginas no corresponde. | Actualizar el campo (clic derecho → Actualizar campos → Toda la tabla). |
| C2 | Lista de Tablas y Lista de Figuras | Siguen con el texto de la plantilla. | Insertar las tablas de ilustraciones automáticas. Para eso, los rótulos "Tabla N" y "Figura N" deben insertarse como títulos de Word (hoy son texto escrito a mano en estilo Normal). |
| C3 | Títulos de los capítulos 5, 6 y 7 | "5.  VALIDACIÓN" y "6.  DISCUSIÓN " tienen doble espacio, "6.  DISCUSIÓN " tiene un espacio al final y "7.CONCLUSIONES" no tiene espacio. | Dejar el mismo formato que "1. DEFINICIÓN DEL PROYECTO". |
| C4 | Índice, Anexo 05 | "Tunitin" en el índice y "Turnitin" en el título. | Se corrige al actualizar el índice. |
| C5 | 2.2.3 | "Palabras claves". | "Palabras clave". |
| C6 | Figura 2 | Mide 16,5 cm de ancho y el área de texto es de 15,5 cm (A4, márgenes de 3 y 2,5 cm): se sale del margen derecho. | Reducirla a 15,5 cm o menos. |
| C7 | Figura 1 (organigrama) | El texto de las cajas es ilegible al tamaño de página. | Usar una versión recortada (Gerencia, Cumplimiento, Operaciones, Sistemas) o ponerla en orientación horizontal. |
| C8 | Subtítulos sueltos ("Datos de identificación", "Misión, visión y objetivos", "Organigrama", "Síntomas identificados", "Diagnóstico", etc.) | Son párrafos Normal en negrita, no títulos de nivel 5, así que no aparecen en el índice. "Datos de identificación" además repite el título de la Tabla 1. | Usar un estilo de título (APA nivel 5) o quitarlos. Eliminar "Datos de identificación". |
| C9 | Referencias: cursivas | En los artículos de Ajagbe, Bakry, Luo y Oztas la revista y el volumen no van en cursiva (en Doran sí). En Redacción Gestión está en cursiva el título de la nota, cuando debería estarlo el nombre del diario (*Gestión*). Las páginas de SBS y UNODC no tienen el título en cursiva. | Aplicar APA 7: *Revista, volumen*(número); en prensa, el periódico en cursiva; en páginas web, el título en cursiva. |
| C10 | Referencias: conector | Se mezcla "&" (Ajagbe, Bakry, Kitchenham, Luo, Oztas) con "y" (Flores Dueñas, "Keele University y Durham University"). | Usar uno solo. En APA 7 en español se usa "y". |
| C11 | Referencias: UNODC (s.f.) | Falta la fecha de consulta en una página que cambia. | Agregar "Recuperado el … de …". |
| C12 | Notas de tablas y figuras | Se quitó "Elaboración propia", lo cual es correcto en APA 7, pero ahora unas tablas tienen nota y otras no. La Figura 2 no tiene nota y la Figura 1 sí. | Es aceptable. Solo verificar que toda tabla o figura con datos de terceros indique su fuente. |
| C13 | Secciones de plantilla | Siguen con instrucciones de la plantilla: Dedicatoria, Agradecimientos, **Resumen y Abstract (obligatorios)**, Palabras clave/Keywords, 2.4 y 2.5 (texto guía), Cap. 3 a 7, "(Poner el título adecuado del aporte)" y Anexos. | Normal para el avance actual, pero el Resumen y el Abstract son obligatorios en la entrega. |

## Lo que está bien (verificado)

- Matriz de Vester: las sumas de filas y columnas y los promedios (4,67) son correctos, y la clasificación concuerda con la regla descrita.
- Todas las citas del texto tienen su referencia y todas las referencias se citan. El orden alfabético es correcto.
- Las referencias tienen sangría francesa.
- Los números siguen el formato español de forma consistente (1 536; 80 000; 4,67; 2 %).
- Los objetivos e indicadores están bien vinculados (IE1–IE10 con OE1–OE4). La referencia al "apartado 1.3.3" es correcta.
- Los rótulos de tablas y figuras siguen APA 7: número en negrita y título en cursiva en línea aparte; notas en 10 pt con "Nota." en cursiva.
