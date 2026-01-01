cat > README.md << 'EOF'
# 🤖 Sistema RAG Gestoría Alex

Sistema inteligente de gestión documental con IA para gestorías y asesorías fiscales.

![Python](https://img.shields.io/badge/python-3.9+-blue.svg)
![Streamlit](https://img.shields.io/badge/streamlit-1.28+-red.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)

## ✨ Características

- **Chat Inteligente con IA**: Conversación natural con razonamiento avanzado
- **RAG (Retrieval Augmented Generation)**: Búsqueda semántica en documentos
- **Generación Automática**: Crea documentos TXT y Excel profesionales
- **Multi-modelo IA**: Llama 3.2 (rápido) y Qwen 2.5 (preciso)
- **Procesamiento Robusto**: PDF y Excel con múltiples métodos de extracción
- **Portal de Clientes**: Interfaz independiente para acceso de clientes
- **Biblioteca Inteligente**: Gestión completa de documentos procesados

## 📋 Requisitos Previos

- Python 3.9 o superior
- [Ollama](https://ollama.ai/) instalado
- 8GB RAM mínimo (16GB recomendado)
- macOS, Linux o Windows (WSL)

## 🚀 Instalación

### 1. Clonar el repositorio
```bash
git clone https://github.com/TU_USUARIO/rag-gestoria.git
cd rag-gestoria
```

### 2. Crear entorno virtual
```bash
python3 -m venv venv
source venv/bin/activate  # En Windows: venv\Scripts\activate
```

### 3. Instalar dependencias
```bash
pip install -r requirements.txt --break-system-packages
```

### 4. Instalar modelos de IA
```bash
# Asegúrate de tener Ollama instalado
ollama pull llama3.2
ollama pull qwen2.5:14b
ollama pull nomic-embed-text
```

### 5. Dar permisos a scripts (macOS/Linux)
```bash
chmod +x *.sh
```

## 💻 Uso

### Iniciar el Sistema
```bash
# Activar entorno virtual
source venv/bin/activate

# Iniciar panel de administración
streamlit run app_admin.py --server.address 0.0.0.0 --server.port 8501
```

### Acceso

- **Panel Admin**: http://localhost:8501
- **Portal Clientes**: http://localhost:8502 (si ejecutas `dashboard_cliente.py`)

## 📚 Capacidades del Chat

### Consultar Documentos
```
"¿Qué documentos tiene Juan?"
"Busca información sobre IVA en todos los archivos"
"Analiza el contrato de María"
```

### Generar Documentos TXT
```
"Genera un informe fiscal de Juan"
"Crea una carta formal para el cliente"
"Redacta un resumen ejecutivo"
```

### Generar Excel
```
"Genera un Excel con todos los clientes y sus documentos"
"Crea una tabla comparativa de facturas"
"Exporta los datos a formato Excel"
```

### Conocimiento General
```
"¿Cómo se calcula el IRPF?"
"¿Cuándo se presenta el modelo 347?"
"Explícame las deducciones fiscales para autónomos"
```

## 📁 Estructura del Proyecto
```
rag-gestoria/
├── app_admin.py              # Interfaz principal de administración
├── procesador_hibrido.py     # Motor RAG y procesamiento
├── dashboard_cliente.py      # Portal para clientes
├── documentos/
│   ├── entrada/              # Documentos a procesar
│   ├── procesados/           # Documentos procesados
│   ├── resumenes/            # Resúmenes generados
│   └── generados/            # TXT y Excel generados
├── chroma_db/                # Base de datos vectorial
├── documentacion/            # Documentación del proyecto
├── requirements.txt          # Dependencias Python
└── README.md                 # Este archivo
```

## 🛠️ Tecnologías

- **Frontend**: [Streamlit](https://streamlit.io/)
- **IA/LLM**: [Ollama](https://ollama.ai/) (Llama 3.2, Qwen 2.5)
- **Embeddings**: nomic-embed-text
- **Vector DB**: [ChromaDB](https://www.trychroma.com/)
- **PDF Processing**: PyPDF2, pdfplumber, PyMuPDF
- **Data**: Pandas, OpenPyXL
- **Visualización**: Plotly

## 🔧 Configuración

### Cambiar Puerto

Edita los scripts o usa:
```bash
streamlit run app_admin.py --server.port 8080
```

### Modelos de IA

Por defecto usa:
- **Llama 3.2**: Consultas rápidas
- **Qwen 2.5 14B**: Análisis complejos

Para cambiar modelos, edita las constantes en `procesador_hibrido.py`:
```python
MODELO_RAPIDO = "llama3.2"
MODELO_CALIDAD = "qwen2.5:14b"
```

## 📊 Características Técnicas

- **Chunking**: 700 palabras, 150 overlap
- **Búsqueda**: Top-k semántica con ChromaDB
- **Generación**: Razonamiento en 3 pasos
- **Formatos soportados**: PDF, XLSX, XLS
- **Salida**: TXT, XLSX con formato profesional

## 🐛 Solución de Problemas

### Error: Puerto ocupado
```bash
pkill -f streamlit
```

### Error: Modelos no encontrados
```bash
ollama list
ollama pull llama3.2
ollama pull qwen2.5:14b
```

### Error: Permisos en macOS
```bash
chmod +x *.sh
```

## 📝 Roadmap

- [ ] Autenticación de usuarios
- [ ] Roles y permisos
- [ ] Integración con APIs externas (AEAT)
- [ ] OCR avanzado
- [ ] Exportación a Word/PDF
- [ ] Notificaciones automáticas
- [ ] Firma digital de documentos

## 🤝 Contribuir

Las contribuciones son bienvenidas! Por favor:

1. Fork el proyecto
2. Crea tu rama (`git checkout -b feature/AmazingFeature`)
3. Commit tus cambios (`git commit -m 'Add some AmazingFeature'`)
4. Push a la rama (`git push origin feature/AmazingFeature`)
5. Abre un Pull Request

## 📄 Licencia

Este proyecto está bajo la Licencia MIT. Ver `LICENSE` para más detalles.

## 👤 Autor

**Alex** - @alete.c

## 🙏 Agradecimientos

- [Ollama](https://ollama.ai/) por los modelos de IA locales
- [Streamlit](https://streamlit.io/) por el framework
- [ChromaDB](https://www.trychroma.com/) por la base de datos vectorial

---

⭐ Si este proyecto te fue útil, ¡dale una estrella en GitHub!
EOF
