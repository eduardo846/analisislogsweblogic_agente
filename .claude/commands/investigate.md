# /investigate — Flujo multiagente de análisis WebLogic

Orquesta subagentes especializados: triage → especialistas en paralelo → reporte.

## Pasos

1. **Triage.** Lanza el subagente `wls-triage` con el log indicado en `$ARGUMENTS` (o sin ruta para que use el más reciente de `./logs/`). Espera su resultado.

2. **Especialistas en paralelo.** Según la sección "Especialistas recomendados" del triage, lanza en un solo mensaje (para que corran en paralelo) los que apliquen:
   - `wls-stuck-threads`
   - `wls-memory`
   - `wls-jdbc`
   - `wls-deploy-state`

   A cada uno pásale la ruta del log y el resumen completo del triage. Si el triage no encontró hallazgos críticos, omite este paso e indícalo.

3. **Correlación.** Revisa las salidas: cruza timestamps entre especialistas (p. ej. STUCK coincidiendo con BEA-001129) y señala contradicciones o citas dudosas. Si una cita parece incorrecta, verifícala con `sed -n '<línea>p' <log>`.

4. **Reporte.** Lanza `wls-reporter` con el triage, las salidas de los especialistas y tus notas de correlación.

5. **Respuesta al usuario.** Presenta el resultado con el formato de respuesta de `CLAUDE.md` (Estado general, hallazgos por severidad con archivo y línea, acciones inmediatas, diagnóstico adicional, nivel de confianza) y la ruta del reporte generado.

## Reglas

- Todo el flujo es de solo lectura sobre los logs; solo `wls-reporter` escribe, y únicamente en `./reports/`.
- No propongas reinicio como primera acción. Las acciones que afectan producción van marcadas con ⚠️ y requieren confirmación.

## Argumento
`$ARGUMENTS` → archivo de log (opcional). Si vacío, usa el más reciente de `./logs/`.
