# Farmatodo WebLogic Environment Reference

Consulta esta referencia solo cuando sea necesario identificar un host, dominio o versión. Las etiquetas `PRD`, `QA` y `DEV` forman parte del ambiente.

## Producción

| Ambiente | Servicio | Hosts | Versión | Dominio |
|---|---|---|---|---|
| AR PRD | EBS | ALARP000-001 | 10.3.6.0 | EBS_domain |
| AR PRD | ODI | ALARP002-003 | 12.2.1.2.0 | odiprdar_domain |
| AR PRD | FTS / Portal Item | ALARP004-005 | 12.2.1.4.0 / 14.1.1.0.0 | ftsprdar_domain / piprd_domain |
| AR PRD | BIP | ALARP006-007 | 12.2.1.3.0 | bipprdar_domain |
| AR PRD | ATOM | ALARP008-009 | 12.2.1.4.0 | atomprdar_domain |
| AR PRD | RPM | ALARP010-011 | 12.2.1.2.0 | rpmco_domain |
| AR PRD | REIM | ALARP012-013 | 12.2.1.2.0 | reimco_domain |
| AR PRD | RESA / RMS | ALARP014-015 | 12.2.1.2.0 | resaco_domain / rmsco_domain |
| AR PRD | SIM | ALARP016-017 | 12.2.1.3.0 | simco_domain |
| AR PRD | XOFFICE | ALARP018-019 | 12.2.1.3.0 | xstco_domain |
| AR PRD | RIB | ALARP020 | 12.2.1.2.0 | ribprdar_domain |
| AR PRD | WMS | ALARP030 | 12.2.1.2.0 | rwmsco_domain |
| CO PRD | ALLOC | ALCOP000-001 | 12.2.1.2.0 | allocco_domain |
| CO PRD | RPM | ALCOP002-003 | 12.2.1.2.0 | rpmco_domain |
| CO PRD | REIM | ALCOP004-005 | 12.2.1.2.0 | reimco_domain |
| CO PRD | RESA / RMS | ALCOP006-007 | 12.2.1.2.0 | resaco_domain / rmsco_domain |
| CO PRD | SIM | ALCOP008-009 | 12.2.1.3.0 | simco_domain |
| CO PRD | WMS | ALCOP022-023 | 12.2.1.2.0 | rwmsco_domain |
| CO PRD | ODI-RDE / ODI-RI / OBIEE | ALCOP010-011 | 12.2.1.2.0 | ODIRDEDomain / ODIRIDomain / BIDomain |
| CO PRD | OID | ALCOP012-013 | 10.3.6.0 | oidm_domain |
| CO PRD | RIB / RIHA | ALCOP014 | 12.2.1.2.0 | ribco-domain |
| CO PRD | BIP | ALCOP016 | 10.3.6.0 | bipco-domain |
| CO PRD | FTS / Portal Item | ALCOP018-019 | 12.2.1.2.0 / 14.1.1.0.0 | ftsbaseco_domain / piprd_domain |
| CO PRD | XOFFICE | ALCOP024-025 | 12.2.1.3.0 | xstco_domain |
| CO PRD | BIP ETIQ | ALCOP028 | 12.2.1.2.0 | bipcoe_domain |
| CO PRD | ATOM | ALCOP030-031 | 12.2.1.2.0 | atomco_domain |
| CO PRD | ODI-INT | ALCOP032-033 | 12.2.1.2.0 | odiico_domain |
| VE PRD | GEPE | ALVEP000 | 10.3.6.0 | rrhh_prd |
| VE PRD | FTS / Portal Item | ALVEP039-040 | 12.2.1.3.0 / 14.1.1.0.0 | ftsbaseve_domain / piprd_domain |
| VE PRD | ODI INT | ALVEP041-042 | 12.2.1.2.0 | odiive_domain |
| VE PRD | ATOM | ALVEP043-044 | 12.2.1.2.0 | atomve_domain |
| VE PRD | XOFFICE | ALVEP045-046 | 12.2.1.3.0 | xstve_domain |
| VE PRD | WMS | ALVEP047-048 | 12.2.1.2.0 | rwmsprdve_domain |
| VE PRD | BIP ETIQ | ALVEP049-050 | 12.2.1.2.0 | bipeve_domain |
| VE PRD | RIB | ALVEP056 | 12.2.1.2.0 | ribve_domain |
| VE PRD | BDOS | ALVEP062-063, 066-069 | 12.2.1.4.0 | bdos_rehub_prd / bdos_prd |
| VE PRD | OBIEE | ALVEO070, ALVEP071 | 12.2.1.2.0 | BIDomain |
| VE PRD | ODI DWH | ALVEP075 | 12.2.1.4.0 | ODI_DWHPRD_Domain |
| VE PRD | SIM | ALVEP084-085 | 12.2.1.3.0 | simve_domain |
| VE PRD | RPM | ALVEP086-087 | 12.2.1.2.0 | rpmve_domain |
| VE PRD | REIM | ALVEP088-089 | 12.2.1.2.0 | reimve_domain |
| VE PRD | RESA / RMS | ALVEP090-091 | 12.2.1.2.0 | resave_domain / rmsve_domain |
| VE PRD | ALLOC | ALVEP092-093 | 12.2.1.2.0 | allocve_domain |
| VE PRD | BIP | ALVEP094-095 | 12.2.1.3.0 | bipprdve_domain |

## QA y desarrollo

| Ambiente | Servicios y hosts principales |
|---|---|
| AR QA | ODI alard301; FTS alard302; BIP alard303; ATOM alard304; RPM alard305; SIM alard306; XCENTER alard307; RIB alard309; REIM alard310; RESA alard311; ODI dev alard501; PIQA alard302 |
| CO QA | ALLOC alcod300-301; RPM alcod302-303; REIM alcod304-305; RESA alcod306-307; SIM alcod308-309; ODI alcod310; OID alcod312-313; RIB alcod314; BIP alcod316; FTS/PIQ alcod318-319; WMS alcod322; XCENTER alcod324-325; ATOM alcod326-327; ODI 508 ALCOD508 |
| VE QA | FTS alved333-334; ODI alved335-336; ATOM alved337-338; XCENTER alved339-340; WMS alved341-342; RIB alved349; BIP ETIQ alved351; OBIEE alved357; SIM alved369; RPM alved373; REIM alved374; RESA/RMS alved375; ALLOC alved376; BDOS alved355-356; BDOS dev/rehub alved505; ALLOC alved393; Portal Item alved333 |

Cuando un host aparece en más de un servicio, usa el nombre del dominio y el nombre del log para desambiguar antes de atribuir el incidente.
