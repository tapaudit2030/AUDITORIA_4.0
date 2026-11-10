# Conectores

## Conector de este plugin

| Categoría | Conector | Para qué lo usa el plugin |
|---|---|---|
| Documentos y almacenamiento | **Microsoft 365** (SharePoint · OneDrive · Outlook · Teams) | Leer la carpeta que comparte el cliente o el archivo de papeles de la firma |

El conector está declarado **por nombre** en `.mcp.json`. Al instalar el plugin,
si la cuenta ya tiene Microsoft 365 conectado, queda enlazado; si no, hay que
conectarlo desde los ajustes de conectores de claude.ai.

## Qué se hace por conector y qué no

**Sí, por conector** — `sharepoint_search`, `sharepoint_folder_search` y
`read_resource`:

- papeles de trabajo del ejercicio anterior en `.xlsx`, para estudiar formatos,
  referencias y extraer los bancos de preguntas, riesgos y controles;
- estados financieros y dictamen del ejercicio anterior;
- políticas contables, manuales de funciones y de procedimientos, organigramas y
  flujogramas (control interno);
- cualquier PDF de respaldo.

**No, por conector — adjúntalos al chat:**

- los **`.xls` binarios** (OLE2) que exportan los ERP ecuatorianos. El conector
  devuelve el texto desordenado y separa los valores de los códigos de cuenta;
  cualquier cifra extraída de ahí estaría inventada. Esto incluye los balances
  de comprobación mensuales, que son el insumo principal del motor.

Si el cliente puede exportar a `.xlsx` o `.csv`, pídeselo: ese camino sí funciona
por conector.

## Otras opciones en la misma categoría

El plugin no depende de Microsoft 365 en particular. Cualquier conector de
documentos sirve para el mismo fin, y sin ninguno el trabajo se hace igual
adjuntando los archivos al chat. Si la firma usa otro almacenamiento —Box,
Google Drive, Notion— conéctalo y añádelo a `.mcp.json`; la regla de los `.xls`
se mantiene con todos.

## Correo y calendario

Las herramientas de Outlook que trae el mismo conector sirven para la
correspondencia del encargo: solicitud de información al cliente (PPC),
confirmaciones externas bajo NIA 505 y actas de reunión. El plugin **no envía
correo por su cuenta**: toda comunicación con el cliente la aprueba y la envía el
auditor responsable.
