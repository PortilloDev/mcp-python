# Instalar globalmente 
pip install "mcp[cli]"
pip install "azure-ai-inference"


# Abrir servidor
```bash
mcp dev server.py
```

## En caso de error al conectar el servidor web
- cerrar terminal con server levantado
- ejecutar comando en nueva terminal
```bash
npx @modelcontextprotocol/inspector mcp run server.py  
```
- volver al navegador y conectar



# Resumen SSE

Al hablar de MCP, es fundamental comprender los tipos de conexiones disponibles, especialmente las conexiones Server Send Events (SSE). Estas permiten realizar streaming de aplicaciones mediante HTTP, logrando que la comunicación entre servidor y cliente sea más rápida, ligera y eficiente, optimizando así la experiencia del usuario.

¿Qué son las conexiones Server Send Events (SSE)?
Las conexiones SSE posibilitan que tu servidor envíe información al cliente constantemente a través de HTTP. Esto facilita un flujo de datos eficiente y optimizado, reduciendo el exceso de procesamiento y logrando una interacción ágil y continua.

¿Qué beneficios aporta utilizar SSE?
Usar SSE mejora notablemente la comunicación servidor–cliente en aspectos clave:

Transmisión rápida de información.
Menor carga en el procesamiento.
Mayor eficiencia en el manejo continuo de datos.
Esto evita la lentitud progresiva causada por contextos extensos y mejora la gestión dinámica de información mediante entregas parciales, similares al funcionamiento de plataformas como Netflix.

¿Cómo configurar una conexión SSE en Python con Fast MCP?
Para implementar una conexión SSE, realiza los siguientes pasos básicos:

Crea una carpeta para tu clase, por ejemplo, clase siete.
Genera un archivo Python llamado server.py.
Importa las siguientes librerías necesarias para trabajar con Fast MCP, Starlette Applications y Starlette Routing:
from starlette.applications import Starlette
from starlette.routing import Route
from fast_mcp import FastMCP
Define e inicia tu servidor usando Fast MCP, nombrándolo claramente para diferenciarlo:
app = FastMCP("SSE de Platzi")
Despliega tu aplicación mediante UVCORN, ejecutando el siguiente comando en la terminal:
uvicorn server:app
Conecta tu aplicación con SSE usando la URL específica: localhost:8000/SSE.
La conexión al inspector sigue siendo igual, solo cambiando el transporte de STDIO a SSE al especificar la URL señalada. Esta pequeña modificación hará más eficiente el intercambio de información sin cambios visibles en la interfaz del usuario.

¿Es notable la diferencia visual al usar SSE?
En términos visuales o funcionales, el usuario no nota cambios inmediatos al interactuar con la aplicación. Las diferencias residen en los aspectos técnicos internos: el rendimiento y la eficiencia en el procesamiento de datos al usar SSE hacen que esta opción destaque sobre las conexiones tradicionales STDIO.

Te invitamos a experimentar y dejar tus comentarios sobre qué diferencias observaste al implementar Server Send Events con Fast MCP.