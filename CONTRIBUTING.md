# 🤝 Guía de Contribución

¡Gracias por tu interés en contribuir a este proyecto! Esta guía te ayudará a hacer contribuciones efectivas.

## 📋 Tabla de Contenidos
- [Código de Conducta](#código-de-conducta)
- [¿Cómo puedo contribuir?](#cómo-puedo-contribuir)
- [Proceso de Contribución](#proceso-de-contribución)
- [Guías de Estilo](#guías-de-estilo)
- [Comunidad](#comunidad)

## 🌟 Código de Conducta

Este proyecto se adhiere a un código de conducta que todos los contribuyentes deben seguir:

- **Sé respetuoso**: Trata a todos con respeto y consideración
- **Sé constructivo**: Ofrece críticas constructivas y ayuda
- **Sé inclusivo**: Acepta diferentes perspectivas y experiencias
- **Sé profesional**: Mantén las discusiones enfocadas en el tema

## 💡 ¿Cómo puedo contribuir?

Hay muchas formas de contribuir a este proyecto:

### 1. Reportar Bugs 🐛

¿Encontraste un error? Ayúdanos a mejorarlo:

1. Verifica que el bug no haya sido reportado en [Issues](https://github.com/TU-USUARIO/claude-mcp-notion/issues)
2. Si no existe, crea un nuevo issue con:
   - **Título descriptivo**: Ej: "Error al conectar con Notion en Windows 11"
   - **Descripción detallada** del problema
   - **Pasos para reproducir**
   - **Comportamiento esperado** vs **comportamiento actual**
   - **Screenshots** (si aplica)
   - **Entorno**: SO, versión de Node.js, versión de Claude Desktop
   
**Template de Bug Report:**
```markdown
## Descripción
[Descripción clara del problema]

## Pasos para reproducir
1. [Primer paso]
2. [Segundo paso]
3. [Ver error]

## Comportamiento esperado
[Lo que debería pasar]

## Comportamiento actual
[Lo que realmente pasa]

## Entorno
- SO: [ej. macOS 13.0]
- Node.js: [ej. v18.0.0]
- Claude Desktop: [ej. v1.0.0]

## Screenshots
[Si aplica]
```

### 2. Sugerir Mejoras 💡

¿Tienes una idea para mejorar la guía o funcionalidad?

1. Abre un issue con la etiqueta `enhancement`
2. Describe claramente:
   - **El problema** que resuelve tu sugerencia
   - **La solución propuesta**
   - **Alternativas consideradas**
   - **Beneficios** para los usuarios

### 3. Mejorar Documentación 📚

La documentación siempre puede mejorarse:

- Corregir errores tipográficos o gramaticales
- Aclarar instrucciones confusas
- Agregar ejemplos adicionales
- Mejorar traducciones
- Agregar capturas de pantalla
- Crear tutoriales en video

### 4. Compartir Casos de Uso 🎯

¿Usas Claude + Notion de forma innovadora?

1. Agrega tu caso de uso a `CASOS-DE-USO.md`
2. Incluye:
   - Descripción del escenario
   - Comandos específicos que usas
   - Beneficios que obtuviste
   - Tips útiles

### 5. Contribuir Código 💻

Si quieres contribuir scripts o automatizaciones:

1. Asegúrate de que el código sea útil para otros usuarios
2. Documenta claramente cómo usarlo
3. Incluye ejemplos
4. Sigue las guías de estilo

## 🔄 Proceso de Contribución

### Para cambios pequeños (typos, mejoras menores)

1. Haz fork del repositorio
2. Crea una rama desde `main`:
   ```bash
   git checkout -b fix/typo-en-readme
   ```
3. Realiza tus cambios
4. Commit con mensaje descriptivo:
   ```bash
   git commit -m "Corrige typo en sección de instalación"
   ```
5. Push a tu fork:
   ```bash
   git push origin fix/typo-en-readme
   ```
6. Abre un Pull Request

### Para cambios grandes (nuevas secciones, características)

1. **Primero abre un Issue** para discutir el cambio
2. Espera feedback antes de invertir mucho tiempo
3. Una vez aprobado, sigue el proceso anterior

### Revisión de Pull Requests

Los mantenedores revisarán tu PR considerando:
- ✅ Claridad y utilidad del cambio
- ✅ Calidad de la documentación
- ✅ Consistencia con el estilo del proyecto
- ✅ Que no rompa funcionalidad existente

Pueden solicitar cambios antes de aprobar.

## 📝 Guías de Estilo

### Documentación

- **Idioma**: Español (archivos principales) o Inglés (si prefieres)
- **Formato**: Markdown (.md)
- **Estructura**: Usa headings jerárquicos (H1, H2, H3)
- **Código**: Usa bloques de código con sintaxis highlighting
  ```markdown
  ```bash
  npm install
  ``` 
  ```

### Estilo de Escritura

- **Tono**: Amigable pero profesional
- **Persona**: Segunda persona ("tú", "puedes")
- **Claridad**: Instrucciones paso a paso numeradas
- **Ejemplos**: Incluye ejemplos prácticos siempre que sea posible

### Formato de Commits

Usa mensajes de commit descriptivos:

```bash
# ✅ Bueno
git commit -m "Agrega sección sobre seguridad en FAQ"
git commit -m "Corrige error en comando de instalación para Windows"
git commit -m "Actualiza ejemplo de caso de uso para freelancers"

# ❌ Malo
git commit -m "fix"
git commit -m "update"
git commit -m "cambios varios"
```

### Nombres de Ramas

Usa nombres descriptivos con prefijos:

- `feature/nombre-feature` - Nuevas características
- `fix/descripcion-fix` - Correcciones de bugs
- `docs/tema` - Mejoras en documentación
- `examples/nombre-ejemplo` - Nuevos ejemplos

Ejemplos:
```bash
feature/casos-uso-estudiantes
fix/error-configuracion-windows
docs/mejorar-guia-instalacion
examples/crm-ventas
```

## 📊 Checklist antes de enviar PR

Antes de enviar tu Pull Request, verifica:

- [ ] He leído la guía de contribución
- [ ] Mi cambio sigue el estilo del proyecto
- [ ] He actualizado la documentación relevante
- [ ] He probado que mi cambio funciona
- [ ] Mi commit tiene un mensaje descriptivo
- [ ] He vinculado el Issue relacionado (si existe)

## 🎨 Tipos de Contribuciones Especialmente Bienvenidas

Estamos especialmente interesados en:

1. **Traducciones**: Guías en otros idiomas
2. **Casos de uso específicos**: Para diferentes industrias/roles
3. **Scripts de automatización**: Que complementen la guía
4. **Troubleshooting**: Soluciones a problemas comunes
5. **Integraciones**: Con otros servicios MCP
6. **Videos tutoriales**: Complementos visuales a la guía

## 💬 Comunidad

### ¿Dónde obtener ayuda?

- **GitHub Issues**: Para bugs y sugerencias
- **Discord de Anthropic**: Para preguntas generales sobre Claude
- **Discusiones**: Para conversaciones abiertas sobre el proyecto

### Reconocimiento

Todos los contribuidores serán:
- Listados en un archivo CONTRIBUTORS.md
- Mencionados en los release notes
- Agradecidos públicamente

## 📜 Licencia

Al contribuir, aceptas que tus contribuciones se licenciarán bajo la misma licencia MIT del proyecto.

---

## ❓ ¿Tienes dudas?

Si tienes preguntas sobre cómo contribuir:
1. Revisa los [Issues existentes](https://github.com/TU-USUARIO/claude-mcp-notion/issues)
2. Abre un nuevo Issue con la etiqueta `question`
3. Pregunta en los canales de la comunidad

---

**¡Gracias por hacer de este proyecto algo mejor!** 🙏

Tu tiempo y esfuerzo son muy apreciados.
