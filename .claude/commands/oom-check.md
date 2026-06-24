# /oom-check — Análisis de Memoria y Garbage Collection

Detecta problemas de OOM, memory leaks y GC degradado.

## Pasos

1. Buscar errores OOM explícitos:
   ```bash
   grep -n "OutOfMemoryError\|OOM\|java.lang.OutOfMemory" "$LOG"
   ```

2. Detectar tipo de OOM:
   ```bash
   grep -n "heap space\|PermGen\|Metaspace\|GC overhead" "$LOG"
   ```

3. Buscar señales previas al OOM (GC frecuente):
   ```bash
   grep -n "GC\|garbage\|allocation.*failed" "$LOG" | tail -50
   ```

4. Revisar si hubo server restart por OOM:
   ```bash
   grep -n "killed\|FAILED\|Server.*shutdown\|JVM.*exit" "$LOG"
   ```

5. Extraer configuración de heap visible en logs:
   ```bash
   grep -n "\-Xmx\|\-Xms\|MaxHeap\|HeapSize" "$LOG" | head -5
   ```

## Output esperado
- Tipo de OOM (heap / metaspace / GC overhead)
- Momento exacto del fallo
- Tendencia previa (¿hubo warning antes?)
- Recomendaciones: flags JVM, heap dump config, herramienta de análisis

## Argumento
`$ARGUMENTS` → archivo de log o GC log específico (opcional)
