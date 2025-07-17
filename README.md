# mcp-notes

## Introducción

- Se tiene un LLM determinado que funcionaría como un cliente ya que consume recursos para devolver una respuesta.
- Se puede determinar que un LLM realice una acción.
- Para que un LLM realice una acción, este debe recibir una instrucción que el LLM va a interpretar y enviar al servidor mediante el protocolo MCP (Model Context Protocol: es un protocolo de comunicación).
- Un LLM puede realizar diversas acciones en el servidor luego de que este recibiese las reglas a ejecutar mediante MCP:
  - Conectarse a la API de GitHub
  - Crear una PR con una solución.
- Flujo de una petición:
  - 1. El usuario envía una petición (Instrucción para realizar una acción) y el cliente (LLM) la interpreta.
  - 2. Mediante MCP le envía la información al servidor.
  - 3. El servidor le envía la respuesta al cliente LLM.
  - 4. El cliente LLM le devuelve la respuesta procesada al o los usuarios.
- Se puede usar docker o npx para poder utilizar MCP.
- Ejemplo con Claude:
  - El archivo "claude_desktop_config.json" permite servidores MCP con la siguiente configuración:

```json
{
  "mcpServers": {
    "filesystem": {
      "command": "npx",
      "args": [
        "-y",
        "@modelcontextprotocol/server-filesystem",
        "/Users/username/Desktop",
        "/path/to/other/allowed/dir"
      ]
    }
  }
}
```

CONTINUAR EN 21:30
