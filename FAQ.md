# ❓ Preguntas Frecuentes (FAQ)

## Índice
- [General](#general)
- [Instalación y Configuración](#instalación-y-configuración)
- [Uso y Funcionalidad](#uso-y-funcionalidad)
- [Seguridad y Privacidad](#seguridad-y-privacidad)
- [Solución de Problemas](#solución-de-problemas)
- [Limitaciones](#limitaciones)

---

## General

### ¿Qué es MCP?
MCP (Model Context Protocol) es un protocolo desarrollado por Anthropic que permite a Claude conectarse con aplicaciones externas y acceder a datos en tiempo real. Es como darle a Claude "herramientas" para interactuar con tus aplicaciones.

### ¿Es gratis?
Sí, la configuración es completamente gratuita. Sin embargo:
- Notion tiene planes gratuitos y de pago (la integración funciona con ambos)
- Claude puede requerir una suscripción según tu plan (verifica en claude.ai)
- Los servidores MCP son open-source y gratuitos

### ¿Funciona con claude.ai (web)?
Actualmente, los servidores MCP solo funcionan con Claude Desktop App. La versión web no soporta esta funcionalidad todavía.

### ¿En qué sistemas operativos funciona?
- ✅ macOS
- ✅ Windows
- ✅ Linux

### ¿Necesito saber programar?
No. Esta guía está diseñada para usuarios sin conocimientos de programación. Solo necesitas:
- Seguir instrucciones paso a paso
- Editar un archivo de configuración (te mostramos cómo)
- Usar la terminal para comandos simples (te damos todos los comandos)

---

## Instalación y Configuración

### ¿Cuánto tiempo toma la configuración?
Entre 15-30 minutos para la primera configuración. Una vez hecho, no necesitas volver a configurar.

### ¿Dónde consigo el token de Notion?
Sigue estos pasos:
1. Ve a [notion.so/my-integrations](https://www.notion.so/my-integrations)
2. Crea una nueva integración
3. Copia el token que te proporciona
4. **Importante**: Comparte las páginas que quieres que Claude acceda con esta integración

Ver [Paso 1 de la guía completa](./guia-mcp-notion.md#paso-1-obtener-api-key-de-notion) para detalles.

### ¿Dónde está el archivo de configuración?
Depende de tu sistema operativo:
- **macOS**: `~/Library/Application Support/Claude/claude_desktop_config.json`
- **Windows**: `%APPDATA%\Claude\claude_desktop_config.json`
- **Linux**: `~/.config/Claude/claude_desktop_config.json`

Si el archivo no existe, créalo con el contenido de `config.example.json`.

### ¿Puedo usar múltiples integraciones?
Sí, puedes configurar múltiples servidores MCP en el mismo archivo de configuración. Por ejemplo, Notion + Google Drive + Slack.

Ejemplo:
```json
{
  "mcpServers": {
    "notion": { ... },
    "google-drive": { ... },
    "slack": { ... }
  }
}
```

### ¿Cómo actualizo la configuración?
1. Edita el archivo `claude_desktop_config.json`
2. Guarda los cambios
3. Reinicia Claude Desktop completamente (ciérralo y ábrelo de nuevo)

---

## Uso y Funcionalidad

### ¿Qué puede hacer Claude con mi Notion?
Claude puede:
- ✅ Leer páginas y bases de datos
- ✅ Crear nuevas páginas
- ✅ Editar contenido existente
- ✅ Agregar y modificar propiedades de bases de datos
- ✅ Crear y actualizar tablas
- ✅ Buscar información
- ✅ Generar reportes y análisis

### ¿Qué NO puede hacer?
- ❌ Eliminar páginas (por seguridad)
- ❌ Cambiar permisos de páginas
- ❌ Acceder a páginas que no has compartido con la integración
- ❌ Modificar configuraciones del workspace

### ¿Cómo le digo a Claude que use Notion?
Simplemente hazle una pregunta o solicitud relacionada con Notion:
- "Muéstrame mis páginas de Notion"
- "Crea una nueva página de proyecto"
- "Actualiza la base de datos de tareas"

Claude detectará automáticamente que necesita usar la integración de Notion.

### ¿Puedo deshacer cambios que haga Claude?
Sí, Notion mantiene historial de versiones. Puedes:
1. Hacer clic en "⋯" en cualquier página
2. Seleccionar "Page history"
3. Restaurar versiones anteriores

### ¿Claude puede trabajar con plantillas de Notion?
Sí, Claude puede:
- Usar plantillas existentes
- Crear páginas basadas en plantillas
- Crear nuevas plantillas
- Modificar plantillas

---

## Seguridad y Privacidad

### ¿Es seguro compartir mi token con Claude?
El token se almacena **localmente** en tu computadora en el archivo de configuración. Claude Desktop lo usa para conectarse a Notion, pero:
- ❌ No se envía a servidores de Anthropic
- ❌ No se comparte con terceros
- ✅ Solo tu instalación local de Claude lo usa

**Importante**: Nunca compartas tu token públicamente ni lo subas a repositorios.

### ¿Claude puede ver toda mi información de Notion?
**NO**. Claude solo puede acceder a:
- Páginas que explícitamente hayas compartido con la integración
- Sub-páginas de esas páginas compartidas

Todo lo demás permanece privado y no accesible.

### ¿Cómo revoco el acceso?
Para revocar completamente el acceso:
1. Ve a [notion.so/my-integrations](https://www.notion.so/my-integrations)
2. Encuentra tu integración
3. Haz clic en "..." y selecciona "Delete integration"

O simplemente deja de compartir páginas con la integración.

### ¿Los datos salen de mi computadora?
Cuando Claude procesa tu información:
- Lee datos de Notion (vía API)
- Los analiza usando los modelos de Anthropic (esto requiere enviar datos a sus servidores)
- Ejecuta las acciones en Notion

Si tienes datos sensibles, considera qué páginas compartes con la integración.

### ¿Puedo limitar lo que Claude puede hacer?
Sí, a través de:
1. **Permisos de la integración**: En Notion puedes limitar los permisos de lectura/escritura
2. **Páginas compartidas**: Solo comparte las páginas necesarias
3. **Supervisión**: Revisa las acciones que Claude realiza antes de confirmarlas

---

## Solución de Problemas

### Claude no detecta el servidor MCP

**Posibles causas y soluciones:**

1. **Archivo de configuración en ubicación incorrecta**
   - Verifica la ruta según tu SO
   - Asegúrate de que el directorio exista

2. **Error de sintaxis en JSON**
   - Usa un validador JSON online
   - Copia de nuevo desde `config.example.json`
   - Verifica comillas y comas

3. **No reiniciaste Claude**
   - Cierra completamente Claude Desktop
   - Espera 5 segundos
   - Vuelve a abrirlo

4. **Permisos de archivo**
   ```bash
   # macOS/Linux - verifica permisos
   chmod 644 ~/Library/Application\ Support/Claude/claude_desktop_config.json
   ```

### Error: "Invalid token" o "Unauthorized"

**Causas comunes:**

1. **Token incorrecto**
   - Verifica que copiaste el token completo
   - No debe tener espacios ni saltos de línea
   - Debe comenzar con `secret_`

2. **Token expirado o revocado**
   - Genera un nuevo token en Notion
   - Actualiza el archivo de configuración

3. **Integración eliminada**
   - Verifica que la integración aún existe en Notion
   - Crea una nueva si es necesario

### "Cannot access page" o "Page not found"

**Solución:**
La página no está compartida con tu integración.

1. Abre la página en Notion
2. Clic en "⋯" (arriba a la derecha)
3. "Add connections" → Selecciona tu integración
4. Confirma

**Nota**: Si es una página dentro de otra, ambas deben estar compartidas.

### Node.js no encontrado

```bash
# Verifica instalación
node --version

# Si no está instalado:
# macOS: brew install node
# Windows: Descarga desde nodejs.org
# Linux: sudo apt install nodejs npm
```

### El servidor MCP no inicia

1. **Instala el paquete globalmente**
   ```bash
   npm install -g @modelcontextprotocol/server-notion
   ```

2. **Verifica versión de Node.js**
   ```bash
   node --version
   # Debe ser 18 o superior
   ```

3. **Revisa logs de Claude**
   - macOS: `~/Library/Logs/Claude/`
   - Windows: `%APPDATA%\Claude\logs\`
   - Linux: `~/.config/Claude/logs/`

### Claude hace cambios incorrectos

**Prevención:**
- Sé muy específico en tus instrucciones
- Pide a Claude que confirme antes de hacer cambios grandes
- Revisa cambios en Notion inmediatamente

**Corrección:**
- Usa el historial de versiones de Notion
- Restaura la versión anterior

---

## Limitaciones

### ¿Qué limitaciones tiene?

**Técnicas:**
- Rate limits de la API de Notion (3 requests/segundo)
- Tamaño máximo de página (depende de Notion)
- No puede procesar imágenes dentro de páginas (solo texto)

**Funcionales:**
- Claude puede cometer errores en operaciones complejas
- No puede "recordar" contexto entre sesiones sin re-leer
- Limitado por las capacidades de la API de Notion

### ¿Cuántas páginas puede manejar Claude?

No hay un límite estricto, pero:
- Para operaciones en muchas páginas (50+), puede tomar tiempo
- Bases de datos muy grandes pueden requerir múltiples consultas
- La velocidad depende de la complejidad de las páginas

### ¿Funciona con todas las versiones de Notion?

Sí, funciona con:
- ✅ Notion Personal (gratis)
- ✅ Notion Plus
- ✅ Notion Business
- ✅ Notion Enterprise

### ¿Puedo usarlo para workspaces de equipos?

Sí, pero considera:
- La integración necesitará permisos de admin del workspace
- Todos los miembros pueden ver que existe la integración
- Los cambios que hagas serán visibles para el equipo

---

## ¿No encuentras tu pregunta?

1. **Revisa la [guía completa](./guia-mcp-notion.md)**
2. **Busca en [Issues existentes](https://github.com/TU-USUARIO/claude-mcp-notion/issues)**
3. **Abre un [nuevo Issue](https://github.com/TU-USUARIO/claude-mcp-notion/issues/new)**
4. **Únete al [Discord de Anthropic](https://discord.gg/anthropic)**

---

**¿Esta FAQ te ayudó?** Considera contribuir agregando más preguntas que encuentres.

**Última actualización**: Enero 2024
