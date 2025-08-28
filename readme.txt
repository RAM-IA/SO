1 Objetivo General

Propósito: Capturar requerimientos y compras de materiales en obra, tomar fotos de avances y notificar a supervisores para autorización.
Problema que resuelve: Evita errores y retrasos en la comunicación entre campo y oficina, centraliza la información y sincroniza con SQL Server.

Usuarios:
Personal en campo (solicita materiales y captura avances).
Supervisores (autorizan compras).
Oficina (sincroniza catálogos de obras y materiales).
Administrador (gestión de usuarios).

2 Funcionalidades Principales

Esenciales:
Captura de pedidos y requerimientos de materiales.
Autorización de compras por supervisores.
Registro fotográfico de avances de obra.
Sincronización con SQL Server.

Deseables:
Generación de reportes en PDF.
Exportación a Excel.
Filtros avanzados por obra, material, fecha, solicitante.

Requisitos operativos:
Funcionamiento offline con sincronización cuando haya conexión.
Notificaciones push para supervisores.

3 Estructura y Navegación

Flujo de usuario: Login → Menú principal → Captura de materiales → Envío de solicitud → Supervisor autoriza → Oficina sincroniza.
Diseño de navegación: Menú principal con accesos directos, compatible con web y app móvil.
Roles de usuario: Campo, Supervisor, Oficina, Administrador.

4 Datos y Almacenamiento

Datos de usuario: Nombre, contraseña, rol.

Requisiciones:
General: Folio, fechas, áreas, partidas, subpartidas, concepto, observaciones, archivos, status, usuarios involucrados.
Detalle: Id_Mat, Material, Cantidad, Observaciones.

Compras: General y Detalle (mismo esquema que requisiciones + Precio).

Catálogos internos: Materiales, Áreas, Partidas, Subpartidas, Conceptos, Usu_Are.

Almacenamiento: Híbrido (SQLite local + sincronización con SQL Server).

Sensibilidad de la información: Solo datos operativos.

Sincronización con base de datos local: Solo cuando haya conexión.


5 Plataformas y Dispositivos

Disponibilidad: Android, iOS, Web, Windows, Mac y tablets.

Modo de uso:

Celular: app instalada.

Web/Escritorio: navegador.

Limitaciones de hardware: Ninguna.


6 Lenguajes y Tecnologías

Frontend: Flutter

Backend: Python (Django/FastAPI) o Node.js (Express)

Base de datos local: SQLite

Integraciones externas: Notificaciones push

IA en desarrollo: GitHub Copilot


Paquetes recomendados en VS Code

Flutter:
flutter_local_notifications
firebase_messaging
sqflite
path_provider
http
provider / riverpod
image_picker
file_picker
flutter_web_plugins

Python:
fastapi / django
sqlalchemy
pyodbc
uvicorn
pydantic
python-dotenv

Node.js:
express
mssql
sequelize
dotenv
cors

Extensiones VS Code: Flutter/Dart, Python/Node.js, SQLite Viewer, REST Client, GitHub Copilot


7 Diseño UX/UI

Estilo: Corporativo
Tema: Claro y oscuro
Accesibilidad: No requerida
Adaptable: Mismo diseño para todos los dispositivos


8 Seguridad

Autenticación: Sí, correo y contraseña
Cifrado: No necesario
Normativas: Solo protección interna de datos


9 Escalabilidad y Mantenimiento

Usuarios esperados: 10–20 primer año
Mantenimiento: Tú mismo
Futuras mejoras: Fácil incorporación de nuevas funciones


Prompts sugeridos para IA (Copilot o ChatGPT)

“Genera la estructura de tablas SQLite para requisiciones y compras según el modelo dado.”
“Crea el flujo de login con roles de usuario (Campo, Supervisor, Oficina, Administrador) en Flutter.”
“Genera código en Flutter para captura de fotos y almacenamiento local en SQLite.”
“Implementa notificaciones push para solicitudes pendientes de autorización.”
“Escribe API en Python/FastAPI para sincronizar datos de SQLite local con SQL Server.”
“Crea formularios adaptables en Flutter para web y app móvil con diseño corporativo.”
“Genera funciones para exportar datos a PDF y Excel desde Flutter.”
“Añade validación de permisos por rol de usuario en Flutter y backend.”
“Optimiza el flujo de sincronización offline → SQL Server cuando haya conexión.”
“Recomienda estructura de proyecto escalable en Flutter con backend Python/Node.js.”