# Clasificación y Detección Automática de SMS Spam mediante Modelos Preentrenados de Hugging Face

*Nombre del alumno:* Angélica Samantha Álvarez Herrera  
*Matrícula:* AL07182919  
*Materia:* Gestión de Proyectos de Inteligencia Artificial  

---

## 1. Descripción del Proyecto
Este proyecto evalúa y compara el desempeño de tres modelos preentrenados de Procesamiento de Lenguaje Natural (NLP) del ecosistema Hugging Face Hub para clasificar mensajes de texto en dos categorías: *Ham (Mensaje legítimo)* o *Spam (Mensaje no deseado o malicioso)*.

El objetivo principal es analizar el equilibrio (trade-off) entre la *precisión* de los modelos y su *latencia (tiempo de respuesta)* en un entorno de prototipado rápido utilizando Google Colab con aceleración por GPU (NVIDIA T4).

---

## 2. Estructura del Dataset
Se utilizó el dataset *UCI SMS Spam Collection* disponible en el ecosistema Hugging Face:
* *Total de registros:* 5,572 mensajes (4,825 Ham y 747 Spam).
* *Campos principales:*
  * text (string): Cuerpo del mensaje SMS.
  * label (int): Categoría numérica (0 = Ham, 1 = Spam).

---

## 3. Resultados de la Evaluación Comparativa
La prueba se realizó sobre una muestra representativa de 500 mensajes procesados por GPU:

| Modelo | Accuracy | Precision | Recall | F1-Score | Latencia Promedio (ms/msg) |
| :--- | :---: | :---: | :---: | :---: | :---: |
| *BERT-Tiny* | 0.9840 | 0.9655 | 0.9032 | 0.9333 | *2.92 ms* |
| *DistilRoBERTa* | *1.0000* | *1.0000* | *1.0000* | *1.0000* | 6.21 ms |
| *RoBERTa-Base* | 0.9940 | 0.9683 | 0.9839 | 0.9760 | 10.11 ms |

---

## 4. Instrucciones de Ejecución
1. Clonar este repositorio o descargar los archivos.
2. Instalar las dependencias listadas en requirements.txt:
   ```bash
   pip install -r requirements.txt

3. Abrir el cuaderno de trabajo ubicado dentro del repositorio (Actividad_4.ipynb o notebooks/Actividad_4.ipynb) en Google Colab.
4. Asegurarse de activar la GPU T4 en Google Colab en: Entorno de ejecución > Cambiar tipo de entorno de ejecución > T4 GPU.
5. Ejecutar todas las celdas en orden secuencial para reproducir los análisis y los resultados obtenidos.

## 5. Conclusión y Modelo Seleccionado
Se selecciona el modelo DistilRoBERTa (SharpWoofer/distilroberta-sms-spam-detector) como la mejor solución técnica para un entorno de producción, ya que alcanzó métricas perfectas (F1-Score de 1.0000) con una latencia muy baja de 6.21 ms por mensaje, ofreciendo el equilibrio óptimo entre precisión y rendimiento computacional.
   
