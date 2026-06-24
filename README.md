# WebLogic Log Analyst — Claude Code Agent

Agente especializado en análisis forense de logs Oracle WebLogic para Farmatodo (CO/AR/VE).

## Setup

```bash
# 1. Clona o copia este proyecto
cd weblogic-log-analyst

# 2. Abre con Claude Code
claude

# 3. ¡Listo! El agente carga el contexto desde CLAUDE.md automáticamente
```

## Uso

### Depositar logs
```bash
# Copia tus logs al directorio logs/
cp /ruta/al/ManagedServer1.log ./logs/
```

### Comandos slash disponibles

| Comando                         | Acción                                      |
|---------------------------------|---------------------------------------------|
| `/analyze`                      | Análisis completo del log más reciente      |
| `/analyze ManagedServer1.log`   | Análisis de un log específico               |
| `/stuck-threads`                | Foco en STUCK threads y deadlocks           |
| `/oom-check`                    | Foco en OOM y problemas de memoria          |
| `/summary xstco-server1`        | Genera reporte Markdown en ./reports/       |

### Ejemplos de uso en lenguaje natural

```
# Pegar un fragmento directo en el chat:
"Aquí está el error: <BEA-000802> ..."

# Pedir análisis de archivo:
"Analiza el log de ayer del alarp014"

# Diagnóstico específico:
"¿Por qué está fallando RESA_BROADCASTER en xstco-server1?"
```

## Estructura

```
.claude/
├── settings.json      ← Permisos (qué puede ejecutar el agente)
└── commands/          ← Slash commands personalizados
    ├── analyze.md
    ├── stuck-threads.md
    ├── oom-check.md
    └── summary.md
CLAUDE.md              ← System prompt + contexto Farmatodo (se carga automáticamente)
logs/                  ← Deposita aquí tus server.log
reports/               ← Output del agente
```

## Entornos configurados

- **ARG PRD**: detectado automáticamente desde logs
- **COL PRD**: detectado automáticamente desde logs
- **VEN PRD**: detectado automáticamente desde logs
