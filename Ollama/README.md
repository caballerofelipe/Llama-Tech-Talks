# 🚀 Módulo 3: Deployment y Consumo de Llama 3.1 con Ollama

## 📋 Descripción

Este módulo te enseña a **desplegar y consumir modelos Llama 3.1** usando **Ollama**, una herramienta que permite ejecutar LLMs localmente de forma eficiente. Aprenderás desde la instalación hasta el desarrollo de aplicaciones que consumen el modelo a través de API REST.

## 📁 Contenido del Módulo

```
codigo/modulo3/
├── README.md                        # Este archivo
└── laboratorio-modulo-n3.ipynb     # Laboratorio completo de Ollama
```

## 🎯 Objetivos de Aprendizaje

Al completar este módulo, dominarás:

1. **🛠️ Instalación y configuración** de Ollama en Windows/Mac
2. **⚙️ Configuración del entorno** de desarrollo con VS Code
3. **🦙 Descarga y ejecución** de modelos Llama 3.1 localmente
4. **🌐 Consumo de modelos** a través de API REST
5. **🔧 Configuración de parámetros** de generación
6. **📡 Streaming de respuestas** en tiempo real
7. **🐍 Desarrollo de aplicaciones** Python que integran LLMs
8. **🌐 Creación de APIs web** con Flask

## 🛠️ Herramientas y Tecnologías

### **🔧 Software Requerido:**
- **Visual Studio Code** - Editor de código principal
- **Python 3.10+** - Lenguaje de programación
- **Ollama** - Runtime para modelos LLM locales
- **Git** (opcional) - Control de versiones

### **📦 Librerías Python:**
- **requests** - Cliente HTTP para API REST
- **jupyter** - Notebooks interactivos
- **flask** (opcional) - Framework web
- **json** - Manejo de datos JSON

## 📓 Laboratorio Práctico: `laboratorio-modulo-n3.ipynb`

### **🚀 Estructura del Laboratorio:**

#### **0. 🛠️ Instalación de Herramientas**
- **Visual Studio Code**: Editor principal
- **Python 3.10+**: Entorno de desarrollo
- **Extensiones VS Code**: Python y Jupyter

#### **1. 🔧 Preparación del Entorno**
- **Entorno virtual**: Aislamiento de dependencias
- **Instalación de librerías**: requests, jupyter
- **Configuración de VS Code**: Terminal integrada

#### **2. 📥 Instalación de Ollama**
- **Windows**: Instalador oficial + WSL2
- **Mac**: Homebrew o instalador oficial
- **Verificación**: Comando `ollama --version`

#### **3. 🦙 Descarga y Ejecución de Llama 3.1**
- **Descarga del modelo**: `ollama pull llama3`
- **Prueba desde terminal**: Comandos básicos
- **Verificación de funcionamiento**: Respuestas simples

#### **4. 🌐 Consumo via API REST**
- **Configuración de cliente**: requests HTTP
- **Llamadas básicas**: Generación de texto
- **Parámetros de configuración**: temperature, top_p
- **Manejo de respuestas**: JSON parsing

#### **5. 📡 Streaming de Respuestas**
- **Respuestas en tiempo real**: stream=True
- **Procesamiento incremental**: iter_lines()
- **Experiencia de usuario**: Feedback inmediato

#### **6. 🛡️ Manejo de Errores**
- **Errores de conexión**: Ollama no disponible
- **Timeouts**: Respuestas lentas
- **Manejo robusto**: try/except patterns

#### **7. 🌐 Servidor Web con Flask**
- **API REST personalizada**: Endpoints propios
- **Integración con Ollama**: Proxy de requests
- **Desarrollo web**: Aplicaciones completas

## 🚀 Guía de Instalación Paso a Paso

### **1. 🖥️ Instalación de Visual Studio Code**

#### **Windows/Mac:**
1. Descarga desde [https://code.visualstudio.com/](https://code.visualstudio.com/)
2. Ejecuta el instalador
3. Instala extensiones requeridas:
   - **Python** (Microsoft)
   - **Jupyter** (Microsoft)

### **2. 🐍 Instalación de Python**

#### **Windows:**
1. Descarga desde [https://www.python.org/downloads/](https://www.python.org/downloads/)
2. **IMPORTANTE**: Marca "Add Python to PATH"
3. Verifica: `python --version`

#### **Mac:**
```bash
# Opción 1: Instalador oficial
# Descarga desde python.org

# Opción 2: Homebrew
brew install python
```

### **3. 🦙 Instalación de Ollama**

#### **Windows:**
1. Descarga desde [https://ollama.ai/download](https://ollama.ai/download)
2. Ejecuta el instalador
3. WSL2 se instala automáticamente si es necesario
4. Verifica: `ollama --version`

#### **Mac:**
```bash
# Opción 1: Homebrew (recomendado)
brew install ollama

# Opción 2: Instalador oficial
# Descarga desde ollama.ai/download
```

### **4. 🔧 Configuración del Entorno**

#### **Crear entorno virtual:**
```bash
# Windows
python -m venv venv
.\venv\Scripts\activate

# Mac/Linux
python3 -m venv venv
source venv/bin/activate
```

#### **Instalar dependencias:**
```bash
pip install jupyter requests flask
```

## 🦙 Uso de Ollama

### **📥 Descarga de Modelos**

```bash
# Llama 3.1 (recomendado)
ollama pull llama3

# Otros modelos disponibles
ollama pull llama3:70b      # Versión grande
ollama pull codellama       # Especializado en código
ollama pull mistral         # Alternativa rápida
```

### **🔍 Comandos Básicos**

```bash
# Listar modelos instalados
ollama list

# Ejecutar modelo interactivo
ollama run llama3

# Ejecutar con prompt directo
ollama run llama3 "Explica qué es la IA"

# Iniciar servidor (si no está corriendo)
ollama serve
```

### **⚙️ Configuración del Servidor**

```bash
# Puerto por defecto: 11434
# Host por defecto: localhost
# URL completa: http://localhost:11434
```

## 🌐 API REST de Ollama

### **📡 Endpoint Principal**

```
POST http://localhost:11434/api/generate
```

### **📋 Parámetros de Request**

```json
{
  "model": "llama3",
  "prompt": "Tu pregunta aquí",
  "stream": false,
  "temperature": 0.7,
  "top_p": 0.9,
  "max_tokens": 100
}
```

### **📊 Parámetros de Configuración**

| **Parámetro** | **Rango** | **Descripción** | **Uso Recomendado** |
|---------------|-----------|-----------------|---------------------|
| `temperature` | 0.0-2.0 | Creatividad/Aleatoriedad | 0.3 (conservador), 0.7 (balanceado), 1.0 (creativo) |
| `top_p` | 0.0-1.0 | Diversidad de tokens | 0.9 (recomendado) |
| `stream` | true/false | Respuesta en tiempo real | true (UX mejor), false (simple) |
| `max_tokens` | 1-∞ | Longitud máxima | 100-500 (típico) |

### **🐍 Ejemplo de Código Python**

```python
import requests
import json

OLLAMA_HOST = "http://localhost:11434"

def consultar_llama(prompt, temperature=0.7):
    payload = {
        "model": "llama3",
        "prompt": prompt,
        "temperature": temperature,
        "stream": False
    }
    
    try:
        response = requests.post(
            f"{OLLAMA_HOST}/api/generate", 
            json=payload,
            timeout=60
        )
        response.raise_for_status()
        return response.json().get("response", "")
    
    except requests.exceptions.ConnectionError:
        return "Error: Ollama no está corriendo"
    except Exception as e:
        return f"Error: {e}"

# Uso
respuesta = consultar_llama("¿Qué es machine learning?")
print(respuesta)
```

## 📡 Streaming de Respuestas

### **🔄 Implementación de Streaming**

```python
def consultar_streaming(prompt):
    payload = {
        "model": "llama3",
        "prompt": prompt,
        "stream": True
    }
    
    response = requests.post(
        f"{OLLAMA_HOST}/api/generate", 
        json=payload, 
        stream=True
    )
    
    print("Respuesta: ", end="", flush=True)
    for line in response.iter_lines():
        if line:
            chunk = json.loads(line)
            print(chunk.get("response", ""), end="", flush=True)
            if chunk.get("done"):
                print("\n--- Completado ---")
                break
```

### **✨ Ventajas del Streaming**

- **⚡ Respuesta inmediata**: Usuario ve progreso
- **🎯 Mejor UX**: Sensación de velocidad
- **🔄 Interactividad**: Posibilidad de cancelar
- **📱 Apps en tiempo real**: Chat interfaces

## 🌐 Desarrollo de APIs Web

### **🐍 Servidor Flask Básico**

```python
from flask import Flask, request, jsonify
import requests

app = Flask(__name__)
OLLAMA_HOST = "http://localhost:11434"

@app.route('/chat', methods=['POST'])
def chat():
    datos = request.json
    prompt = datos.get("prompt", "")
    
    payload = {
        "model": "llama3",
        "prompt": prompt,
        "stream": False
    }
    
    try:
        resp = requests.post(f"{OLLAMA_HOST}/api/generate", json=payload)
        return jsonify(resp.json())
    except Exception as e:
        return jsonify({"error": str(e)}), 500

if __name__ == "__main__":
    app.run(port=5000, debug=True)
```

### **🌐 Frontend HTML Simple**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Chat con Llama 3.1</title>
</head>
<body>
    <div id="chat"></div>
    <input type="text" id="prompt" placeholder="Escribe tu pregunta...">
    <button onclick="enviarPregunta()">Enviar</button>
    
    <script>
        async function enviarPregunta() {
            const prompt = document.getElementById('prompt').value;
            const response = await fetch('/chat', {
                method: 'POST',
                headers: {'Content-Type': 'application/json'},
                body: JSON.stringify({prompt: prompt})
            });
            const data = await response.json();
            document.getElementById('chat').innerHTML += 
                `<p><strong>Tú:</strong> ${prompt}</p>
                 <p><strong>Llama:</strong> ${data.response}</p>`;
        }
    </script>
</body>
</html>
```

## 🚨 Solución de Problemas

### **❌ "Ollama no está corriendo"**
**Problema**: Error de conexión a localhost:11434
**Soluciones**:
1. Ejecutar `ollama serve` en terminal
2. Verificar que el puerto 11434 esté libre
3. Reiniciar Ollama: `ollama stop` → `ollama serve`

### **❌ "Modelo no encontrado"**
**Problema**: Model 'llama3' not found
**Soluciones**:
1. Descargar modelo: `ollama pull llama3`
2. Verificar modelos: `ollama list`
3. Usar modelo alternativo disponible

### **❌ "Respuestas muy lentas"**
**Problema**: Timeouts o respuestas tardías
**Soluciones**:
1. Reducir `max_tokens`
2. Aumentar `timeout` en requests
3. Usar modelo más pequeño
4. Verificar recursos del sistema (RAM/CPU)

### **❌ "Error de memoria"**
**Problema**: Sistema sin recursos suficientes
**Soluciones**:
1. Cerrar aplicaciones innecesarias
2. Usar modelo más pequeño (llama3:7b)
3. Aumentar memoria virtual
4. Considerar modelo cuantizado

## 🎓 Ejercicios Prácticos

### **Nivel Básico:**
1. **Instalación completa**: Configura todo el entorno
2. **Primera consulta**: Haz una pregunta simple a Llama 3.1
3. **Parámetros básicos**: Experimenta con temperature
4. **Manejo de errores**: Implementa try/except

### **Nivel Intermedio:**
1. **Streaming**: Implementa respuestas en tiempo real
2. **API personalizada**: Crea endpoints con Flask
3. **Frontend simple**: HTML + JavaScript básico
4. **Configuraciones**: Compara diferentes parámetros

### **Nivel Avanzado:**
1. **Chat completo**: Aplicación web funcional
2. **Múltiples modelos**: Soporte para varios LLMs
3. **Autenticación**: Sistema de usuarios
4. **Optimización**: Caché y performance

## 🔗 Recursos Adicionales

### **📚 Documentación Oficial:**
- [Ollama Documentation](https://ollama.ai/docs)
- [Ollama API Reference](https://github.com/ollama/ollama/blob/main/docs/api.md)
- [Llama 3.1 Model Card](https://huggingface.co/meta-llama/Meta-Llama-3.1-8B-Instruct)

### **🛠️ Herramientas Complementarias:**
- [Ollama Web UI](https://github.com/open-webui/open-webui) - Interfaz web completa
- [LangChain](https://langchain.com/) - Framework para LLMs
- [Streamlit](https://streamlit.io/) - Apps rápidas de ML

### **🎥 Videos y Tutoriales:**
- [Ollama Official Channel](https://www.youtube.com/@ollama)
- [Local LLM Setup Guides](https://www.youtube.com/results?search_query=ollama+setup)

## 🚀 Próximos Pasos

Después de completar este módulo:

1. **Módulo 4**: Fine-tuning y personalización avanzada
2. **Módulo 5**: Aplicaciones empresariales y casos de uso
3. **Módulo 6**: Optimización y despliegue en producción

## 🤝 Contribuciones

¿Tienes mejoras para el laboratorio?

1. Reporta problemas de instalación
2. Sugiere nuevos ejercicios
3. Comparte casos de uso interesantes
4. Contribuye con optimizaciones

## 📄 Licencia

Este material educativo está disponible bajo licencia MIT. Libre uso para educación y desarrollo.

---

**¡Despliega Llama 3.1 localmente y crea aplicaciones increíbles!** 🦙🚀✨
