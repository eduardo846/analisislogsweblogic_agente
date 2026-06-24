# /analyze — Análisis completo de log WebLogic

Analiza el archivo de log WebLogic especificado o el más reciente en `./logs/`.

## Pasos

1. Si no se especifica archivo, ejecuta:
   ```bash
   ls -lt ./logs/*.log | head -5
   ```
   y usa el más reciente.

2. Ejecuta el scan de patrones críticos:
   ```bash
   grep -nE "STUCK|OutOfMemoryError|BEA-000802|BEA-001129|BEA-000337|CRITICAL|deadlock|killed|RESA_BROADCASTER" "$LOG"
   ```

3. Cuenta ocurrencias por tipo:
   ```bash
   grep -oE "BEA-[0-9]+" "$LOG" | sort | uniq -c | sort -rn | head -20
   ```

4. Extrae ventana temporal del log:
   ```bash
   head -3 "$LOG" && echo "---" && tail -3 "$LOG"
   ```

5. Genera análisis estructurado con:
   - Resumen ejecutivo (2-3 líneas)
   - Tabla de errores encontrados con severidad
   - Top 3 problemas a resolver
   - Comandos de remediación

## Argumento
`$ARGUMENTS` → nombre del archivo de log (opcional). Si vacío, usa el más reciente.
