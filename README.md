# gestor-a-web-
Gestion de documentación via IA
cd ~/rag-gestoria-app

# Crear .gitignore para no subir archivos innecesarios
cat > .gitignore << 'EOF'
# Python
venv/
__pycache__/
*.pyc
*.pyo
*.pyd
.Python
*.so
*.egg
*.egg-info/
dist/
build/

# Datos sensibles (no subir documentos de clientes)
documentos/entrada/*
documentos/procesados/*
documentos/generados/*
documentos/resumenes/*

# Mantener estructura de carpetas
!documentos/entrada/.gitkeep
!documentos/procesados/.gitkeep
!documentos/generados/.gitkeep
!documentos/resumenes/.gitkeep

# Base de datos (no subir datos, solo estructura)
chroma_db/

# Logs
*.log
*.log.*
rag-admin.log
rag-gestoria.log
rag-gestoria-error.log

# Sistema
.DS_Store
.env
.vscode/
.idea/

# Backups locales
Backups/
EOF

# Crear archivos .gitkeep para mantener estructura de carpetas
touch documentos/entrada/.gitkeep
touch documentos/procesados/.gitkeep
touch documentos/generados/.gitkeep
touch documentos/resumenes/.gitkeep

cat > requirements.txt << 'EOF'
streamlit>=1.28.0
chromadb>=0.4.0
PyPDF2>=3.0.0
pdfplumber>=0.10.0
PyMuPDF>=1.23.0
pandas>=2.0.0
openpyxl>=3.1.0
plotly>=5.17.0
python-docx>=1.0.0
EOF

