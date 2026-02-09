# Aplicación de Búsqueda y Calificación de Películas

Aplicación web desarrollada con React y Vite que permite buscar películas, ver sus detalles, calificarlas y mantener una lista personalizada de películas vistas con persistencia de datos.

## Descripción del Proyecto

Esta aplicación consume la API de OMDb (Open Movie Database) para proporcionar información detallada sobre películas. Los usuarios pueden buscar películas por título, ver información completa como sinopsis, elenco, director y calificaciones, además de crear su propia lista de películas vistas con calificaciones personales.

## Funcionalidades Principales

### Búsqueda de Películas
- Búsqueda en tiempo real de películas por título
- Validación de entrada mínima de 3 caracteres
- Manejo de estados de carga y errores
- Visualización de resultados con póster, título y año

### Detalles de Películas
- Información completa: sinopsis, elenco, director, género, duración
- Calificación de IMDb
- Sistema de calificación con estrellas interactivo
- Agregar películas a la lista personal

### Lista de Películas Vistas
- Estadísticas automáticas: promedio de calificaciones IMDb y personales
- Tiempo total de visualización
- Eliminación de películas de la lista
- Persistencia de datos con localStorage

## Tecnologías Utilizadas

- **React 18**: Librería principal para la construcción de interfaces
- **Vite**: Herramienta de construcción y desarrollo
- **OMDb API**: Fuente de datos de películas
- **localStorage**: Persistencia de datos del lado del cliente

## Hooks Personalizados

### useFetchMovies
Hook personalizado para gestionar la búsqueda de películas.

**Responsabilidades:**
- Realizar peticiones a la API de OMDb con el término de búsqueda
- Gestionar estados de carga, errores y resultados
- Validar longitud mínima de búsqueda
- Actualizar automáticamente cuando cambia el término de búsqueda

**Estados:**
- `movies`: Array de películas encontradas
- `isLoading`: Indicador de carga
- `error`: Mensajes de error

### useFetchMovieDetails
Hook personalizado para obtener información detallada de una película específica.

**Responsabilidades:**
- Realizar peticiones a la API con el ID de IMDb
- Gestionar estados de carga y errores
- Limpiar estado cuando no hay película seleccionada
- Actualizar automáticamente cuando cambia la película seleccionada

**Estados:**
- `movie`: Objeto con detalles completos de la película
- `isLoading`: Indicador de carga
- `error`: Mensajes de error

## Estructura de Componentes

### Persistencia
Se utiliza localStorage para mantener la lista de películas vistas entre sesiones:
- Carga automática al iniciar la aplicación
- Guardado automático al agregar o eliminar películas
- Sincronización reactiva con el estado de React

## API Utilizada

**OMDb API** (Open Movie Database)

Endpoints utilizados:
- Búsqueda por título: `/?apikey=KEY&s=QUERY`
- Detalles por ID: `/?apikey=KEY&i=IMDB_ID`

La API proporciona información como título, año, género, director, elenco, sinopsis, calificaciones y pósters de películas.

## Instalación y Uso

### Requisitos Previos
- Node.js 18 o superior
- npm o yarn

### Instalación

```bash
# Clonar el repositorio
git clone https://github.com/Jhonnattan7/practica3-watched-movies-app-list.git

# Entrar al directorio
cd practica3-watched-movies-app-list

# Instalar dependencias
npm install
```

### Desarrollo

```bash
# Iniciar servidor de desarrollo
npm run dev
```

La aplicación estará disponible en `http://localhost:5173`

### Producción

```bash
# Generar build de producción
npm run build

# Previsualizar build
npm run preview
```

## Estructura del Proyecto

```
src/
├── components/
│   ├── Box.jsx
│   ├── Movie.jsx
│   ├── MovieDetails.jsx
│   ├── Nav.jsx
│   ├── StarRating.jsx
│   └── WatchedMovie.jsx
├── hooks/
│   ├── useFetchMovies.js
│   └── useFetchMovieDetails.js
├── App.jsx
├── main.jsx
└── index.css
```

## Funcionalidades Implementadas

- Búsqueda de películas en tiempo real
- Visualización de detalles completos
- Sistema de calificación interactivo
- Lista personalizada de películas vistas
- Estadísticas automáticas
- Eliminación de películas de la lista
- Persistencia de datos con localStorage
- Manejo de estados de carga y errores
- Interfaz responsive

## Autor

Jhonnatan - Desarrollo Web II

# React + Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react) uses [Babel](https://babeljs.io/) (or [oxc](https://oxc.rs) when used in [rolldown-vite](https://vite.dev/guide/rolldown)) for Fast Refresh
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh

## React Compiler

The React Compiler is not enabled on this template because of its impact on dev & build performances. To add it, see [this documentation](https://react.dev/learn/react-compiler/installation).

## Expanding the ESLint configuration

If you are developing a production application, we recommend using TypeScript with type-aware lint rules enabled. Check out the [TS template](https://github.com/vitejs/vite/tree/main/packages/create-vite/template-react-ts) for information on how to integrate TypeScript and [`typescript-eslint`](https://typescript-eslint.io) in your project.
