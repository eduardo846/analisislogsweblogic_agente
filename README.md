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
| `/investigate [archivo.log]`    | Flujo multiagente: triage → especialistas → reporte |

### Flujo multiagente (`/investigate`)

```
wls-triage ──► especialistas en paralelo ──► correlación ──► wls-reporter
               ├─ wls-stuck-threads  (BEA-000802, deadlocks)
               ├─ wls-memory         (OOM, GC, Metaspace)
               ├─ wls-jdbc           (BEA-001129/1153, ORA-*, RESA_BROADCASTER)
               └─ wls-deploy-state   (BEA-149265, FAILED, transiciones)
```

El triage decide qué especialistas se lanzan según la evidencia del log. Solo `wls-reporter` escribe, y únicamente en `./reports/`.

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
├── agents/            ← Subagentes del flujo /investigate
│   ├── wls-triage.md
│   ├── wls-stuck-threads.md
│   ├── wls-memory.md
│   ├── wls-jdbc.md
│   ├── wls-deploy-state.md
│   └── wls-reporter.md
└── commands/          ← Slash commands personalizados
    ├── investigate.md
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
