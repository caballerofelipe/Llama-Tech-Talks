# 🧠 Módulo 1: Fundamentos de Transformers y Mecanismo de Atención

## 📋 Descripción

Este módulo introduce los **conceptos fundamentales** de los modelos Transformer y el **mecanismo de atención**, que son la base de los modelos de lenguaje modernos como GPT, BERT, y Llama.

## 📁 Contenido del Módulo

```
codigo/modulo1/
├── README.md                 # Este archivo
└── demo-atencion.ipynb      # Demo interactiva del mecanismo de atención
```

## 🎯 Objetivos de Aprendizaje

Al completar este módulo, entenderás:

1. **🔍 Qué es el mecanismo de atención** y por qué es revolucionario
2. **🧮 Cómo funciona matemáticamente** la atención en los Transformers
3. **👁️ Visualización práctica** de patrones de atención en modelos reales
4. **🔗 Relaciones entre tokens** y cómo el modelo las aprende
5. **🏗️ Arquitectura básica** de los modelos Transformer

## 📓 Demo Interactiva: Mecanismo de Atención

### **🚀 `demo-atencion.ipynb`**

Un notebook interactivo que te permite **explorar visualmente** cómo funciona el mecanismo de atención en un modelo BERT real.

#### **✨ Características:**

- 🎮 **Interfaz interactiva** con widgets para explorar diferentes capas y cabezas
- 📊 **Visualización en tiempo real** de patrones de atención
- 🇪🇸 **Modelo en español** (BERT español de la Universidad de Chile)
- 🎨 **Gráficos intuitivos** que muestran conexiones entre tokens
- 🔢 **Valores numéricos** de atención para análisis detallado

#### **🎛️ Controles Interactivos:**

- **Layer Selector**: Explora las 12 capas del modelo BERT
- **Head Selector**: Examina las 12 cabezas de atención por capa
- **Token Selector**: Elige qué token analizar como origen de atención

#### **📝 Ejemplo de Análisis:**

**Frase:** *"El perro que persiguió al gato cruzó la calle."*

**Observaciones típicas:**
- **Capa 0-2**: Atención principalmente a tokens adyacentes
- **Capa 3-6**: Patrones sintácticos (sujeto-verbo, artículo-sustantivo)
- **Capa 7-11**: Relaciones semánticas complejas y dependencias largas

## 🛠️ Instalación y Uso

### **Requisitos:**
```bash
pip install transformers==4.41.2
pip install ipywidgets
pip install matplotlib
pip install torch
```

### **Ejecución:**

1. **Abrir el notebook:**
   ```bash
   jupyter notebook demo-atencion.ipynb
   ```

2. **En Kaggle/Colab:**
   - Sube el archivo `demo-atencion.ipynb`
   - Ejecuta todas las celdas secuencialmente
   - Interactúa con los widgets para explorar

3. **Uso local:**
   - Asegúrate de tener Jupyter instalado
   - Ejecuta en un entorno con las dependencias instaladas

## 🔍 Conceptos Clave Explicados

### **1. Mecanismo de Atención**

El mecanismo de atención permite que cada token en una secuencia **"preste atención"** a todos los demás tokens, determinando qué información es relevante para su procesamiento.

**Fórmula básica:**
```
Attention(Q, K, V) = softmax(QK^T / √d_k)V
```

Donde:
- **Q** (Query): "¿Qué estoy buscando?"
- **K** (Key): "¿Qué información tengo?"
- **V** (Value): "¿Cuál es esa información?"

### **2. Multi-Head Attention**

Cada capa tiene **múltiples cabezas** de atención que aprenden diferentes tipos de relaciones:

- **Cabeza 1**: Relaciones sintácticas (sujeto-verbo)
- **Cabeza 2**: Dependencias semánticas
- **Cabeza 3**: Patrones posicionales
- **...y así sucesivamente**

### **3. Capas y Especialización**

- **Capas tempranas (0-3)**: Patrones locales y sintaxis básica
- **Capas medias (4-8)**: Estructura gramatical y dependencias
- **Capas tardías (9-11)**: Semántica compleja y razonamiento

## 📊 Interpretación de Visualizaciones

### **🎨 Elementos Visuales:**

1. **Líneas de conexión**: Grosor = intensidad de atención
2. **Colores**: Escala de calor (azul = baja, rojo = alta atención)
3. **Tokens resaltados**: 
   - **Azul**: Token origen (desde donde se calcula atención)
   - **Rojo**: Token con mayor atención recibida
4. **Valores numéricos**: Puntuaciones exactas de atención

### **🔍 Patrones Comunes:**

- **Atención a sí mismo**: Tokens que se atienden a sí mismos
- **Atención posicional**: Preferencia por tokens cercanos
- **Atención sintáctica**: Conexiones gramaticales (artículo→sustantivo)
- **Atención semántica**: Relaciones de significado

## 🎓 Ejercicios Sugeridos

### **Nivel Básico:**
1. Ejecuta el demo con la frase por defecto
2. Observa cómo cambian los patrones entre capas
3. Identifica qué cabezas se especializan en qué tipos de relaciones

### **Nivel Intermedio:**
1. Cambia la frase de entrada por una más compleja
2. Analiza cómo el modelo maneja ambigüedades
3. Compara patrones entre diferentes tipos de palabras (sustantivos vs verbos)

### **Nivel Avanzado:**
1. Modifica el código para usar otros modelos (GPT, RoBERTa)
2. Implementa métricas de análisis de atención
3. Crea visualizaciones adicionales (mapas de calor, grafos)

## 🔗 Recursos Adicionales

### **📚 Lecturas Recomendadas:**
- [Attention Is All You Need](https://arxiv.org/abs/1706.03762) - Paper original de Transformers
- [The Illustrated Transformer](http://jalammar.github.io/illustrated-transformer/) - Explicación visual
- [BERT: Pre-training of Deep Bidirectional Transformers](https://arxiv.org/abs/1810.04805)

### **🎥 Videos Educativos:**
- [3Blue1Brown: Attention in transformers](https://www.youtube.com/watch?v=eMlx5fFNoYc)
- [Andrej Karpathy: Let's build GPT](https://www.youtube.com/watch?v=kCc8FmEb1nY)

### **🛠️ Herramientas Relacionadas:**
- [BertViz](https://github.com/jessevig/bertviz) - Visualización avanzada de atención
- [Transformers Interpret](https://github.com/cdpierse/transformers-interpret) - Interpretabilidad
- [Attention Visualizer](https://github.com/PAIR-code/attention-viz) - Google Research

## 🚀 Próximos Pasos

Después de completar este módulo:

1. **Módulo 2**: Arquitectura completa de Transformers
2. **Módulo 3**: Modelos de lenguaje generativos (GPT)
3. **Módulo 4**: Fine-tuning y adaptación de modelos
4. **Módulo 5**: Llama 3 y modelos de código abierto

## 🤝 Contribuciones

¿Encontraste un error o tienes una mejora? 

1. Abre un issue describiendo el problema
2. Propón cambios via pull request
3. Comparte tus experimentos y descubrimientos

## 📄 Licencia

Este material educativo está disponible bajo licencia MIT. Siéntete libre de usar, modificar y compartir.

---

**¡Disfruta explorando el fascinante mundo de la atención en los Transformers!** 🧠✨
