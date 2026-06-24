# /stuck-threads — Análisis de STUCK Threads y Deadlocks

Foco exclusivo en hilos bloqueados. Identifica causa raíz y operación bloqueante.

## Pasos

1. Extraer todos los STUCK con contexto:
   ```bash
   grep -n -A 10 "STUCK\|BEA-000802" "$LOG" | head -200
   ```

2. Contar STUCKs por hora para ver tendencia:
   ```bash
   grep "STUCK" "$LOG" | awk '{print $1, $2}' | cut -c1-13 | sort | uniq -c
   ```

3. Identificar el ExecuteThread involucrado:
   ```bash
   grep -A5 "STUCK" "$LOG" | grep "ExecuteThread\|executeThread\|Thread-"
   ```

4. Buscar si hay deadlock explícito:
   ```bash
   grep -ni "deadlock\|circular\|waiting to lock" "$LOG"
   ```

5. Verificar si coincide con ventanas de alta carga en DB:
   ```bash
   grep -n "BEA-001129\|Cannot get.*connection\|pool.*exhausted" "$LOG"
   ```

## Output esperado
- Timeline de cuándo aparecen los STUCKs
- Operación que está colgada (DB call, HTTP call externo, etc.)
- Si es JDBC: datasource afectado
- Recomendación: timeout a configurar + Work Manager si aplica

## Argumento
`$ARGUMENTS` → archivo de log específico (opcional)
