## Creación de tablas de tiempo dentro del Espacio

- Dentro de Space Management, en la sección Time Data crear las tablas (solo se debe elegir el Rango de Tiempo x ej: 2000-2050):

![image](uploads/03ef45b5254292d8fdc00c7928623a7f/image.png)

- Dentro del Data Builder se ve que las tablas se crearon y agregaron al espacio:

![image](uploads/b160da68b3ce41af6694b7675b095e2c/image.png)

## Importación de tablas remotas

- Dentro del Data Builder (con la precondición de que se haya creado la conexión con la BBDD -en este caso con la Replica de Máximo en SBIRP01-) dentro del Espacio se puede importar la tabla remota:
- 
![image](uploads/45804a57063296e88b10c25685b073d1/image.png)

- Se selecciona la conexión, se eligen las tablas, se importa y se despliega.

## Conversión de datos Timestamp a Date a través de Vista intermedia

- Una vez importadas las tablas, en caso de tener datos en formato Timestamp se deberá crear una vista intermedia para poder castear y asociar estos datos a formatos de tiempo que luego nos permitan trabajar con ellos de manera directa:

- Si la vista luego tiene que ser utilizada desde un Analytic Model debe ser configurada como Fact en el Semantic Usage:

![image](uploads/ea2d0e0e6d0295ffc0582281dea459a6/image.png)

- Se importa la tabla en la vista y se crean Calculated Columns para el casteo:

![image](uploads/123affd42cf1ed9fb6d17e1b5824f767/image.png)
- Por cada fecha que se debe castear se crea una Calculated Column con Data Type “Date” y la función “TO_DATE(campo)”:

![image](uploads/7e4000058b49523c8cc3afb265a3bf87/image.png)

- Si es de tipo String hay que definir bien el formato: 

`TO_DATE('19082021', 'DDMMYYYY')`

- Workaround para fechas feas: 

`CASE "Fecha de solución" WHEN 'Sin solución' THEN NULL ELSE TO_DATE("Fecha de solución", 'DD/MM/YYYY')  END`

```
TO_TIMESTAMP(
  LPAD(TO_NVARCHAR(ID_ANO), 4, '0') ||
  LPAD(TO_NVARCHAR(ID_MES), 2, '0') ||
  LPAD(TO_NVARCHAR(ID_DIA), 2, '0') || ' ' ||
  TO_NVARCHAR(HORA), 'YYYYMMDD HH24:MI:SS'
)
```

- Luego la Calculated Column se debe asociar al campo de fecha que generamos para el espacio creando una Association por cada una:

![image](uploads/1dc2c95c7d744bb1c7410e11653e8ffe/image.png)

![image](uploads/ceb5b7464ffeeeea4837f97ccc45cd8b/image.png)

- Una vez seleccionada la “Time Dimmension - Day” se debe mapear el campo nuestro (timestamp) al Date. Se debe generar uno por cada fecha a castear:
 
![image](uploads/949d9ed9b2910c1adf3b2de3e640acdc/image.png)

## Uso de la vista intermedia en el Analytic Model

- Crear un Analytic Model y arrastrar la vista creada desde el repositorio. Elegir todas las dimensiones asociadas para tener las fechas casteadas e importar:

![image](uploads/2a4a55f8db00420d26313a14273ad1c0/image.png)

- Generar un Measure cualquiera (un distinct sirve), hacer Preview y se pueden ver las fechas en acción:

![image](uploads/2415e147ed6458a1f5c2ec749fcd3fdd/image.png)