# Todo List App - Full Stack

Una aplicación completa de lista de tareas construida con React + Vite en el frontend y Express.js en el backend.

## Descripción del Proyecto

Esta es una aplicación de gestión de tareas que permite a los usuarios crear, editar, eliminar y marcar tareas como completadas. La aplicación sigue una arquitectura moderna con frontend y backend separados, desplegados en diferentes plataformas de hosting.

## Stack Tecnológico

**Frontend:** 
- React 18
- Vite
- ESLint
- CSS Modules

**Backend:**
- Express.js
- CORS
- Nodemon (desarrollo)

**Despliegue:**
- Frontend: Vercel
- Backend: Render
- Base de datos: Railway (PostgreSQL)

## Requisitos Previos

- Node.js (versión 18 o superior)
- npm (versión 9 o superior)
- Git

## Cómo Ejecutar en Local

### 1. Clonar el repositorio
```bash
git clone https://github.com/leorodrivi/Todo_List_App.git
cd Todo_List_App
```

### 2. Configurar Variables de Entorno

**Backend (.env.example):**
```env
PORT=3001
DATABASE_URL=postgresql://usuario:contraseña@localhost:5432/todo_db
NODE_ENV=development
```

**Frontend (.env.example):**
```env
VITE_API_URL=http://localhost:3001/api
```

Copia los archivos `.env.example` a `.env` y ajusta los valores según tu configuración local.

### 3. Ejecutar el Backend
```bash
cd backend
npm install
npm run dev
```
Servidor disponible en: `http://localhost:3001`

### 4. Ejecutar el Frontend
```bash
cd frontend
npm install
npm run dev
```
Aplicación disponible en: `http://localhost:5173`

## Enlaces de Producción

- **Repositorio:** https://github.com/leorodrivi/Todo_List_App
- **Frontend (Vercel):** https://leorodrivi.github.io/Todo_List_App/
- **Backend (Render):** https://todo-list-backend.onrender.com
- **Base de Datos (Railway):** https://railway.app/

## Documentación

### Arquitectura del Sistema

Consulta el documento de arquitectura completo en [ARQUITECTURA.md](./ARQUITECTURA.md) que incluye:

**Diagrama de Arquitectura (C4 Nivel 2):**
```
Usuario → Frontend (Vercel) → Backend (Render) → Base de Datos (Railway PostgreSQL)
```

**Componentes:**
- **Frontend:** Aplicación React con pantallas principales (Lista de Tareas, Formulario de Edición)
- **Backend:** API REST con capas (Rutas, Controladores, Servicios)
- **Base de Datos:** Modelo de datos con tabla `tareas` (id, texto, completada, fecha_creacion)

### Documentación de API

Consulta la documentación completa de la API en [API.md](./API.md) que incluye:

**Endpoints disponibles:**
| Método | Endpoint | Descripción |
|--------|----------|-------------|
| `GET` | `/api/tareas` | Obtener todas las tareas |
| `POST` | `/api/tareas` | Crear nueva tarea |
| `PUT` | `/api/tareas/:id` | Actualizar tarea |
| `DELETE` | `/api/tareas/:id` | Eliminar tarea |

**Ejemplo de petición:**
```bash
curl -X POST https://todo-list-backend.onrender.com/api/tareas \
  -H "Content-Type: application/json" \
  -d '{"texto": "Mi nueva tarea", "completada": false}'
```

**Respuestas de ejemplo y códigos de estado HTTP documentados.**

## Estructura del Repositorio

```
Todo_List_App/
├── frontend/           # Aplicación React
│   ├── src/
│   │   ├── components/ # Componentes React
│   │   ├── App.jsx     # Componente principal
│   │   └── main.jsx    # Punto de entrada
│   ├── package.json
│   └── vite.config.js
├── backend/            # API Express
│   ├── src/
│   │   ├── routes/     # Rutas de la API
│   │   ├── controllers/# Controladores
│   │   └── services/   # Lógica de negocio
│   ├── package.json
│   └── server.js
├── ARQUITECTURA.md     # Documentación de arquitectura
├── API.md              # Documentación de la API
├── README.md           # Este archivo
└── .gitignore
```

## Scripts Principales

**Backend:**
```bash
npm start        # Modo producción
npm run dev      # Desarrollo con recarga automática
```

**Frontend:**
```bash
npm run dev      # Servidor de desarrollo
npm run build    # Build para producción
npm run preview  # Vista previa del build
npm run lint     # Verificación de código
```

## Notas Importantes

- Para desarrollo local, asegúrate de que ambos servidores (frontend y backend) estén corriendo
- En producción, el frontend se conecta automáticamente al backend desplegado
- La base de datos en producción es PostgreSQL en Railway
- El backend está configurado con CORS para permitir peticiones desde Vercel
