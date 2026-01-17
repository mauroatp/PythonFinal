# 🏎️ Sistema de Gestión Automotora Pro v1.0

Este proyecto es una solución integral para la administración de concesionarias, desarrollada con **Django 6.0**. Permite gestionar inventarios de vehículos, sedes operativas (automotoras) y personal de ventas, todo bajo un entorno seguro y personalizado.

## 🛠️ Stack Tecnológico
- **Backend:** Python 3.14 / Django 6.0
- **Frontend:** HTML5, CSS3 (Custom Styles), Bootstrap 5.3
- **Base de Datos:** SQLite 3
- **Manejo de Imágenes:** Pillow (Librería de procesamiento de imágenes)
- **Control de Versiones:** Git con reglas estrictas de exclusión

---

## 👥 Módulo de Usuarios y Seguridad (App: `accounts`)
El sistema utiliza un modelo de usuario extendido para enriquecer la experiencia administrativa.

- **Perfiles Personalizados:** Cada usuario cuenta con un perfil que incluye `avatar`, `país`, `fecha de nacimiento` y `dirección`.
- **Gestión de Seguridad:**
    - Registro de nuevos usuarios con carga de archivos (Media).
    - Cambio de contraseña seguro mediante `update_session_auth_hash` (mantiene la sesión activa tras el cambio).
    - Mensajes de éxito (Pop-ups) integrados con el Framework de Mensajes de Django.
- **Acceso Privado:** Uso intensivo de `@login_required` para proteger las operaciones de edición y eliminación.

---

## 🚗 Gestión de Inventario y Sedes (App: `concesionaria`)
Implementación completa de flujos CRUD (Crear, Leer, Actualizar, Borrar) para el core del negocio.

### 🏢 Automotoras (Sedes)
- **Localizador de Sedes:** Buscador inteligente con filtros por nombre (`icontains`).
- **Estados Dinámicos:** Manejo de estados vacíos (`{% empty %}`) con feedback visual cuando no hay coincidencias.
- **Edición y Baja:** Formularios protegidos y confirmación de eliminación para integridad de datos.

### 🚘 Vehículos
- **Catálogo Detallado:** Vista individual de vehículos con especificaciones técnicas y precios.
- **Gestión de Stock:** Alta y modificación de vehículos incluyendo carga de imágenes de catálogo.

---

## 👔 Módulo de Vendedores (App: `vendedores`)
- Registro y visualización del equipo de ventas vinculado a las operaciones.
- Acceso restringido únicamente a personal administrativo autenticado.

---

## 🎨 Interfaz de Usuario (UI/UX)
- **Navbar Inteligente:** Adapta sus opciones según si el usuario es un visitante (Login/Registro) o un administrador (Dashboard completo + Perfil).
- **Sobre Mí (About Me):** Sección dedicada a la información del desarrollador y tecnologías del proyecto.
- **Feedback:** Alertas de Bootstrap 5 para confirmar acciones exitosas o advertir sobre eliminaciones.

---

## 🛠️ Tecnologías Utilizadas

* **Backend:** [Python](https://www.python.org/) & [Django Framework](https://www.djangoproject.com/)
* **Frontend:** [Bootstrap 5](https://getbootstrap.com/) (CSS/JS) & [Bootstrap Icons](https://icons.getbootstrap.com/)
* **Base de Datos:** [SQLite](https://www.sqlite.org/) (Local)

---

## 🚀 Funcionalidades

- **Panel de Control:** Inicio con acceso rápido a todas las áreas.
- **Altas Personalizadas:** Formularios modernos para Automotoras, Vendedores, Autos y Usuarios con mensajes de éxito sin redirección.
- **Buscador de Sedes:** Motor de búsqueda por nombre con visualización en tablas profesionales.
- **Vista de Detalle:** Página específica para consultar la información completa de cada automotora.
- **Diseño Responsive:** Adaptado para su uso en computadoras y dispositivos móviles.

---

## 📂 Estructura del Proyecto

automotora/
├── accounts/        # Usuarios, Perfiles y Login
├── concesionaria/   # Gestión de Vehículos y Sedes (CRUD)
├── vendedores/      # Gestión de Personal
├── media/           # Fotos de Perfil y Autos
├── static/          # CSS y Estilos
├── manage.py        # Comando principal
└── requirements.txt # Librerías (Django, Pillow)

---

## ⚙️ Guía de Instalación (Paso a Paso)

Sigue estas instrucciones para replicar el entorno de desarrollo en tu computadora local:

### 1. Clonar el repositorio
Descarga el código fuente en tu máquina local:
git clone https://github.com/mauroatp/PythonFinal.git

### 2. Configuración del Entorno Virtual

Crea el entorno para aislar las librerías:
python -m venv env

### 3. Activación del Entorno

env\Scripts\activate
Sabrás que está activo porque aparecerá (env) al principio de la línea en tu terminal.

### 4. Instalación de Django

pip install django

### 5. Preparación de la Base de Datos

Genera los archivos necesarios para guardar la información localmente:
python manage.py makemigrations
python manage.py migrate

### 6. Creación de la cuenta de Administrador

Crea un usuario para acceder al panel /admin:
python manage.py createsuperuser
Escribe el nombre de usuario, correo y contraseña (los caracteres no se verán mientras escribes por seguridad).

### 7. Ejecución del Sistema

Inicia el servidor local:
python manage.py runserver
Accede mediante tu navegador a: http://127.0.0.1:8000/

### 8. Video link

https://drive.google.com/file/d/1QSNZHVEqzvOvjRBKktS1oVUDCOJIn9C2/view

