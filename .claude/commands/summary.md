# /summary — Reporte Ejecutivo para Infraestructura

Genera un reporte Markdown completo en `./reports/` listo para compartir con el equipo.

## Pasos

1. Determinar servidor desde el nombre del archivo o preguntar al usuario.

2. Obtener fecha actual:
   ```bash
   date +%Y-%m-%d
   ```

3. Construir el reporte con esta estructura y guardarlo:
   ```bash
   cat > "./reports/$(date +%Y-%m-%d)_${SERVIDOR}_analysis.md" << 'EOF'
   # Análisis de Log WebLogic — {SERVIDOR}
   **Fecha**: {FECHA}
   **Analista**: Claude Code Agent
   **Ambiente**: Farmatodo {CO|AR|VE} PRD

   ## Resumen Ejecutivo
   {2-3 líneas del estado general}

   ## Errores Encontrados

   | Severidad | Código/Patrón | Ocurrencias | Primera vez | Última vez |
   |-----------|---------------|-------------|-------------|------------|
   | ...       | ...           | ...         | ...         | ...        |

   ## Top Problemas

   ### 1. {Problema principal}
   - **Causa raíz**: ...
   - **Impacto**: ...
   - **Remediación**:
     ```bash
     # comando aquí
     ```

   ## Acciones Recomendadas

   - [ ] Inmediato (< 1h): ...
   - [ ] Corto plazo (< 24h): ...
   - [ ] Largo plazo: ...

   ## Comandos de Diagnóstico Adicional

   ```bash
   # Para profundizar en el problema X:
   ...
   ```
   EOF
   ```

4. Confirmar que el archivo fue creado:
   ```bash
   ls -la ./reports/
   ```

## Argumento
`$ARGUMENTS` → nombre del servidor (ej: `xstco-server1`, `alarp014`)
