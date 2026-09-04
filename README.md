# BotE-Commerce

**BotE-Commerce** es un sistema de comercio electrónico desarrollado en **Python** que integra un **Bot de Telegram**, una **API REST con FastAPI** y una base de datos **PostgreSQL**. El proyecto permite gestionar productos y pedidos mediante servicios web, mientras el bot interactúa con los usuarios desde Telegram consumiendo la API de forma transparente.

---

## Tecnologías utilizadas

- Python 3.10+
- FastAPI
- PostgreSQL
- SQLAlchemy
- python-telegram-bot v21
- Uvicorn
- python-dotenv
- Requests

---

## Arquitectura del proyecto

El proyecto está organizado de la siguiente manera:

```text
BotE-Commerce/
├── api/
│   ├── main.py        # Punto de entrada de la API
│   ├── db.py          # Configuración de la base de datos
│   ├── models.py      # Modelos de datos
│   └── config.py      # Configuración general
│
├── bot/
│   └── bot.py         # Bot de Telegram
│
├── requirements.txt
└── README.md
```

### Descripción de cada componente

- **api:** contiene la API REST desarrollada con FastAPI y toda la lógica relacionada con la base de datos.
- **db.py:** administra la conexión con PostgreSQL mediante SQLAlchemy.
- **models.py:** define las entidades utilizadas por la aplicación.
- **config.py:** centraliza la configuración del proyecto.
- **bot:** implementa el Bot de Telegram encargado de interactuar con los usuarios y consumir la API.

---

## Funcionalidades

El sistema permite:

- Gestión completa de productos.
- Creación y administración de pedidos.
- Integración con Telegram mediante un bot.
- Consumo de una API REST.
- Persistencia de datos en PostgreSQL.

---

## Requisitos

Antes de ejecutar el proyecto asegúrate de tener instalado:

- Python 3.10 o superior
- PostgreSQL
- Git (opcional para clonar el repositorio)
- Un Bot de Telegram creado mediante **BotFather**

---

## Instalación

### 1. Clonar el repositorio

```bash
git clone https://github.com/ricardoJGC11/BotE-Commerce.git
cd BotE-Commerce
```

### 2. Crear un entorno virtual

```bash
python -m venv venv
```

Activar el entorno virtual:

**Windows**

```bash
venv\Scripts\activate
```

**Linux / macOS**

```bash
source venv/bin/activate
```

---

### 3. Instalar las dependencias

```bash
pip install -r requirements.txt
```

---

## Configuración de la base de datos

Crear una base de datos llamada:

```sql
CREATE DATABASE chatbotdb;
```

---

## Variables de entorno

Crear un archivo `.env` en la raíz del proyecto con la siguiente información:

```env
TELEGRAM_TOKEN=TU_TOKEN_DEL_BOT
API_URL=http://127.0.0.1:8000
DATABASE_URL=postgresql://usuario:password@localhost:5432/chatbotdb
```

> **Importante:** No subas el archivo `.env` al repositorio, ya que contiene información sensible.

---

## Ejecución

### 1. Iniciar la API

```bash
uvicorn api.main:app --reload
```

La API estará disponible en:

```text
http://127.0.0.1:8000
```

---

### 2. Ejecutar el Bot

```bash
python bot/bot.py
```

El bot se conectará automáticamente a Telegram utilizando el token configurado en el archivo `.env`.

---

## Endpoints principales

### Productos

| Método | Endpoint | Descripción |
|---------|----------|-------------|
| GET | `/productos` | Obtener todos los productos |
| GET | `/productos/{id}` | Obtener un producto por ID |
| POST | `/productos` | Crear un producto |
| PUT | `/productos/{id}` | Actualizar un producto |
| DELETE | `/productos/{id}` | Eliminar un producto |

### Pedidos

| Método | Endpoint | Descripción |
|---------|----------|-------------|
| POST | `/pedidos` | Crear un nuevo pedido |
| GET | `/pedidos/usuario/{id}` | Obtener pedidos de un usuario |
| PUT | `/pedidos/{id}/cancelar` | Cancelar un pedido |

---

## Características

- API REST desarrollada con FastAPI.
- Integración con Bot de Telegram.
- Arquitectura modular.
- Persistencia de datos mediante PostgreSQL y SQLAlchemy.
- Configuración mediante variables de entorno.
- CRUD completo para productos.
- Gestión de pedidos.
- Comunicación entre el bot y la API en tiempo real.

---

## Autor

**Ricardo JGC**

GitHub: https://github.com/ricardoJGC11
