# gemelo-digital-controlador-climático-inteligente-invernadero-ecosmart 2026 (Primera pesentación básica en 2010 Camagüey, Cuba) 
**Actualizado para ubicación hipotética en Paradela, Lugo, Galicia, España**

Greenhouse EcoSmart — Gemelo digital de invernadero con IA híbrida (Ridge + Fuzzy + LLM local) aplicado a un caso hipotético en Paradela, Lugo, Galicia, España

Gemelo digital del invernadero EcoSmart (Paradela, Lugo, 500 m²) que integra: regresión Ridge para la simulación matemática precisa de los valores de los distintos sensores en el interior del invernadero porque aún no está instalado con sensores reales (esto será una próxima etapa del proyecto),  hemos incorporado a la salida del modelo LLM pequeño free (lo hemos prerentrenado con datos recopilados en los últimos 10 años con valores reales climáticos históricos de la zona), además le hemos conectado a la salida del modelo de LLM un controlador difuso determinista con recalibración en línea conectado a las entradas de los actuadores que regulan el clima al interior del invernadero, y hemos utilizado un modelo supervisor de LLM local entrenado previamente (Ollama llama3.2) que diagnostica y ajusta los setpoints de las variables climáticas externas. Dichos valoes climáticos externos las tomamos en tiempo real desde Mla estación meteorológica MeteoGalicia (ubicada en la zona más próxima a Paradela que es en Portomarín/Bóveda). 

El Dashboard en localhost lo hemos desarrollado en React (el frontend) su backend en fastAPI y cuando sea necesario utilizaremos una base de datos en PostgreSQL, por el momento el histórial del dataset de las distintas variables en 10 años lo hemos compilado y se actualizada en tiempo real en un archivo JSON local. 

Las visualización de las funciones de pertenencia del controlador Difuso a la salida del modelo LLM se muestran en tiempo real así como la activación o desactivación de los distintos actuadores que componen el sistema. El sistema está diseñado para ser implementado 100% local, sin uso de APIs externas ni tokens de pago usando herramientas Open Source.

![Dashboard Invernadero EcoSmart01](https://github.com/ecoruralia/invernadero-ecosmart/blob/main/demo/demo1.png)
![Dashboard Invernadero EcoSmart02](https://github.com/ecoruralia/invernadero-ecosmart/blob/main/demo/demo2.png).
![Dashboard Invernadero EcoSmart03](https://github.com/ecoruralia/invernadero-ecosmart/blob/main/demo/demo3.png).

[Ver Demo 🤠👉▶️](https://drive.google.com/file/d/1Z-qbThvZQTA1r9duXYIJJHbeYNd7qOGZ/view?usp=sharing).
 

**Análisis estratégico — Invernadero EcoSmart (Paradela, Lugo)**

Cifras orientativas 2026 para Galicia, España (IVA no incluido salvo indicación). No son un presupuesto cerrado de proveedor: sirven para decidir.

**1. Análisis FODA**
Fortalezas (internas +)
- Coste software ~0 €: FastAPI + React + Ollama local + MeteoGalicia pública. Sin licencias ni tokens ni nube.
- Gemelo digital con 10 años de datos (3652 días) y reentrenamiento en línea: R² temp 0.958, luz 0.987, CO₂ 0.897.
- Control híbrido seguro: fuzzy determinista en lazo + LLM solo como supervisor validado (luces de día bloqueadas, techo limitado con lluvia/viento).
- Stack ligero y mantenible por una persona: un puerto (9001), un dashboard en español, hardware modesto (mini-PC).
- Dato local real: Portomarín a ~6,8 km + viento de Bóveda; hora Europe/Madrid y setpoints por estación gallega.
Debilidades (internas −)
- Aún sin sensores interiores reales: el interior es estimado (gemelo), no medido. El suelo tiene R² débil (0.135).
- Proyecto unipersonal: si falla hardware/red eléctrica, no hay redundancia ni soporte 24 h.
- Calefacción e iluminación son el coste operativo dominante en invierno gallego.
- Dependencia de internet y red eléctrica para MeteoGalicia y actuadores.
Oportunidades (externas +)
- Mercado km 0: Lugo capital a ~30 min; venta directa, cestas, restauración local con prima de precio.
- Ayudas: convocatorias FEADER / PAC y Xunta de Galicia para modernización de explotaciones e incorporación de jóvenes (verificar convocatoria vigente: % típico 40–50 % de inversión elegible).
- Escalabilidad del software: el mismo sistema sirve para 2–3 módulos más sin reescribir.
- Diferenciación: "invernadero con IA local" vende en agroturismo, colegios y prensa local.
Amenazas (externas −)
- Precio de la energía (calefacción/luz) y sequías/olas de calor que tensionan riego y techo.
- Granizo, viento (>25 km/h ya limita el techo) y plagas del Miño.
- Cambios en la API de MeteoGalicia o cortes de conectividad rural.
- Competencia de precio de hortaliza de gran distribución.

**Objetivo General** Mejorada la calidad de la producción de hortalizas y vegetales inocuos en Hombres y Mujeres de la Comunidad del pueblo rural de Paradela

**Objetivo Específico**  Contribuir al aprovechamiento de parcelas y terrenos disponibles para  la producción EcoInteligente de hortalizas y vegetales de temporada en banacales elevados de madera reciclada con uso de la IA y tecnologías alternativas dentr de un invernadero de estructura metálica y cubierta de policarbonato con techo curvo estilo mariposa beneficiando a 810 Hombres y 804 mujeres Mujeres en la comunidad de Paradela

**Estimados**

Cifras orientativas para España, septiembre 2026, con IVA e instalación incluidas (±30 %). He contrastado los dos precios más volátiles: electricidad PVPC hoy ~0,18 €/kWh de media (horas solares de mediodía ~0,03–0,11 €/kWh, puntas de tarde 0,35) y ESP32 Kits de inicio con sensores: Los paquetes completos para proyectos de IoT cuestan alrededor de 26,99 € solo placa en tienda española.

Supuestos de partida
- Parcela familiar propia en Paradela (Lugo); invernadero tipo túnel de 500 m² (el de la documentación del proyecto).
- El software del proyecto (FastAPI + React + Ollama local + datos MeteoGalicia) cuesta 0 € en licencias: todo es open source y sin nube.
- Lo que sí hay que comprar es lo que el propio código reconoce como pendiente: "Se integrarán sensores reales cuando haya financiación" (main.py). Hoy el gemelo estima el interior con Ridge; el presupuesto lo convierte en sistema real.
- Se asume que hay red eléctrica en la parcela; internet se resuelve con la fibra/casa o un router 4G.

## Supuestos

- Parcela familiar propia en Paradela (Lugo); invernadero tipo túnel de **500 m²** ya existente.
- El software del proyecto (FastAPI + React + Ollama local + MeteoGalicia) cuesta **0 €** en licencias.
- Lo presupuestado es lo que el código reconoce como pendiente: sensores y actuadores reales
  (`main.py`: *"Se integrarán sensores reales cuando haya financiación"*).
- Red eléctrica disponible en la parcela; internet de la casa o router 4G.

![Ubicación]()

**Beneficios para una familia en Paradela**
# Beneficios — Gemelo digital EcoSmart para una familia en Paradela (Lugo)

> Lo que aporta el proyecto (invernadero de 500 m² tecnificado con gemelo digital:
> MeteoGalicia → Ridge → Fuzzy → supervisor LLM local → actuadores → aprendizaje en línea)
> a una familia con parcela en Paradela, Lugo, Galicia.
> Cifras orientativas, España, septiembre 2026 (±30 %).

## A. Beneficios cuantificables (€/año)

| Beneficio | Fundamento | Valor (€/año) |
|-----------|------------|---------------|
| Compra evitada de verdura | Un hogar gasta ~1.400–1.800 €/año en fruta y hortaliza; 500 m² tecnificados cubren el autoconsumo de una familia de 4–5 casi todo el año + conservas | 1.000–1.500 |
| Venta de excedente | 1.500–3.000 kg/año (tomate, pimiento, hoja, calabacín) a 1–2 €/kg en mercado de Sarria/Portomarín, cestas o restauración local | 1.000–2.500 |
| Ahorro de agua | Riego por goteo gobernado por humedad real de suelo (el gemelo riega solo si suelo < 70 %): 30–50 % menos que manguera/aspersión | 100–200 |
| Ahorro eléctrico vs. control manual | Ventilación pasiva antes que calefacción, luces solo cuando faltan, bombeo desplazable a horas solares baratas (~0,05 €/kWh a mediodía) | 80–150 |
| Temporada extendida | En Lugo la helada va de octubre a abril; con invernadero + anti-helada se pasa de 5–6 meses de cosecha a 9–10 (su valor va incluido en las dos primeras filas) | — |

**Total orientativo: ~2.000–4.000 €/año** entre ahorro y excedente.

**Beneficios no cuantificables**

- **Protección frente al clima de Paradela:** ~1.000 mm de lluvia/año, granizo y heladas
  tardías arruinan cosechas al aire libre; el techo automático por lluvia/viento
  (seguridades que ya implementa el código) elimina ese riesgo.
- **Salud y calidad:** producto km 0 sin tratamientos, recogido en su punto; al controlar
  HR y ventilación hay menos hongos, el gran problema del clima gallego.
- **Familia y territorio:** actividad intergeneracional en la parcela, relevo rural y
  aprendizaje técnico para los jóvenes; fija población y da uso productivo a la tierra.
- **Ayudas públicas:** posible cofinanciación del 40–50 % vía PGDR Galicia o ayudas a
  incorporación de jóvenes agricultores.
- **Resiliencia del hogar:** ante subidas de precios en tienda, la huerta tecnificada
  estabiliza el coste de la cesta familiar.
