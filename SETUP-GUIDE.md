# Guía Completa: Configuración de Servidor MCP para Notion

## 📋 Tabla de Contenidos
1. [Introducción](#introducción)
2. [Requisitos Previos](#requisitos-previos)
3. [Paso 1: Obtener API Key de Notion](#paso-1-obtener-api-key-de-notion)
4. [Paso 2: Configurar el Servidor MCP](#paso-2-configurar-el-servidor-mcp)
5. [Paso 3: Integrar con Claude](#paso-3-integrar-con-claude)
6. [Paso 4: Pruebas y Verificación](#paso-4-pruebas-y-verificación)
7. [Ejemplos de Uso](#ejemplos-de-uso)
8. [Solución de Problemas](#solución-de-problemas)
9. [Recursos Adicionales](#recursos-adicionales)

---

## Introducción

Esta guía te enseñará cómo conectar Claude con tu workspace de Notion mediante el Model Context Protocol (MCP), permitiéndote administrar, actualizar y reorganizar tu Notion mediante comandos en lenguaje natural.

### ¿Qué podrás hacer?
- ✅ Crear y editar páginas automáticamente
- ✅ Administrar bases de datos y propiedades
- ✅ Reorganizar la estructura de tu workspace
- ✅ Dar seguimiento a proyectos mediante Claude
- ✅ Generar reportes y análisis de tus datos
- ✅ Automatizar tareas repetitivas

---

## Requisitos Previos

Antes de comenzar, asegúrate de tener:

- [ ] Cuenta activa de Notion
- [ ] Cuenta de Claude (claude.ai o Claude Desktop App)
- [ ] Node.js versión 18 o superior instalado
- [ ] npm o yarn instalado
- [ ] Conocimientos básicos de terminal/línea de comandos
- [ ] Cuenta de GitHub (opcional, para publicar tu configuración)

### Verificar instalación de Node.js

```bash
node --version
npm --version
```

Si no tienes Node.js, descárgalo desde: https://nodejs.org/

---

## Paso 1: Obtener API Key de Notion

### 1.1 Crear una Integración en Notion

1. Ve a [https://www.notion.so/my-integrations](https://www.notion.so/my-integrations)
2. Haz clic en **"+ New integration"**
3. Completa la información:
   - **Name**: "Claude MCP Integration" (o el nombre que prefieras)
   - **Associated workspace**: Selecciona tu workspace
   - **Type**: Internal Integration
4. En **Capabilities**, asegúrate de tener activado:
   - ✅ Read content
   - ✅ Update content
   - ✅ Insert content
5. Haz clic en **"Submit"**
6. **IMPORTANTE**: Copia y guarda tu **Internal Integration Token** (comienza con `secret_...`)
   - ⚠️ No compartas este token con nadie
   - ⚠️ Guárdalo en un lugar seguro

### 1.2 Compartir páginas con la integración

Para que tu integración pueda acceder a tus páginas de Notion:

1. Abre la página o base de datos que quieres compartir
2. Haz clic en los tres puntos (**•••**) en la esquina superior derecha
3. Selecciona **"Add connections"** o **"Connections"**
4. Busca y selecciona tu integración "Claude MCP Integration"
5. Haz clic en **"Confirm"**

**Nota**: Debes hacer esto para cada página/base de datos que quieras que Claude pueda administrar.

---

## Paso 2: Configurar el Servidor MCP

### 2.1 Instalar el Servidor MCP de Notion

Existen varias opciones. Aquí usaremos el servidor oficial de la comunidad MCP:

```bash
# Opción 1: Instalación global con npm
npm install -g @modelcontextprotocol/server-notion

# Opción 2: Instalación con npx (recomendado, no requiere instalación global)
# Se configura directamente en el siguiente paso
```

### 2.2 Configurar Claude Desktop (Si usas la app de escritorio)

**Para macOS:**

1. Localiza el archivo de configuración:
```bash
~/Library/Application Support/Claude/claude_desktop_config.json
```

2. Edita el archivo (puedes usar nano, vim, o cualquier editor de texto):
```bash
nano ~/Library/Application\ Support/Claude/claude_desktop_config.json
```

3. Agrega la siguiente configuración:
```json
{
  "mcpServers": {
    "notion": {
      "command": "npx",
      "args": [
        "-y",
        "@modelcontextprotocol/server-notion"
      ],
      "env": {
        "NOTION_API_KEY": "TU_TOKEN_AQUI"
      }
    }
  }
}
```

**Para Windows:**

1. Localiza el archivo de configuración:
```
%APPDATA%\Claude\claude_desktop_config.json
```

2. Usa el mismo contenido JSON del ejemplo anterior.

**Para Linux:**

1. Localiza el archivo de configuración:
```bash
~/.config/Claude/claude_desktop_config.json
```

2. Usa el mismo contenido JSON del ejemplo anterior.

### 2.3 Reemplazar el Token

En el archivo JSON, reemplaza `"TU_TOKEN_AQUI"` con tu token de Notion que copiaste en el Paso 1.1.

**Ejemplo:**
```json
"NOTION_API_KEY": "secret_AbCdEf123456..."
```

### 2.4 Guardar y Cerrar

- Si usas nano: presiona `Ctrl + O` para guardar, luego `Ctrl + X` para salir
- Si usas otro editor: guarda normalmente

---

## Paso 3: Integrar con Claude

### 3.1 Reiniciar Claude

- **Claude Desktop App**: Cierra completamente la aplicación y vuelve a abrirla
- **claude.ai (web)**: Esta configuración solo funciona con Claude Desktop por el momento

### 3.2 Verificar la conexión

1. Abre Claude Desktop
2. En el campo de entrada, deberías ver un ícono de herramientas o "🔌" indicando que hay servidores MCP conectados
3. Envía un mensaje de prueba:

```
¿Puedes ver mis páginas de Notion?
```

Si todo está configurado correctamente, Claude debería poder listar tus páginas compartidas.

---

## Paso 4: Pruebas y Verificación

### 4.1 Comandos de prueba básicos

Prueba estos comandos para verificar que todo funciona:

```
1. Lista todas mis páginas de Notion

2. Muéstrame el contenido de la página [nombre de tu página]

3. Crea una nueva página llamada "Prueba MCP" con un título y un párrafo de ejemplo
```

### 4.2 Verificar permisos

Si Claude no puede acceder a alguna página:
- Verifica que compartiste esa página con tu integración (ver Paso 1.2)
- Verifica que el token sea correcto en el archivo de configuración

---

## Ejemplos de Uso

### Gestión de Proyectos

```
Claude, por favor:
1. Revisa mi base de datos "Proyectos"
2. Actualiza todos los proyectos con fecha límite esta semana a estado "Urgente"
3. Crea un reporte semanal con el resumen
```

### Organización de Contenido

```
Reorganiza mi workspace de Notion:
- Crea una nueva página "Dashboard 2024"
- Agrupa todos los proyectos activos
- Crea una tabla con las métricas principales
```

### Automatización de Tareas

```
Cada lunes:
1. Revisa las tareas completadas la semana pasada
2. Crea un resumen en la página "Weekly Reviews"
3. Actualiza los KPIs en el dashboard principal
```

### Creación de Templates

```
Crea un template para mis reuniones semanales que incluya:
- Fecha y participantes
- Agenda con checkboxes
- Notas
- Action items con responsables
```

---

## Solución de Problemas

### Problema: Claude no detecta el servidor MCP

**Solución:**
1. Verifica que el archivo de configuración esté en la ubicación correcta
2. Revisa que el JSON tenga la sintaxis correcta (sin comas extras, comillas correctas)
3. Reinicia completamente Claude Desktop
4. Verifica los logs del sistema:
   - macOS: `~/Library/Logs/Claude/`
   - Windows: `%APPDATA%\Claude\logs\`
   - Linux: `~/.config/Claude/logs/`

### Problema: Error de autenticación

**Solución:**
1. Verifica que el token sea correcto y esté completo
2. Asegúrate de no haber compartido el token con espacios o saltos de línea
3. Regenera el token en Notion si es necesario

### Problema: No puede acceder a ciertas páginas

**Solución:**
1. Verifica que hayas compartido esas páginas específicas con tu integración
2. Las sub-páginas también necesitan ser compartidas individualmente en algunos casos
3. Revisa los permisos de la integración en Notion

### Problema: El servidor no inicia

**Solución:**
1. Verifica que Node.js esté instalado correctamente: `node --version`
2. Intenta instalar el paquete globalmente: `npm install -g @modelcontextprotocol/server-notion`
3. Verifica que no haya conflictos de versiones de Node.js

---

## Recursos Adicionales

### Documentación Oficial
- [Notion API Documentation](https://developers.notion.com/)
- [MCP Documentation](https://modelcontextprotocol.io/)
- [Claude Documentation](https://docs.claude.com/)

### Servidores MCP Alternativos
- [mcp-notion-server](https://github.com/modelcontextprotocol/servers/tree/main/src/notion) - Servidor oficial
- Otros servidores comunitarios en [GitHub MCP Topic](https://github.com/topics/model-context-protocol)

### Comunidad y Soporte
- [Anthropic Discord](https://discord.gg/anthropic)
- [Notion Community](https://www.notion.so/community)
- Issues en GitHub del servidor MCP específico que uses

---

## Seguridad y Mejores Prácticas

### ⚠️ Importantes

1. **NUNCA** compartas tu token de API públicamente
2. **NUNCA** subas tu archivo `claude_desktop_config.json` a repositorios públicos
3. Usa variables de entorno si trabajas en equipo
4. Revoca tokens que ya no uses
5. Crea integraciones separadas para diferentes propósitos

### Recomendaciones

- Haz backup de tu configuración
- Documenta las páginas que compartes con la integración
- Revisa periódicamente los permisos de tu integración
- Mantén actualizado el servidor MCP

---

## Contribuciones

Si encontraste útil esta guía o quieres mejorarla:

1. Haz fork del repositorio
2. Crea una rama para tus cambios
3. Envía un pull request con tus mejoras
4. Comparte tu experiencia en issues

---

## Licencia

Esta guía está disponible bajo licencia MIT. Siéntete libre de usar, modificar y compartir.

---

## Changelog

- **v1.0.0** (2024) - Versión inicial de la guía
  - Configuración básica de servidor MCP
  - Integración con Notion
  - Ejemplos de uso
  - Solución de problemas comunes

---

## Agradecimientos

Gracias a la comunidad de Anthropic, desarrolladores de MCP, y usuarios de Notion que han contribuido con sus experiencias y mejores prácticas.

---

**¿Tienes preguntas?** Abre un issue en este repositorio o únete a las comunidades mencionadas en la sección de Recursos Adicionales.

**¿Funcionó esta guía?** ⭐ Dale una estrella al repositorio y compártela con otros usuarios.
