# AUDITOR_4.0

Agente de auditoría de estados financieros para **ThePowerAudit S.A.** y
**GLOBALAUDITORS CÍA. LTDA.**, construido sobre **Claude Code**. Ejecuta la
auditoría en tres fases —**Planificación, Preliminar y Final**— bajo NIA, con
NIIF completas o NIIF para las PYMES (se pregunta en cada cliente) y la
normativa tributaria, laboral y societaria del Ecuador.

## Instalación en la PC de cada auditor

1. Instale **Claude Code** (https://claude.com/claude-code) e inicie sesión con su cuenta de la firma.
2. Instale **Python 3.10+** y **Git**.
3. Clone el repositorio y entre a la carpeta:
   ```bash
   git clone https://github.com/<organizacion>/auditor-4.0.git
   cd auditor-4.0
   pip install -r requirements.txt
   ```
4. Abra Claude Code dentro de la carpeta: `claude`
5. Para recibir mejoras del equipo: `git pull` antes de empezar el día.

## Cómo se usa

| Comando | Para qué |
|---|---|
| `/nuevo-encargo` | Abre un cliente: firma, tipo de cliente, marco NIIF, materialidad, ciclos. Crea `encargos/<CLIENTE_AÑO>/` |
| `/fase-planificacion` | Fase 1: aceptación, carta de encargo, entendimiento, materialidad P-01, analítica, riesgos, COSO, recorridos, estrategia y programas |
| `/fase-preliminar` | Fase 2: materialidad P-01.1, revisión interina por ciclos, pruebas de controles, carta de control interno |
| `/fase-final` | Fase 3: materialidad P-01.2, sustantivas, confirmaciones, hechos posteriores, AJ-01, carta de representación, borrador de informe |
| `/estado-encargo` | Qué está hecho, qué falta y qué decide el socio |

También puede pedirlo en lenguaje natural: *"abre el encargo de ACME 2026"*,
*"haz la materialidad de la fase preliminar"*, *"prepara la carta de control interno"*.

## Estructura

```
CLAUDE.md                 reglas del agente (las lee Claude Code al iniciar)
.claude/skills/           fases (nuevo-encargo, fase-*, estado-encargo) y skills de área
.claude/agents/           subagente revisor-calidad
firmas/                   identidad de cada firma (nombre, RUC, paleta, logo)
formatos_referencias/     modelos propios de cada firma (Word y Excel)
plantillas/               plantilla de encargo.json
encargos/                 datos de los clientes — NO se suben a GitHub
```

## Reglas de oro

- No inventa cifras, evidencia ni normativa; lo que falta queda marcado.
- Pregunta siempre la firma, el tipo de cliente, el marco NIIF y la materialidad.
- Papeles en **Excel**; cartas e informes en **Word**; no genera PDF.
- No contabiliza ajustes ni decide la opinión: eso es del socio.
- La información de clientes vive en `encargos/` y nunca se sube al repositorio.

## Pendientes de configuración

- `formatos_referencias/` — cargar los modelos de cada firma.
- Generalizar los generadores de sumarias, comparativos y analítica (hoy conservan
  textos del encargo piloto; el agente los adapta por encargo).
