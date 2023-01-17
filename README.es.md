<!-- hide -->
# Logistic Regression Project Tutorial
<!-- endhide -->

- Comprender tus datos.
- Seguir las instrucciones de limpieza.
- Modelar tus datos usando Regresión Logística.
- Optimizar tu modelo y guárdalo.

## 🌱  Cómo iniciar este proyecto

Esta vez no se hará Fork, tómate un tiempo para leer estas instrucciones:

1. Crear un nuevo repositorio basado en el [proyecto de Machine Learing](https://github.com/4GeeksAcademy/machine-learning-python-template/generate) [haciendo clic aquí](https://github.com/4GeeksAcademy/machine-learning-python-template).
2. Abre el repositorio creado recientemente en Gitpod usando la [extensión del botón de Gitpod](https://www.gitpod.io/docs/browser-extension/).
3. Una vez que Gitpod VSCode haya terminado de abrirse, comienza tu proyecto siguiendo las instrucciones a continuación.

## 🚛 Cómo entregar este proyecto

Una vez que hayas terminado de resolver los ejercicios, asegúrate de confirmar tus cambios, hazle "push" al fork de tu repositorio y ve a 4Geeks.com para subir el enlace del repositorio.

## 📝 Instrucciones

**Campaña de Marketing Bancario**:

Comprensión Empresarial:

Los depósitos a plazo permiten a los bancos retener dinero durante un período de tiempo específico, lo que permite al banco utilizar ese dinero para mejores inversiones. Las campañas de marketing de este producto se basaron en llamadas telefónicas. Muchas veces se requería más de un contacto con el mismo cliente, para saber si el depósito a plazo estaría o no suscrito.

Descripción del problema:

El banco portugués está teniendo una disminución en sus ingresos, por lo que quieren poder identificar a los clientes existentes que tienen una mayor probabilidad de suscribir un depósito a plazo. Esto permitirá que el banco centre sus esfuerzos de marketing en esos clientes y evitará perder dinero y tiempo en clientes que probablemente no se suscribirán, ya que quieren aumentar sus ingresos. 

Para abordar este problema crearemos un algoritmo de clasificación que ayude a predecir si un cliente suscribirá o no un depósito a plazo.

**Paso 1:**

El conjunto de datos se puede encontrar en esta carpeta de proyecto como archivo 'bank-marketing-campaign-data.csv'. Te invitamos a cargarlo directamente desde el enlace (`https://raw.githubusercontent.com/4GeeksAcademy/logistic-regression-project-tutorial/main/bank-marketing-campaign-data.csv`), o para descargarlo y agregarlo a tu carpeta data/raw. En ese caso, no olvides agregar la carpeta de datos al archivo .gitignore.

Solo se ha proporcionado un conjunto de datos etiquetado porque queremos que practiques tus habilidades de modelado.

No es necesario que hagas predicciones, ya que no se ha proporcionado ningún conjunto de prueba, sin embargo, asegúrate de dividir tus datos en conjuntos de entrenamiento y validación para evaluar el rendimiento de tu modelo, porque el banco solicitaría un modelo confiable para que lo usen.

En esta ocasión queremos que te centres en la parte de modelado y optimización, por lo que te daremos algunas pistas para el proceso de limpieza.

¡Es hora de trabajar en ello!

**Paso 2:**

Realiza un análisis de datos exploratorio rápido. Comprueba qué categorías hay en cada función.

¿Tus datos están equilibrados o desequilibrados? 

Puedes usar un diagrama de barras para visualizar tu variable objetivo para verificar si está balanceada o no.

Si no recuerdas cómo lidiar con conjuntos de datos desequilibrados, puedes ir a tu clase de estadística y buscar los consejos en el párrafo específico de conjuntos de datos desequilibrados.: https://github.com/4GeeksAcademy/machine-learning-content/blob/master/02-6d-stats/hypothesis-testing.ipynb 

> Sugerencia: Elije tu métrica de evaluación correctamente si tus datos están desequilibrados. 

**Paso 3:**

Significado de cada atributo:

1. Edad (numérica).

2. Trabajo: Tipo de trabajo (categórico).

3. Civil: estado civil (categórico).

4. Educación: (categórico).

5. Mora: ¿tiene crédito en mora? (categórico).

6. Vivienda: ¿tiene un préstamo de vivienda? (categórico).

7. Préstamo: tiene un préstamo personal? (categórico).

8. Contacto: tipo de comunicación de contacto (categórica).

9. Mes: último mes de contacto del año (categórico).

10. day_of_week: último día de contacto de la semana (categórico).

11. Duración: duración del último contacto, en segundos (numérico).

Nota importante: esta salida afecta en gran medida al objetivo de salida (si la duración = 0, entonces y = 'no'). Sin embargo, la duración no se conoce antes de que se realice una llamada. Además, después del final de la llamada, obviamente se conoce y. Considera si debes incluirlo o no para un modelo predictivo realista.

12. Campaña: número de contactos realizados durante esta campaña y para este cliente (numérico).

13. Pdays: número de días que transcurrieron después de que el cliente fue contactado por última vez de una campaña anterior (numérico; 999 significa que el cliente no fue contactado previamente)

14. Anterior: número de contactos realizados antes de esta campaña y para este cliente (numérico).

15. Poutcome: resultado de la campaña de marketing anterior (categórico).

Nota importante: este atributo tiene tres categorías: 'fracaso', 'éxito' e 'inexistente'. El 86% de los datos cae en la categoría 'inexistente'.

16. emp.var.rate: tasa de variación del empleo - indicador trimestral (numérico).

17. cons.price.idx: índice de precios al consumidor- indicador mensual (numérico).

18. cons.conf.idx: índice de confianza del consumidor - indicador mensual (numérico).

19. euribor3m: tasa euribor 3 meses: - indicador diario (numérico).

20. nr.employed: número de empleados - indicador trimestral (numérico).

Variable objetivo: 

21. y: ¿el cliente ha suscrito un depósito a plazo?  

Sugerencia para el proceso de limpieza:

1. El conjunto de datos no tiene valores nulos, pero asegúrate de eliminar las filas duplicadas.

2. Hay algunas funciones que incluyen valores desconocidos.

- En las características categóricas, reemplaza la categoría desconocida con el valor más frecuente.

- En las características numéricas, reemplaza los valores desconocidos con la media.

> Crea una función que funcione en todas esas categorías es una buena práctica.

3. Busca valores atípicos. Hay tres características que muestran valores atípicos. Elimina todos los valores atípicos utilizando el IQR para establecer los límites superior e inferior.

4. Convierte la edad en datos categóricos creando grupos de edad de diez años.

> Usa .cut en pandas y usa los siguientes contenedores: [10,20,30,40,50,60,70,80,90,100].

5. Inserta las categorías 'básico.9y', 'básico.6y', 'basic4y' en 'middle_school'

6. Convierte la variable objetivo en binaria.

7. Codifica características categóricas.

8. Escala tus datos.

9. Siéntete libre de seleccionar las características que consideres importantes para el modelo.

**Paso 4:**

¡Es hora de construir tu modelo!

1. Separa tu variable objetivo de los predictores.

2. Elije cómo dividir tus datos para evaluar el rendimiento de tu modelo.

3. Crea un primer modelo de regresión logística con hiperparámetros predeterminados.

4. Hiperajusta tu modelo para mejorar sus resultados.

5. Usa app.py para crear un pipeline.

6. Guarda tu modelo final en la carpeta 'modelos'.

7. En tu archivo README escribe un breve resumen.

8. Entrega tu enlace de repositorio.

Guía de soluciones: https://github.com/4GeeksAcademy/logistic-regression-project-tutorial/blob/main/cleaning-solution.ipynb
