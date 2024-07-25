## Arquitectura General

![1-sacdsp-GSN-SD](uploads/59c8d2dbf07e14cb1cecf7aa620603a7/1-sacdsp-GSN-SD.jpg)

### Arquitectura Interna DSP

![arqDspSD](uploads/363b382df170e4ccde24c012e788709d/arqDspSD.PNG)

### Flujo

Se toma la tabla remota de origen PTRF_ServiceDesk_Solicitud_00 (SASQL01_DBSD_GSN: "dbo"."GSN_Actual$") y se calendariza la carga para tenerla en memoria los miércoles luego del volcado por parte de Sistemas Colaborativos.

La tabla de origen tiene asociaciones en los campos Fecha de creación, Fecha de solución, Fecha de cierre, Fecha de rechazo con las tablas de tiempo de SAP. No tiene filtros de origen y su clave es "Solicitud".

## Schedule

![scheduleSD](uploads/e94edf6c2297ae689077822a72b92106/scheduleSD.PNG)