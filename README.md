# 🗄️ Symphytum - Personal Database Desktop App

[![GitHub Stars](https://img.shields.io/github/stars/giowck/symphytum?style=flat-square&logo=github)](https://github.com/giowck/symphytum)
[![GitHub Release](https://img.shields.io/github/v/release/giowck/symphytum?style=flat-square&logo=github)](https://github.com/giowck/symphytum/releases)
[![License](https://img.shields.io/github/license/giowck/symphytum?style=flat-square)](https://github.com/giowck/symphytum/blob/master/LICENSE)
[![Platform](https://img.shields.io/badge/platform-Windows%20%7C%20macOS%20%7C%20Linux-lightgrey?style=flat-square)](https://github.com/giowck/symphytum/releases)

## 📋 Descripción general

**Symphytum** es un software de base de datos personal multiplataforma (Windows, macOS, Linux) escrito en **C++ y Qt** que permite diseñar y gestionar bases de datos visuales e intuitivas **sin necesidad de SQL**. Incluye editor de formularios drag-and-drop, dos vistas (Formulario para entrada estructurada, Tabla para búsqueda/ordenación), sincronización cloud automática (Dropbox, MEGA), backend SQLite embebido, campos personalizables, recordatorios, búsqueda en tiempo real, backup y exportación CSV. Todo bajo tu control, sin dependencias de servicios cloud obligatorios.

> ⚠️ **Nota importante**: Symphytum es una **aplicación de escritorio (GUI)**, NO una aplicación web ni contenedor Docker. El repositorio fue archivado en octubre 2020 y ya no recibe actualizaciones activas (última versión estable v2.6, febrero 2020).

## ✨ Características principales

- **Editor visual drag-and-drop**: Diseña formularios sin escribir código, reorganiza campos dinámicamente
- **Dos vistas sincronizadas**: 
  - *Form View*: Entrada estructurada campo a campo
  - *Table View*: Búsqueda mientras escribes, ordenación por columnas, comparación de registros
- **Tipos de campo ricos**: Texto, Numérico, Fecha, Progreso, Imagen, Lista de archivos, Checkbox, Combobox
- **Cloud Sync integrado**: Sincronización automática con **Dropbox** y **MEGA** (gestión de conflictos: escritura única, modo solo lectura en otros dispositivos)
- **Recordatorios de fecha**: Tareas, citas, cumpleaños con notificaciones centralizadas
- **Búsqueda instantánea**: Resultados resaltados en tiempo real en vista Tabla
- **Backup & Export**: Asistente de backup (`.symphytum`) y exportación/importación CSV (limitada a campos de texto)
- **SQLite embebido**: Base de datos local rápida, eficiente y resistente a corrupción
- **Multiidioma**: Inglés, Alemán, Polaco, Francés, Italiano
- **Multiplataforma nativo**: Windows (7/8/10), macOS (10.12+), Linux (AppImage, .deb, AUR, Snap)
- **Licencia BSD-2.0**: Código abierto, libre para cualquier propósito

## 📋 Requisitos del sistema

- **Windows**: 7, 8, 10 (32 o 64 bits)
- **macOS**: 10.12 (Sierra) o superior, 64 bits
- **Linux**: x86_64 (AppImage universal, .deb para Ubuntu/Debian, AUR para Arch, Snap)
- **RAM**: 512 MB mínimo (muy ligero)
- **Espacio en disco**: 50-200 MB + datos
- **Cloud Sync (opcional)**: Cuenta Dropbox o MEGA
- **SQLite**: Incluido (base de datos embebida)
- **NO es servidor web**: No expone puertos, no requiere Docker, no es reemplazo de Airtable/NocoDB web

## 🐳 Instalación

> Symphytum NO usa Docker. Instalación nativa por plataforma:

### Windows
```bash
# Opción 1: Instalador recomendado
# Descargar: symphytum-2.6-setup.exe
# Ejecutar y seguir asistente

# Opción 2: Portable (sin instalación)
# Descargar: Symphytum-windows-portable.zip
# Descomprimir y ejecutar Symphytum.exe
```

### macOS
```bash
# Descargar imagen DMG
# symphytum-2.6.dmg
# Arrastrar a carpeta Applications
```

### Linux (AppImage - Universal)
```bash
wget https://github.com/giowck/symphytum/releases/download/v2.6/Symphytum-x86_64.AppImage
chmod +x Symphytum-x86_64.AppImage
./Symphytum-x86_64.AppImage
```

### Linux (Ubuntu/Debian - .deb)
```bash
wget https://github.com/giowck/symphytum/releases/download/v2.6/symphytum-2.6-x86_64.deb
sudo apt install ./symphytum-2.6-x86_64.deb
```

### Linux (Arch Linux - AUR)
```bash
yay -S symphytum
# o
paru -S symphytum
```

### Linux (Snap)
```bash
sudo snap install symphytum
```

## ⚙️ Configuración

1. **Primer lanzamiento**: Al abrir Symphytum, se crea automáticamente el directorio de configuración (`~/.config/symphytum/` en Linux)
2. **Idioma**: Settings → Language → Seleccionar (English, Deutsch, Polski, Français, Italiano)
3. **Cloud Sync (opcional)**: Settings → Cloud Sync → Elegir Dropbox o MEGA → Authorize con credenciales → Enable sync
4. **Recordatorios**: Settings → Reminders → Configurar notificaciones de tareas/citas/cumpleaños
5. **Backup automático**: Settings → Backup → Definir frecuencia y ubicación de backups automáticos
6. **Rendimiento**: Settings → General → Ajustar caché y comportamiento de guardado automático

## 🚀 Primeros pasos

1. **Crear nueva base de datos**
   - File → New → Nombrar tu database (ej: "Contactos", "Inventario")
   - Elegir ubicación para guardar (archivo `.symphytum`)
   - La base de datos se abre vacía

2. **Crear primera colección**
   - Panel Collections (izquierda) → "+" para agregar
   - Dar nombre (ej: "Personas") → Colección creada, pestaña abierta

3. **Agregar campos**
   - Colección → click "+" para agregar field
   - Elegir tipo: Text, Numeric, Date, Image, File, Checkbox, Combobox, etc.
   - Nombrar field (ej: "Nombre", "Email", "Cumpleaños") → OK → field agregado
   - Repetir para más campos

4. **Usar Form View**
   - Pestaña Form muestra layout de campos
   - Drag-and-drop para reorganizar campos
   - Click "New record" → Ingresar valores → Auto-save al cerrar

5. **Usar Table View**
   - Pestaña Table muestra grid con filas
   - Caja de búsqueda arriba: búsqueda mientras escribes
   - Click en cabecera de columna para ordenar
   - Seleccionar múltiples registros para comparar
   - Eliminar filas si necesario

6. **Configurar Cloud Sync (opcional)**
   - Settings → Cloud Sync → Elegir Dropbox o MEGA
   - Authorize con credenciales → Enable sync
   - Abrir misma base de datos en otro equipo → sync automático

7. **Backup y Export**
   - File → Backup → Asistente crea backup `.symphytum`
   - File → Export CSV → Crea `.csv` con todos los registros

## 💡 Casos de uso

- **Gestión de contactos**: Directorio personal con emails, teléfonos, cumpleaños, recordatorios
- **Inventario tracking**: SKU, cantidades, ubicaciones, imágenes, búsqueda/ordenación rápida
- **Catálogos de colecciones**: DVDs, libros, juguetes, monedas, etc. con imágenes
- **CRM personal clientes/leads**: Notas, estado, fechas de seguimiento
- **Base de datos de recetas**: Ingredientes, pasos, imágenes de platos
- **Seguimiento tareas/proyectos simple**: Tareas, fechas, estado, notas sin complejidad
- **Multi-dispositivo sincronizado**: Cloud sync (Dropbox/MEGA) para acceso en laptop, desktop, otra máquina

## 🔒 Acceso remoto seguro

Symphytum **NO expone interfaz web ni puertos de red**. Para acceso remoto:

- **Cloud Sync nativo**: Usar Dropbox o MEGA (sincronización automática del archivo `.symphytum`)
- **Copia manual**: Copiar archivo `.symphytum` entre dispositivos (USB, red local, Nextcloud, Syncthing)
- **Escritorio remoto**: RDP/VNC/TeamViewer al equipo donde corre Symphytum
- **NO es accesible desde navegador**: No hay API REST, no hay Web UI

## 🛠️ Gestión y mantenimiento

- **Actualizaciones**: Proyecto archivado (oct 2020). v2.6 es última versión estable. No hay actualizaciones de seguridad.
- **Backup regular**: File → Backup → Guardar copias `.symphytum` en ubicación segura (externo/cloud)
- **Integridad SQLite**: Base de datos embebida resistente a corrupción; si hay problemas, restaurar desde backup
- **Migración datos**: Export CSV → Import en alternativa moderna (NocoDB, Teable, Baserow)
- **Logs**: Consola/terminal al lanzar AppImage muestra salida debug
- **Limpieza**: Eliminar archivos `.symphytum-journal` y `.symphytum-wal` si quedan tras cierre forzado

## 📝 Licencia

**BSD-2-Clause License** - Código abierto, libre para cualquier propósito (comercial, privado, modificación, distribución).

Copyright (c) 2010-2020, giowck. All rights reserved.

---

> 📖 **Artículo original**: [Cómo instalar Symphytum en Docker - Personal Database con Cloud Sync](https://genbyte.blogspot.com/2026/09/como-instalar-symphytum-en-docker.html)  
> ⚠️ *Nota: El título del post menciona "Docker" pero Symphytum es aplicación desktop nativa, no contenedor.*