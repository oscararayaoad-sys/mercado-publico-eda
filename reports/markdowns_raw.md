# Carga #

---

---

---

# Dividiendo la pregunta "¿Cómo y dónde gasta el estado chileno a través de Mercado Público, y dónde están las mejores oportunidades para un proveedor?" en partes: #
- **¿Cómo gasta el estado?**
    - **1.1.- ¿El estado gasta de forma concentrada o distribuida?**
    - **1.2.- ¿El estado gasta de forma fragmentada o consolidada?**
    - **1.3.- ¿Existe un monopolio o está abierto a la competencia?**
- **¿Dónde gasta el estado?**
    
    - **2.1.- ¿Cúanto gasta el estado por categoría?**
    - **2.2.- ¿Cúanto gasta el estado por región?**
    - **2.3.- ¿Cúanto gasta el estado por rubro?**
- **¿Qué oportunidades tienen los proveedores?**
    
    - **3.1.- ¿Qué organismos tienen pocos proveedores y que se supone es más facil entrar?**
    - **3.2.- ¿Qué categorías tienen mucho gasto y tambien tienen pocos proveedores?**
    - **3.3.- ¿Que nichos especificos no están saturados?**

---

---

---

*Creamos función para legibilizar notación cientifica*

---

---

---

**¿El estado gasta de forma concentrada o distribuida?**

---

**Hallazgos clave:**

- Regla del 80/20 (Principio de Pareto):
  Solo 10 organismos concentran el 84.1% del gasto total, mientras que el resto de las instituciones se reparte un porcentaje marginal.

- Dominio en la cúpula:
  Casi dos terceras partes del gasto (64.6%) son ejecutadas por apenas 5 organismos.

- Impacto individual:
  Un solo organismo (Corporación Nacional Forestal) abarca casi una quinta parte del total (19.5%).

---

**¿El estado gasta de forma fragmentada o consolidada?**


---

**Hallazgos clave:**
- Fragmentación masiva a nivel transaccional:
    - Alto volumen de compras pequeñas: Se registran 400,300 transacciones.
    - Mediana muy baja ($919.16K): El 50% de las líneas de compra no supera el millón de pesos.
    - Rango intercuartil acotado: El 75% de las transacciones son por montos inferiores a $3.07M. La gestión cotidiana del Estado se compone de micro y pequeñas compras.

- Sesgo y asimetría extrema en los montos:
    - Distorsión del promedio: La media ($\approx \$172.58\text{B}$) es 187,000 veces mayor que la mediana ($\approx \$919.16\text{K}$). Esto ocurre cuando un puñado de compras de escala masiva distorsiona el comportamiento del total.
    - Volatilidad gigante: Una desviación estándar de $28.10T y un coeficiente de variación de 162.8 confirman la presencia de mega-operaciones atípicas (con un máximo de $10.72P).

    Conclusión: A nivel de gestión diaria y volumen de órdenes, el Estado opera de forma muy fragmentada (miles de transacciones pequeñas). Sin embargo, a nivel de presupuesto total, el gasto está altamente concentrado en un número mínimo de transacciones monumentales.


---

**¿Existe un monopolio o está abierto a la competencia?**


---

**Hallazgos clave:**

- Alta atomización de participantes:
    - Contar con 35,769 proveedores únicos en 400,302 órdenes de compra (OCs) descarta categóricamente una estructura monopolística. Hay un abanico amplio de competidores adjudicándose contratos.
- Frecuencia de adjudicación equilibrada:
    - El promedio de 11.19 OCs por proveedor indica que las órdenes no están hiperconcentradas en un solo jugador desde la perspectiva del volumen de transacciones.


    Advertencia metodológica:

Estas métricas evalúan la competencia en conteo de transacciones (OCs), no en monto monetario ($).

Un mercado puede tener miles de proveedores recibiendo órdenes pequeñas (aparentando alta competencia), mientras que un puñado de actores grandes (oligopolio) se adjudica el 80%+ del dinero. Para determinar si existe concentración de mercado real (p. ej., índice Herfindahl-Hirschman - HHI), se debe replicar este análisis ponderado por el monto total adjudicado por proveedor.

---

---

---

**¿Cúanto gasta el estado por región?**


---

**Hallazgos clave:**
- Macro-centralismo absoluto (Top 1 = 96.7%):
    - La Región Metropolitana de Santiago absorbe por sí sola el 96.7% del gasto total (~66.82 Peta-pesos CLP). Casi la totalidad del presupuesto ejecutado queda registrado en la capital.
- Marginalidad regional acumulada (Resto de Chile = 3.3%):
    - Las otras 15 regiones juntas representan apenas el 3.3% del dinero gastado.
    - Incluso las regiones que siguen en el ranking (Biobío con ~987.89T y Valparaíso con ~556.26T) quedan opacadas en el gráfico por la diferencia de escala de Santiago.
- Concentración técnica en el Top 5 (99.5%):
    - Las primeras 5 regiones en el listado abarcan el 99.5% del presupuesto regionalizado.


Interpretación en Ciencia de Datos:

Más que reflejar un "no gasto" en regiones, este patrón suele indicar un sesgo de facturación centralizada (ej. casas matrices de proveedores o ministerios con domicilio fiscal en Santiago registrando las compras que benefician a todo el país).

---

**¿Cúanto gasta el estado por rubro?**


---

**Hallazgos clave:**
- Liderazgo absoluto de TI (Top 1 = 42.8%):
    - El rubro Tecnologías de la información, telecomunicaciones y radiodifusión absorbe por sí solo más de 4 de cada 10 pesos del Estado (42.8% / ~29.45 Peta-pesos CLP).
- Hiperconcentración en el Top 5 (93.7%):
    - Más del 93% del presupuesto en rubros se liquida en apenas 5 sectores principales: Tecnología, Transporte, Ingeniería/Ciencias Sociales, Servicios Básicos y Financieros/Seguros.
- Monopolización del Top 10 (98.7%):
    - Los primeros 10 rubros concentran el 98.7% del gasto total.
    - Efecto cola larga: Los otros 34 rubros restantes (que abarcan desde Salud, Educación y Alimentos hasta Medicamentos) deben repartirse apenas un marginal 1.3% del presupuesto registrado en estas órdenes.

---

**¿Cúanto gasta el estado por categoría?**


---

**Hallazgos clave:**
- Dominio masivo del Top 10 (92.1%):
    - Casi la totalidad del presupuesto asignado a categorías se agrupa en solo 10 rubros. Todo el resto de las categorías representa un marginal 7.9%.
- Núcleo del gasto público (Top 5 = 74.7%):
    - Tres de cada cuatro pesos se destinan a las 5 categorías principales.
    - Categoría líder: Servicios de transporte, almacenaje y correo (Transporte aéreo de pasajeros) abarca por sí sola el 19.2% del gasto total (~13.17 Peta-pesos CLP).
- Prevalencia del sector TI y Servicios:
    - Múltiples subcategorías de Tecnologías de la Información (software de gestión, administración de sistemas, equipos impresoras) dominan el Top 5, convirtiendo a la transformación digital y el soporte informático en uno de los mayores motores del gasto estatal.

    Conclusión: El gasto no es homogéneo entre sectores. Existe una fuerte dependencia presupuestaria en infraestructura de transporte, tecnología (TI) e ingeniería/consultoría.

---

---

---

**¿Qué organismos tienen pocos proveedores y que se supone es más facil entrar?**


---

**Hallazgos clave:**

Conclusión: Este filtro por sí solo resulta bastante ambiguo para tomar decisiones. Para que un hallazgo de "barrera de entrada" sea sólido, necesitarías cruzar: Cantidad de OCs / N° de proveedores / Monto promedio de compra.

---

**¿Qué categorías y rubros tienen mucho gasto y tambien tienen pocos proveedores?**


---

| categoria                                                                                                                                                                                                   |   proveedores | gasto   |
|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------:|:--------|
| Servicios financieros, pensiones y seguros / Banca e inversiones / Instituciones bancarias                                                                                                                  |             6 | 3,79P   |
| Maquinaria para minería y perforación / Equipo para perforación y exploración para petróleo / Equipo de perforación direccional                                                                             |             2 | 3,45T   |
| Instrumentos musicales, juegos, juguetes, artesanías y materiales educativos / Materiales, artículos y suministros didácticos profesionales y para el desarrollo personal / Recursos de lenguas extranjeras |             6 | 2,92T   |
| Equipamiento para laboratorios / Equipos e insumos para laboratorio / Bibliotecas técnicas y material relacionado                                                                                           |             7 | 1,60T   |
| Maquinaria para minería y perforación / Artículos para perforación de petróleo y gas / Lodo de perforación                                                                                                  |             2 | 1,00T   |
| Equipamiento para laboratorios / Instrumentos de medida y experimentación / Instrumentos geofísicos, geotécnicos e hidrológicos                                                                             |             6 | 320,09B |
| Servicios financieros, pensiones y seguros / Banca e inversiones / Asesorías de inversiones                                                                                                                 |             4 | 218,43B |
| Maquinaria para agricultura, pesca y silvicultura / Maquinaria para agricultura, silvicultura y paisaje / Equipamiento para aves de corral y ganado                                                         |             4 | 122,00B |
| Vehículos y equipamiento en general / Componentes para sistemas aeroespaciales / Sistemas de comunicaciones en vuelo                                                                                        |             5 | 93,11B  |
| Maquinaria para minería y perforación / Maquinaria para minería / Barrenas para rocas                                                                                                                       |             3 | 77,40B  |
| Servicios de perforación de minería, petróleo y gas / Servicios gestión y proceso de datos e información sobre petróleo y gas / Servicios de interpretación y traducción del campo petrolífero              |             6 | 49,27B  |
| Maquinaria para minería y perforación / Maquinaria para minería / Equipo de corte                                                                                                                           |             4 | 37,64B  |
| Servicios profesionales, administrativos y consultorías de gestión empresarial / Servicios legales / Derecho penal                                                                                          |             5 | 25,84B  |
| Servicios basados en ingeniería, ciencias sociales y tecnología de la información / Servicios informáticos / Programadores informáticos                                                                     |             4 | 25,16B  |
| Artículos para plantas y animales / Alimento para animales / Alimento para roedores                                                                                                                         |             3 | 21,50B  |
| Servicios básicos y de información pública / Telecomunicaciones / Capacidades del eje troncal de telecomunicaciones                                                                                         |             4 | 11,04B  |
| Equipamiento y suministros médicos / Productos para imágenes y de medicina nuclear / Artículos del acelerador lineal de terapia de radiación de intensidad modulada (IMRT) l                                |             4 | 8,21B   |
| Servicios financieros, pensiones y seguros / Banca e inversiones / Servicios de transferencia de fondos, compensación y cambio                                                                              |             3 | 7,20B   |
| Servicios de defensa nacional, orden público y seguridad / Orden público y seguridad / Sistema judicial                                                                                                     |             5 | 5,84B   |
| Servicios agrícolas, pesqueros, forestales y relacionados con la fauna / Cultivos forestales / Servicios de conservación forestal                                                                           |             7 | 4,57B   |
| Servicios financieros, pensiones y seguros / Contabilidad y auditorías / Asesoría tributarias                                                                                                               |             7 | 3,68B   |
| Servicios de perforación de minería, petróleo y gas / Servicios gestión y proceso de datos e información sobre petróleo y gas / Servicios de comunicación de datos del campo petrolífero                    |             1 | 2,98B   |

---

| rubro                                               |   proveedores | gasto   |
|:----------------------------------------------------|--------------:|:--------|
| Obras MINVU                                         |            33 | 525,27T |
| Servicios medioambientales                          |           167 | 3,00T   |
| Servicios de perforación de minería, petróleo y gas |           225 | 55,40B  |
| Obras                                               |            27 | 19,61B  |

---

**Hallazgos en Categorías (Matriz $P_{80}$ de Gasto vs $P_{25}$ de Proveedores):**

Las categorías donde la concentración del gasto en pocos actores es crítica son:
- Servicios Financieros y Banca (Extremo):
    - Banca e inversiones: Gasto colosal ($3.79P) repartido en solo 6 proveedores.
- Minería y Maquinaria Pesada:
    - Equipos para minería: $3.45T con apenas 2 proveedores.
    - Artículos de minería: $1.00T concentrado también en 2 proveedores.
- Música, Arte y Entretenimiento:
    - Instrumentos musicales/juegos: $2.92T con solo 6 proveedores.
- Equipamiento Científico y Laboratorio:
    - Insumos de laboratorio: $1.60T gestionados por solo 7 proveedores.

**Hallazgos en Rubros (Matriz $P_{10}$ de Gasto vs $P_{10}$ de Proveedores):**
A nivel macro (rubro), el filtro ($Gasto \ge P_{10}$ y $Proveedores \le P_{10}$) aísla áreas donde el volumen es alto pero el parque de proveedores es llamativamente reducido:
- Obras MINVU (Criticidad Alta):
    - Acumula $525.27T ejecutados por tan solo 33 proveedores. Es el rubro de infraestructura urbana con mayor concentración por empresa.
- Servicios Medioambientales:
    - Representa $3.00T distribuidos en 167 proveedores (pocos para la escala del rubro).
- Perforación y Minería/Petróleo:
    - Genera $55.40B repartidos en 225 proveedores.

**Resumén de Análisis:**

| Nivel | Sector Crítico | Gasto | Proveedores | Diagnóstico |
| --------- | ------------- | ------- | -------- | -----------|
| Categoría | Banca e Instituciones Financieras | $3.79P | 6 | Monopolización / Oligopolio financiero |
| Categoría | Equipos de Minería y Perforación | $3.45T | 2 | Captura de mercado por nicho técnico |
| Rubro | Obras MINVU | $525.27T | 33 | Alta barrera de entrada en licitaciones públicas |

---

**¿Que nichos especificos no están saturados?**

---

**Hallazgos clave:**

1.-**Los Nichos Reales "No Saturados" (Oportunidad Alta)**

Son sectores donde hay **alto presupuesto disponible**, una cantidad de proveedores moderada (no masificada) y un **alto volumen de Transacciones (OCs)**, lo que indica movilidad y oportunidades reales para nuevos oferentes:

- **Servicios de Transporte, Almacenaje y Correo:**
    - **Gasto/Proveedor:** $140,09T
    - **Rotación:** 2.101 OCs distribuidas en 94 proveedores (~22,3 OCs por proveedor).
    - **Diagnóstico:** Mercado **Abierto / Dinámico**. Es el nicho con mejor balance entre liquidez y flujo continuo de licitaciones.
- **Tecnologías de la Información y Telecomunicaciones (Subsector C - 1782):**
    - **Gasto/Proveedor:** $26,33T
    - **Rotación:** 2.565 OCs entre 364 proveedores (~7,0 OCs por proveedor).
    - **Diagnóstico:** Mercado **Abierto / Dinámico**. Alta demanda recurrente con espacio para la entrada de nuevos competidores.
- **Tecnologías de la Información y Telecomunicaciones (Subsector B - 1802):**
    - **Gasto/Proveedor:** $28,69T
    - **Rotación:** 2.024 OCs entre 429 proveedores (~4,7 OCs por proveedor).
    - **Diagnóstico:** Mercado **Competido pero Accesible**. Mantiene un retorno por empresa muy elevado con alta tasa de adjudicación.

2.-**Los Falsos Nichos "No Saturados" (Mercados Cerrados)**

Aparecen en los primeros lugares por tener un ratio $Gasto/Proveedor$ astronómico, pero **no representan mercados no saturados**, sino **oligopolios o nichos hiperconcentrados** con barreras de entrada extremas:

- **Servicios Financieros, Pensiones y Seguros:** $630,98T/proveedor con solo 6 empresas y 11 OCs (capturado por la banca).
- **Maquinaria para Minería y Perforación:** $37,12T/proveedor con 8 empresas y 10 OCs (nicho de alta especialización técnica).
- **Vehículos y Equipamiento / Servicios Profesionales:** Con 9 y 11 proveedores respectivamente y apenas ~1 OC por proveedor (contratos grandes aislados).

## Resumen Ejecutivo

| Categoría Especifica | Tipo de Mercado | Proveedores | Volumen OCs | Gasto / Proveedor | Diagnóstico |
| --- | --- | --- | --- | --- | --- |
| **Transporte, Almacenaje y Correo** | **Abierto / Dinámico** | 94 | 2.101 | **$140,09T** | 🟢 **Nicho #1:** Alta frecuencia y altísimo retorno. |
| **TI y Telecomunicaciones (1782)** | **Abierto / Dinámico** | 364 | 2.565 | **$26,33T** | 🟢 **Nicho #2:** Mayor flujo transaccional del Estado. |
| **TI y Telecomunicaciones (1802)** | **Competido / Moderado** | 429 | 2.024 | **$28,69T** | 🟢 **Nicho #3:** Alta liquidez acumulada. |
| **Servicios Financieros / Banca** | **Cerrado / Concentrado** | 6 | 11 | **$630,98T** | 🔴 **Falso Nicho:** Barrera de entrada institucional. |
| **Maquinaria Minería** | **Cerrado / Concentrado** | 8 | 10 | **$37,12T** | 🔴 **Falso Nicho:** Exclusividad técnica/proveedor único. |

---

---

---

# Export # 

---

---