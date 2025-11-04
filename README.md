# 🚀 FastAPI CI/CD Example

This project showcases a complete CI/CD pipeline for a FastAPI application, integrating the following features:

- ✅ Pre-commit hooks
- ✅ Unit testing with pytest
- ✅ Docker build
- ✅ Docker push to Docker Hub

---

## 🚀 Inicio Rápido

### 1. Clonar el repositorio

```bash
git clone https://github.com/CloudComputingUAO/fastapi-ci-cd-example.git
cd fastapi-ci-cd-example
```

### 2. Configurar entorno virtual

```bash
# Crear entorno virtual
python -m venv venv

# Activar entorno virtual
# En Windows:
venv\Scripts\activate
# En macOS/Linux:
source venv/bin/activate
```

### 3. Instalar dependencias

```bash
pip install -r requirements.txt
```

### 4. Configurar Pre-commit (Opcional pero recomendado)

```bash
pip install pre-commit
pre-commit install
```

### 5. Ejecutar la aplicación localmente

```bash
uvicorn app.main:app --reload
```

La aplicación estará disponible en: http://localhost:8000

### 6. Ejecutar pruebas

```bash
pytest
```

---

## 🌐 Endpoints Disponibles

La API incluye los siguientes endpoints:

| Método | Endpoint | Descripción | Respuesta |
|--------|----------|-------------|-----------|
| GET | `/` | Endpoint principal | `{"message": "Hello CI/CD"}` |
| GET | `/hello` | Saludo simple | `{"message": "Hello world"}` |
| GET | `/docs` | Documentación interactiva (Swagger) | Interfaz Swagger UI |
| GET | `/redoc` | Documentación alternativa | Interfaz ReDoc |

### Ejemplos de uso:

```bash
# Endpoint principal
curl http://localhost:8000/

# Endpoint de saludo
curl http://localhost:8000/hello

# Documentación interactiva
# Visita: http://localhost:8000/docs
```

---

## 🐳 Docker

### Construir imagen Docker

```bash
docker build -t tu-usuario/fastapi-ci-cd .
```

### Ejecutar contenedor

```bash
docker run -p 8000:8000 tu-usuario/fastapi-ci-cd
```

### Probar la aplicación en Docker

```bash
# La aplicación estará disponible en http://localhost:8000
curl http://localhost:8000/
```

---

## 🤖 GitHub Actions CI/CD

### Configuración de Secrets

Para que el pipeline funcione correctamente, necesitas configurar los siguientes secrets en tu repositorio de GitHub:

1. Ve a tu repositorio en GitHub
2. Navega a **Settings** > **Secrets and variables** > **Actions**
3. Agrega los siguientes secrets:

| Secret | Descripción | Ejemplo |
|--------|-------------|---------|
| `DOCKER_USERNAME` | Tu nombre de usuario de Docker Hub | `miusuario` |
| `DOCKER_PASSWORD` | Tu contraseña o token de Docker Hub | `dckr_pat_xxxxx` |

### ¿Qué hace el Pipeline?

El pipeline CI/CD se ejecuta automáticamente en cada:
- **Push** a la rama `main`
- **Pull Request** hacia la rama `main`

**Pasos del pipeline:**

1. ✅ **Checkout del código** - Descarga el código fuente
2. ✅ **Configuración de Python** - Instala Python 3.10
3. ✅ **Instalación de dependencias** - Instala requirements.txt
4. ✅ **Ejecución de pruebas** - Ejecuta pytest
5. ✅ **Construcción de imagen Docker** - Crea la imagen del contenedor
6. ✅ **Login a Docker Hub** - Se autentica con Docker Hub
7. ✅ **Push de imagen** - Sube la imagen a Docker Hub

---

## 🧪 Desarrollo y Pruebas

### Ejecutar pre-commit manualmente

```bash
pre-commit run --all-files
```

### Ejecutar pruebas con cobertura

```bash
pytest --cov=app tests/
```

### Agregar nuevos endpoints

1. Edita `app/main.py` para agregar nuevos endpoints
2. Agrega pruebas correspondientes en `tests/test_main.py`
3. Ejecuta las pruebas para verificar funcionamiento
4. Haz commit de los cambios (pre-commit se ejecutará automáticamente)

---

## 📝 Entregables del Proyecto

### Tareas Principales:

1. **✅ Completado:** Aplicación FastAPI básica con endpoints
2. **✅ Completado:** Pruebas unitarias para todos los endpoints
3. **🔄 Pendiente:** Agregar un nuevo endpoint personalizado
4. **🔄 Pendiente:** Implementar pruebas para el nuevo endpoint

### Tarea Extra (Punto Adicional):

- **🎯 Desafío:** Investigar y desplegar la aplicación en:
  - [Render.com](https://render.com/)
  - [Fly.io](https://fly.io/)
  - Documentar el proceso de despliegue

---

## 🛠️ Solución de Problemas

### Error: "Module not found"
```bash
# Asegúrate de estar en el entorno virtual
pip install -r requirements.txt
```

### Error en Docker build
```bash
# Verifica que Docker esté ejecutándose
docker --version
```

### Fallos en pre-commit
```bash
# Reinstala los hooks
pre-commit uninstall
pre-commit install
```

---

## 🤝 Contribuir

1. Fork el proyecto
2. Crea una rama para tu feature (`git checkout -b feature/nueva-funcionalidad`)
3. Commit tus cambios (`git commit -m 'Agregar nueva funcionalidad'`)
4. Push a la rama (`git push origin feature/nueva-funcionalidad`)
5. Abre un Pull Request

---

## 📚 Recursos Adicionales

- [Documentación FastAPI](https://fastapi.tiangolo.com/)
- [Guía Docker](https://docs.docker.com/)
- [GitHub Actions](https://docs.github.com/en/actions)
- [Pre-commit Hooks](https://pre-commit.com/)
- [Pytest Documentation](https://docs.pytest.org/)

---

## 👨‍🏫 Créditos

**Profesor:** Heberth Martinez
**Curso:** Cloud Computing - UAO

---

## 📄 Licencia

Este proyecto está bajo la Licencia MIT. Ver el archivo `LICENSE` para más detalles.
