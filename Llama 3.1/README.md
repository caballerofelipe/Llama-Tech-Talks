# 🦙 Módulo 2: Introducción a Llama 3.1

## 📋 Descripción

Este módulo proporciona una **demostración práctica completa** de las capacidades y características de **Llama 3.1**, uno de los modelos de lenguaje más avanzados de Meta. A través de un laboratorio interactivo, explorarás todas las funcionalidades del modelo desde la carga hasta aplicaciones prácticas.

## 📁 Contenido del Módulo

```
codigo/modulo2/
├── README.md                        # Este archivo
└── laboratorio-modulo-n2.ipynb     # Laboratorio completo de Llama 3.1
```

## 🎯 Objetivos de Aprendizaje

Al completar este módulo, dominarás:

1. **🔧 Carga y configuración** de modelos Llama 3.1
2. **⚡ Optimización de memoria** con cuantización 4-bit
3. **💬 Capacidades conversacionales** y formato de chat
4. **🌍 Soporte multilingüe** en 6+ idiomas
5. **💻 Generación de código** en múltiples lenguajes
6. **📊 Análisis de rendimiento** y métricas
7. **⚙️ Configuraciones de generación** para diferentes casos de uso

## 📓 Laboratorio Interactivo: `laboratorio-modulo-n2.ipynb`

### **🚀 Características Principales:**

- 🎮 **Demostración completa** con 11 secciones estructuradas
- 🔧 **Carga automática** con fallback a modelos alternativos
- 📊 **Análisis de rendimiento** en tiempo real
- 🌍 **Pruebas multilingües** extensivas
- 💻 **Generación de código** especializada
- ⚙️ **Comparación de configuraciones** de generación

### **📚 Secciones del Laboratorio:**

#### **1. 🔧 Configuración Inicial**
- Importación de librerías necesarias
- Configuración de autenticación HuggingFace
- Detección automática de GPU/CPU

#### **2. 🦙 Clase Llama31Demo**
- Arquitectura modular para demostraciones
- Gestión de memoria y recursos
- Información detallada del modelo

#### **3. ⚡ Carga con Cuantización**
- Configuración BitsAndBytesConfig 4-bit
- Optimización de memoria RAM/VRAM
- Reducción significativa de recursos

#### **4. 📥 Carga Básica (Fallback)**
- Configuración estándar sin cuantización
- Modelo alternativo si Llama 3.1 no está disponible
- Manejo robusto de errores

#### **5. 💬 Capacidades Conversacionales**
- Formato de chat con system/user/assistant
- Aplicación de chat templates
- Conversaciones multi-turno

#### **6. 🌍 Capacidades Multilingües**
- Pruebas en 6 idiomas: Español, English, Français, Deutsch, Italiano, Português
- Evaluación de calidad por idioma
- Comparación de rendimiento

#### **7. 💻 Generación de Código**
- Python, JavaScript, SQL
- Algoritmos y estructuras de datos
- Análisis de calidad del código

#### **8. 📊 Análisis de Rendimiento**
- Medición de tiempo de respuesta
- Velocidad de generación (tokens/segundo)
- Uso de memoria en tiempo real

#### **9. ⚙️ Configuraciones de Generación**
- **Conservadora**: Respuestas predecibles
- **Balanceada**: Equilibrio creatividad/coherencia
- **Creativa**: Máxima diversidad
- **Determinística**: Resultados reproducibles

## 🛠️ Instalación y Configuración

### **📋 Requisitos:**

```bash
# Dependencias principales
pip install torch transformers accelerate
pip install bitsandbytes  # Para cuantización
pip install psutil matplotlib  # Para análisis
```

### **🔑 Configuración de Acceso:**

#### **Opción 1: Token HuggingFace (Recomendado)**
```python
# Crear archivo config/hf_config.py
HF_TOKEN = "hf_tu_token_aqui"
```

#### **Opción 2: Login Manual**
```bash
huggingface-cli login
```

### **🚀 Ejecución:**

#### **En Jupyter/Colab:**
1. Sube el notebook `laboratorio-modulo-n2.ipynb`
2. Ejecuta las celdas secuencialmente
3. Interactúa con las demostraciones

#### **En Kaggle:**
1. Activa GPU T4 x2 en configuración
2. Configura HF_TOKEN en Secrets
3. Ejecuta el notebook completo

## 🔍 Análisis Detallado de Capacidades

### **💬 Capacidades Conversacionales**

**Formato de entrada:**
```python
conversacion = [
    {"role": "system", "content": "Eres un asistente útil..."},
    {"role": "user", "content": "¿Puedes explicar...?"},
    {"role": "assistant", "content": "Por supuesto..."}
]
```

**Características evaluadas:**
- Coherencia en conversaciones largas
- Mantenimiento de contexto
- Personalidad consistente

### **🌍 Evaluación Multilingüe**

**Idiomas probados:**
- **🇪🇸 Español**: Idioma nativo del curso
- **🇺🇸 English**: Idioma principal del modelo
- **🇫🇷 Français**: Evaluación europea
- **🇩🇪 Deutsch**: Complejidad gramatical
- **🇮🇹 Italiano**: Similitud con español
- **🇧🇷 Português**: Idioma hermano

**Métricas evaluadas:**
- Fluidez y naturalidad
- Precisión gramatical
- Coherencia semántica

### **💻 Capacidades de Código**

**Lenguajes evaluados:**
- **Python**: Algoritmos y estructuras de datos
- **JavaScript**: Programación web y clases
- **SQL**: Consultas y optimización
- **Algoritmos**: Búsqueda, ordenamiento, recursión

**Criterios de evaluación:**
- Sintaxis correcta
- Lógica funcional
- Buenas prácticas
- Comentarios explicativos

## 📊 Métricas de Rendimiento

### **⏱️ Tiempo de Respuesta**
- **Promedio**: 0.3-2.0 segundos
- **Factores**: Longitud del prompt, configuración GPU
- **Optimización**: Cuantización reduce tiempo

### **🚀 Velocidad de Generación**
- **Rango típico**: 10-50 tokens/segundo
- **Dependencias**: Hardware, configuración
- **Medición**: Palabras generadas por segundo

### **💾 Uso de Memoria**
- **Modelo completo**: ~15-30 GB
- **Con cuantización 4-bit**: ~4-8 GB
- **Optimización**: 60-75% reducción

## ⚙️ Configuraciones de Generación

### **🎛️ Parámetros Clave:**

| **Configuración** | **Temperature** | **Top-p** | **Uso Recomendado** |
|-------------------|-----------------|-----------|---------------------|
| **Conservadora** | 0.3 | 0.8 | Respuestas técnicas, documentación |
| **Balanceada** | 0.7 | 0.9 | Uso general, conversaciones |
| **Creativa** | 1.0 | 0.95 | Escritura creativa, brainstorming |
| **Determinística** | 0.0 | - | Resultados reproducibles |

### **🎯 Casos de Uso:**

- **📚 Educación**: Configuración conservadora
- **💬 Chat**: Configuración balanceada  
- **🎨 Creatividad**: Configuración creativa
- **🔬 Investigación**: Configuración determinística

## 🚨 Solución de Problemas

### **❌ "Modelo no accesible"**
**Problema**: Error 401 al acceder a Llama 3.1
**Solución**:
1. Solicita acceso en [HuggingFace](https://huggingface.co/meta-llama/Meta-Llama-3.1-8B-Instruct)
2. Configura token HF correctamente
3. El notebook usa modelo alternativo automáticamente

### **❌ "Memoria insuficiente"**
**Problema**: CUDA out of memory
**Solución**:
1. Activa cuantización 4-bit
2. Reduce batch size
3. Usa modelo más pequeño

### **❌ "Respuestas de baja calidad"**
**Problema**: Modelo alternativo genera respuestas pobres
**Solución**:
1. Obtén acceso a Llama 3.1 original
2. Ajusta parámetros de generación
3. Usa prompts más específicos

## 🎓 Ejercicios Sugeridos

### **Nivel Básico:**
1. Ejecuta todas las demostraciones del laboratorio
2. Compara respuestas entre configuraciones
3. Prueba prompts en diferentes idiomas

### **Nivel Intermedio:**
1. Modifica parámetros de generación
2. Crea tus propios prompts de prueba
3. Analiza métricas de rendimiento

### **Nivel Avanzado:**
1. Implementa nuevas métricas de evaluación
2. Compara con otros modelos
3. Optimiza configuraciones para casos específicos

## 🔗 Recursos Adicionales

### **📚 Documentación Oficial:**
- [Llama 3.1 Model Card](https://huggingface.co/meta-llama/Meta-Llama-3.1-8B-Instruct)
- [Transformers Documentation](https://huggingface.co/docs/transformers)
- [BitsAndBytesConfig](https://huggingface.co/docs/transformers/quantization)

### **🎥 Videos Relacionados:**
- [Meta AI: Introducing Llama 3.1](https://ai.meta.com/blog/meta-llama-3-1/)
- [Quantization Techniques](https://huggingface.co/blog/4bit-transformers-bitsandbytes)

### **🛠️ Herramientas Útiles:**
- [Gradio](https://gradio.app/) - Interfaces web para modelos
- [Streamlit](https://streamlit.io/) - Apps de ML interactivas
- [LangChain](https://langchain.com/) - Framework para LLMs

## 🚀 Próximos Pasos

Después de completar este módulo:

1. **Módulo 3**: Fine-tuning y personalización de modelos
2. **Módulo 4**: Aplicaciones prácticas y casos de uso
3. **Módulo 5**: Despliegue y optimización en producción

## 🤝 Contribuciones

¿Tienes ideas para mejorar el laboratorio?

1. Reporta bugs o problemas
2. Sugiere nuevas demostraciones
3. Comparte tus experimentos
4. Contribuye con optimizaciones

## 📄 Licencia

Este material educativo está disponible bajo licencia MIT. Libre uso para educación y investigación.

---

**¡Explora el poder de Llama 3.1 y descubre las capacidades de los LLMs modernos!** 🦙🚀✨
