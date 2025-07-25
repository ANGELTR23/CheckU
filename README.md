# 📲 Check-U — Sistema Inteligente de Registro de Asistencias con Códigos QR

Check-U es una plataforma web desarrollada para modernizar el pase de lista en instituciones educativas (secundarias, preparatorias y universidades). El sistema permite a los estudiantes registrar su asistencia escaneando un código QR desde la cámara de su dispositivo móvil, sin necesidad de instalar aplicaciones adicionales. Todo el registro se guarda automáticamente en una base de datos y puede ser consultado por docentes o administradores desde un panel web.

---

## 🎯 Objetivos del Proyecto

- Automatizar el pase de lista con tecnología accesible.
- Reducir el uso de papel y errores humanos.
- Validar asistencia en tiempo real mediante códigos QR únicos.
- Ofrecer un sistema responsivo, accesible y seguro.
- Facilitar reportes clasificados y descargables.

---

## 🌐 Tecnologías Utilizadas

| Categoría         | Herramienta / Librería                         |
|-------------------|------------------------------------------------|
| Frontend          | HTML, CSS (Tailwind), JavaScript              |
| Backend           | Node.js, Express.js                           |
| Base de Datos     | MongoDB (preferido) / MySQL                   |
| Escáner QR        | `html5-qrcode`                                |
| Generador QR      | `qrcode`, `qrcode-generator`                  |
| Reportes PDF/Excel| `jsPDF`, `xlsx`, `pdfkit`                     |
| Gráficas          | `Chart.js`                                    |
| Autenticación     | JWT / Sessions + middleware personalizado     |

---

## 📁 Estructura del Proyecto

```

checku/
├── public/
│   ├── index.html              # Página de escaneo QR
│   ├── login.html              # Acceso admin/docente
│   ├── dashboard.html          # Panel de control
│   ├── qr-display.html         # QR personal de usuario
│   ├── users.html              # Gestión de usuarios
│   ├── reports.html            # Visualización de asistencias
│   ├── css/
│   │   └── styles.css          # Estilo global (fondo, botones, etc.)
│   ├── js/
│   │   ├── scan.js             # Escaneo QR con cámara
│   │   ├── dashboard.js        # Funcionalidad del panel
│   │   ├── auth.js             # Validación de inicio de sesión
│   │   ├── qr-generator.js     # Generación de códigos QR
│   │   ├── reports.js
│   │   └── utils.js
│   └── assets/
│       ├── logo.png            # Logotipo Check-U
│       ├── fondo.jpg           # Imagen de fondo oscuro con luces
│       ├── icono\_qr.png        # Ícono QR decorativo
│       ├── user-avatar.png     # Avatar por defecto
│       └── qr-codes/           # Almacenamiento temporal QR
│
├── server/
│   ├── app.js
│   ├── server.js
│   ├── routes/
│   ├── controllers/
│   ├── middleware/
│   ├── models/
│   ├── utils/
│   └── db/
│
├── config/
│   ├── config.js
│   ├── database.js
│   └── jwt.js
├── uploads/
│   └── temp/
├── docs/
│   ├── API.md
│   ├── INSTALL.md
│   └── USER\_MANUAL.md
├── tests/
│   ├── auth.test.js
│   └── attendance.test.js
├── .env
├── package.json
└── README.md

```

---

## 🔐 Estructura del Código QR

Cada código QR generado contiene una firma única y encriptada con el formato:

```

nombre\_usuario|matricula|firma\_digital

```

Ejemplo:
```

Angel Tovar|123456|8ab87e99127dd...

````

Esto asegura que los códigos generados solo sean válidos dentro del sistema y no se puedan falsificar. La firma se genera mediante un algoritmo hash interno (`HMAC`, `SHA256`, etc.) con clave secreta.

---

## 🔧 Instalación del Proyecto

### 1. Clonar el repositorio
```bash
git clone https://github.com/tu-usuario/checku.git
cd checku
````

### 2. Instalar dependencias del backend

```bash
cd server
npm install
```

### 3. Configurar variables de entorno `.env`

Ejemplo:

```env
PORT=3000
MONGO_URI=mongodb://localhost:27017/checku
JWT_SECRET=clave_secreta_segura
```

### 4. Ejecutar el servidor

```bash
npm start
```

### 5. Ejecutar frontend (HTML estático)

Solo abre `public/index.html` en el navegador o sirve la carpeta con `Live Server` desde VS Code.

---

## 🧪 Pruebas

Las pruebas están ubicadas en la carpeta `/tests/`. Se ejecutan con Jest, Mocha o el framework de tu elección.

```bash
npm test
```

---

## 📊 Funcionalidades por Usuario

| Rol           | Funciones principales                                            |
| ------------- | ---------------------------------------------------------------- |
| Alumno        | Escanear QR, consultar su historial personal                     |
| Docente       | Ver asistencias por grupo, consultar fechas, generar reportes    |
| Administrador | Crear usuarios, generar QR, modificar registros, descargar datos |

---

## 🌍 Futuras Mejoras

* Notificaciones automáticas a padres de familia.
* Control por horarios de clase.
* Escaneo sin conexión (con buffer y sincronización).
* Modo kiosko en tablets o tótems.

---

## 🤝 Equipo de Desarrollo

* **Emmanuel Torres Espinoza** – Coordinador general, diseño e interfaz
* **Ángel Guadalupe Tóvar Andrade** – Generador y lógica QR
* **Luis Ángel Sánchez Pérez** – Base de datos y sincronización
* **Alma Delia Hernández Hernández** – Presentación y documentación
* **José Manuel Lucas Cortés, Miguel Ángel Vázquez García** – Reportes y pruebas
* **Tutora:** Mtra. Esmeralda Guadalupe Arrieta Morales

---

## 🔖 Licencia

Este proyecto está bajo la Licencia MIT. Libre para usar, modificar y distribuir.

---

## 📌 Frase de Impacto

> *Check-U no es solo un pase de lista digital, es una herramienta de control, seguridad y transparencia para las escuelas del futuro.*

```
