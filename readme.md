
# 🚀 Proyecto WordPress en Docker

¡Bienvenido al entorno de desarrollo local! Este proyecto utiliza **Docker Compose** para desplegar WordPress con MariaDB en un contenedor aislado, optimizado para trabajar en equipo mediante Git sin problemas de permisos ni bloqueos en Windows.

---

## 🛠️ Requisitos Previos

Antes de empezar, asegúrate de tener instalado en tu máquina:
* [Docker Desktop](https://www.docker.com/products/docker-desktop/) (con Docker Compose)
* [Git](https://git-scm.com/)

---

## 🚀 Inicio Rápido

Sigue estos pasos para poner a correr el entorno local en tu máquina:

1. **Clonar el repositorio:**
   ```bash
   git clone [https://github.com/LSPlaura/TU_REPOSITO.git](https://github.com/LSPlaura/TU_REPOSITO.git)
   cd TU_REPOSITO

```

2. **Levantar los contenedores:**
```bash
docker compose up -d

```


3. **Acceder a la aplicación:**
* 🌐 **WordPress:** [http://localhost:8080](http://localhost:8080)



---

## 🔐 Credenciales del Proyecto

> ⚠️ **Nota:** Guardar credenciales en el archivo `README` es útil para desarrollo local/clase, pero evita subirlas en entornos de producción.

| Servicio / Rol | Usuario / Email | Contraseña |
| --- | --- | --- |
| **Email Proyecto** | `arv23eg8@gmail.com` | `9D!z@fwdrfMY%@8qVz` |
| **Usuario GitHub** | `LSPlaura` | — |
| **Admin WordPress** | *(Configurado en el 1er inicio)* | *(Configurado en el 1er inicio)* |

---

## 💻 Flujo de Trabajo en Equipo (Git)

Para colaborar en este proyecto sin pisar el trabajo del compañero:

### 📄 Lo que se sincroniza por Git

Únicamente se sube la carpeta **`wp-content/`** (temas, plugins personalizados, estilos CSS, etc.) y el archivo `docker-compose.yml`. El código fuente base de WordPress y la base de datos están aislados dentro de los volúmenes de Docker para evitar errores.

### 🔄 Comandos diarios

* **Antes de empezar a trabajar (traer cambios del equipo):**
```bash
git pull origin main

```


* **Guardar y subir tus cambios (código de temas o plugins):**
```bash
git add wp-content/
git commit -m "feat: añade nuevo diseño al header"
git push origin main

```



---

## ⚙️ Comandos Útiles de Docker

### 🔄 Reiniciar el contenedor desde cero

Si necesitas destruir el contenedor y volver a levantarlo manteniendo tus cambios locales en `wp-content/`:

```bash
docker compose down && docker compose up -d

```

### 🧹 Destrucción total (Limpieza completa + BD)

Si quieres borrar los contenedores **y también los volúmenes internos** (limpia la base de datos para empezar de 0):

```bash
docker compose down -v

```

### 📋 Ver estado y logs

* Ver el estado de los contenedores:
```bash
docker compose ps

```


* Ver los errores o actividad de WordPress en tiempo real:
```bash
docker compose logs -f wordpress

```



---

## 📁 Estructura del Repositorio

```text
├── .gitignore
├── docker-compose.yml
├── README.md
└── wp-content/          <-- 📌 TODO tu trabajo (temas/plugins) va aquí
    ├── plugins/
    └── themes/

```
