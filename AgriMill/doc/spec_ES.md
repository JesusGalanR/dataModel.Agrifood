Entidad: AgriMill
=======================
  
Descripción global: **Esta entidad contiene una descripción armonizada de las condiciones registradas dentro de una almazara genérica.  Esta entidad se ha diseñado para realizar un Trabajo de Fin de Máster asociado al Proyecto de Compra Pública INNOLIVAR de la Universidad de Córdoba.**


## Lista de propiedades    
  

Se van a almacenar datos de las principales variables de una almazara genérica y sus principales operaciones básicas:

- `address`: La dirección postal de la almazara.
- `alternateName`: Un nombre alternativo para este artículo. 
- `dataProvider`: Una secuencia de caracteres que identifica al proveedor de la entidad de datos armonizada.  
- `dateCreated`: Marca de tiempo de creación de la entidad. Suele ser asignada por la plataforma de almacenamiento.  
- `dateModified`: Marca de tiempo de la última modificación de la entidad. Normalmente será asignada por la plataforma de almacenamiento.  
- `decanterHumidity`: Humedad de masa a la salida en decánter, un número entre 0 y 1 que representa el rango de 0% a 100%.
- `decanterTemperature`: Temperatura de masa a la salida en decánter en grados centígrados.
- `description`: Una descripción de este artículo.
- `drainFlowDecanter`: Caudal de masa de aceituna que sale del decánter en kilogramos por hora.
- `drainFlowMill`: Caudal de masa de aceituna que sale del molino en kilogramos por hora.
- `electricalConductivity`: Conductividad eléctrica captada en el purgador en milisiemens por centímetro.
- `filteredOil`: Cantidad de aceite filtrado en litros.
- `filteredTemperature`: Temperatura del aceite filtrado en grados centígrados.
- `filteredTurbidity`: Turbidez del aceite filtrado en NUT.
- `foodTalcAdded`: Cantidad de talco añadido, un número entre 0 y 1 que representa el rango de 0% a 100%.
- `hasDevices`: Referencia a los dispositivos IoT asociados a esta parcela, es decir, sensores y controles. 
- `id`: Identificador único de la entidad.  
- `inputMillTemperature`: Temperatura de entrada aceituna a molino en grados centígrados.
- `location`: Referencia Geojson al elemento. Puede ser Point, LineString, Polygon, MultiPoint, MultiLineString o MultiPolygon.
- `oilFlow`: Caudal de aceite trasegado en litros por segundo.
- `oilTransferred`: Cantidad de aceite trasegado en litros a través de las bombas de trasiego.
- `oilType`: Tipo de aceite trasegado. Enum:'extraVirgin, virgin, lampante.'
- `outputMillTemperature`: Temperatura de salida de masa de molino en grados centígrados.
- `ownedBy`: Propietario (persona u organización) de la almazara.
- `pneumaticValveTime`: Tiempo de apertura de la válvula neumática del purgador en segundos.
- `pressureFilter`: Presión en el interior del filtro en bar.
- `relativeHumidity`: Humedad relativa del patio de almazara, un número entre 0 y 1 que representa el rango de 0% a 100%.
- `rpmMill`: Revoluciones por minuto del molino.
- `rpmPump`: Revoluciones por minuto de la bomba de trasiego.
- `temperature`: Temperatura del patio de almazara, normalmente en bar.
- `thermobilterPressure`: Presión de entrada de la masa en la termobatidora en grados centígrados.
- `thermobilterTemperature`: Temperatura de entrada de la masa en la termobatidora en grados centígrados.
- `type`: Tipo de entidad NGSI. Tiene que ser AgriMill.
- `unfilteredTemperature`: Temperatura de aceite sin filtrar en grados centígrados.
- `unfilteredTurbidity`: Turbidez del aceite sin filtrar en NUT.
- `waterFlowAdded`: Caudal de agua añadido en decánter en litros por segundo.
 

Propiedades requeridas  

- `id`  
- `type`

## Descripción de la estructura de datos de las propiedades  

Ordenados alfabéticamente (haga clic para ver los detalles)  
<details><summary><strong>full yaml details</strong></summary>    

```yaml  
AgriMill:    
  description: 'This entity contains a harmonised description of a generic Oil Mill. This entity is primarily associated with the agricultural vertical and related IoT applications.'    
  properties:    
    address:    
      description: 'The mailing address'    
      properties: &agrimill_-_properties_-_address_-_properties    
        addressCountry:    
          description: 'Property. The country. For example, Spain. Model:''https://schema.org/addressCountry'''    
          type: string    
        addressLocality:    
          description: 'Property. The locality in which the street address is, and which is in the region. Model:''https://schema.org/addressLocality'''    
          type: string    
        addressRegion:    
          description: 'Property. The region in which the locality is, and which is in the country. Model:''https://schema.org/addressRegion'''    
          type: string    
        postOfficeBoxNumber:    
          description: 'Property. The post office box number for PO box addresses. For example, 03578. Model:''https://schema.org/postOfficeBoxNumber'''    
          type: string    
        postalCode:    
          description: 'Property. The postal code. For example, 24004. Model:''https://schema.org/https://schema.org/postalCode'''    
          type: string    
        streetAddress:    
          description: 'Property. The street address. Model:''https://schema.org/streetAddress'''    
          type: string    
      type: object    
      x-ngsi:    
        model: https://schema.org/address    
        type: Property    
    alternateName:    
      description: 'An alternative name for this item'    
      type: string    
      x-ngsi:    
        type: Property         
    dataProvider:    
      description: 'A sequence of characters identifying the provider of the harmonised data entity.'    
      type: string    
      x-ngsi:    
        type: Property    
    dateCreated:    
      description: 'Entity creation timestamp. This will usually be allocated by the storage platform.'    
      format: date-time    
      type: string    
      x-ngsi:    
        type: Property    
    dateModified:    
      description: 'Timestamp of the last modification of the entity. This will usually be allocated by the storage platform.'    
      format: date-time    
      type: string    
      x-ngsi:    
        type: Property 
    decanterHumidity:  
      description: 'The output decanter humidity expressed as a number between 0 and 1 representing the range 0% to 100 (%).<br/><br/>0 <= decanterHumidity <= 1' 
      maximum: 1.0    
      minimum: 0.0    
      type: number    
      x-ngsi:    
        model: http://schema.org/Number    
        type: Property     
    decanterTemperature: 
      description: 'The output decanter temperature in degrees centigrade.'       
      type: number    
      x-ngsi:    
        model: http://schema.org/Number    
        type: Property    
        units: 'degrees centigrade'   
    description:    
      description: 'A description of this item'    
      type: string    
      x-ngsi:    
        type: Property 
    drainFlowDecanter: 
      description: 'The observed olive paste flow rate in kilograms per hour at the output of the decanter'    
      type: object    
      values:    
        maxValue:    
          minimum: 0    
          type: number    
        minValue:    
          minimum: 0    
          type: number    
        unitText:    
          type: string    
        value:    
          minimum: 0    
          type: number    
      x-ngsi:    
        model: http://schema.org/Number    
        type: Property    
        units: kg/h
    drainFlowmill:    
      description: 'The observed olive paste flow rate in kilograms per hour at the input of the mill'    
      type: object    
      values:    
        maxValue:    
          minimum: 0    
          type: number    
        minValue:    
          minimum: 0    
          type: number    
        unitText:    
          type: string    
        value:    
          minimum: 0    
          type: number    
      x-ngsi:    
        model: http://schema.org/Number    
        type: Property    
        units: kg/h
    electricalConductivity:      
      description: 'The oil drain electrical conductivity in millisiemens per centimeter.'       
      type: number    
      x-ngsi:    
        model: http://schema.org/Number    
        type: Property    
        units: 'mS/cm'    
    filteredOil: 
      description: 'Number of liters of olive oil filtered.'       
      type: number    
      x-ngsi:    
        model: http://schema.org/Number    
        type: Property    
        units: 'L' 
    filteredTemperature: 
      description: 'Filtered oil temperature in degrees centigrade.'
      type: number    
      x-ngsi:    
        model: http://schema.org/Number    
        type: Property    
        units: 'degrees centigrade'
    filteredTurbidity: 
      description: 'Filtered oil turbidity in NUT.'
      type: number    
      x-ngsi:    
        model: http://schema.org/Number    
        type: Property    
        units: 'NUT'
    foodTalcAdded: 
      description: 'Amount of food talc added expressed as a number between 0 and 1 representing the range 0% to 100 (%).<br/><br/>0 <= foodTalcAdded <= 1' 
      maximum: 1.0    
      minimum: 0.0    
      type: number    
      x-ngsi:    
        model: http://schema.org/Number    
        type: Property  
    hasDevices:    
      description: 'Reference to the IoT devices associated with this Oil Mill i.e. sensors, controls.'    
      items:    
        - anyOf: *anyof    
          description: 'Property. Unique identifier of the entity'    
      type: array    
      x-ngsi:    
        model: http://schema.org/URL    
        type: Relationship        
    id:    
      anyOf: *anyof    
      description: 'Unique identifier of the entity'    
      x-ngsi:    
        type: Property    
    inputMillTemperature:    
      description: 'The input mill temperature nominally in degrees centigrade.'    
      type: number    
      x-ngsi:    
        model: http://schema.org/Number    
        type: Property    
        units: 'degrees centigrade'     
    location:    
      description: 'Geojson reference to the item. It can be Point, LineString, Polygon, MultiPoint, MultiLineString or MultiPolygon'    
      oneOf: *agrimill_-_properties_-_location_-_oneof    
      x-ngsi:    
        type: Geoproperty
    oilFlow: 
      description: 'The observed oil flow rate in liters per hour at the trasnfer pump'    
      type: object    
      values:    
        maxValue:    
          minimum: 0    
          type: number    
        minValue:    
          minimum: 0    
          type: number    
        unitText:    
          type: string    
        value:    
          minimum: 0    
          type: number    
      x-ngsi:    
        model: http://schema.org/Number    
        type: Property    
        units: L/h
    oilTrasnferred:
      description: 'Number of liters of olive oil transfered.'       
      type: number    
      x-ngsi:    
        model: http://schema.org/Number    
        type: Property    
        units: 'L'
    oilType:
      description: 'Type of oil transferred into the pumps. Enum:' Enum:'extraVirgin, virgin, lampante.''
      enum:    
        - extraVirgin    
        - virgin  
        - lampante     
      type: string    
      x-ngsi:    
        type: Property    
    outputMillTemperature:    
      description: 'The output mill temperature nominally in degrees centigrade.'    
      type: number    
      x-ngsi:    
        model: http://schema.org/Number    
        type: Property    
        units: 'degrees centigrade' 
    ownedBy:    
      anyOf:    
        - description: 'Property. Identifier format of any NGSI entity'    
          maxLength: 256    
          minLength: 1    
          pattern: ^[\w\-\.\{\}\$\+\*\[\]`|~^@!,:\\]+$    
          type: string    
        - description: 'Property. Identifier format of any NGSI entity'    
          format: uri    
          type: string    
      description: 'Owner (Person or Organization) of the farm'    
      x-ngsi:    
        type: Relationship
    pneumaticValveTime: 
      description: 'Opening time of the pneumatic valve in seconds.'   
      type: number    
      x-ngsi:    
        model: http://schema.org/Number    
        type: Property    
        units: 's' 
    pressureFilter: 
      description: 'Filter pressure in bar.'   
      type: number    
      x-ngsi:    
        model: http://schema.org/Number    
        type: Property    
        units: 'bar'
    realtiveHumidity:    
      description: 'The inside relative humidity expressed as a number between 0 and 1 representing the range 0% to 100 (%).<br/><br/>0 <= relativeHumidity <= 1'    
      maximum: 1.0    
      minimum: 0.0    
      type: number    
      x-ngsi:    
        model: http://schema.org/Number    
        type: Property   
    rpmMill:    
      description: 'Revolutions per minute of the oil mill.'    
      type: number    
      x-ngsi:    
        model: http://schema.org/Number    
        type: Property    
        units: 'revolutions per minute '
    temperature:     
      description: 'The average oil mill air temperature nominally in degrees centigrade.'       
      type: number    
      x-ngsi:    
        model: http://schema.org/Number    
        type: Property    
        units: 'degrees centigrade'   
    rpmPump:
      description: 'Revolutions per minute of the oil pump.'    
      type: number    
      x-ngsi:    
        model: http://schema.org/Number    
        type: Property    
        units: 'rpm'  
    temperature:     
      description: 'The average oil mill air temperature nominally in degrees centigrade.'    
      type: number    
      x-ngsi:    
        model: http://schema.org/Number    
        type: Property    
        units: 'degrees centigrade'
    thermobilterPressure: 
      description: 'Thermobilter pressure in bar.'   
      type: number    
      x-ngsi:    
        model: http://schema.org/Number    
        type: Property    
        units: 'bar'
    thermobilterTemperature: 
      description: 'Thermobilter temperature in degrees centigrade.'   
      type: number    
      x-ngsi:    
        model: http://schema.org/Number    
        type: Property    
        units: 'degrees centigrade' 
    type:    
      description: 'NGSI Entity Type. It has to be AgriMill'    
      enum:    
        - AgriMill   
      type: string    
      x-ngsi:    
        type: Property
    unfilteredTemperature: 
      description: 'Unfiltered oil temperature in degrees centigrades.'   
      type: number    
      x-ngsi:    
        model: http://schema.org/Number    
        type: Property    
        units: 'degrees centigrade' 
    unfilteredTurbidity: 
      description: 'Unfiltered oil turbidity in NUT.'
      type: number    
      x-ngsi:    
        model: http://schema.org/Number    
        type: Property    
        units: 'NUT'
    waterFlowAdded: 
      description: 'The observed water flow rate added in kilograms per hour added to the decanter'    
      type: object    
      values:    
        maxValue:    
          minimum: 0    
          type: number    
        minValue:    
          minimum: 0    
          type: number    
        unitText:    
          type: string    
        value:    
          minimum: 0    
          type: number    
      x-ngsi:    
        model: http://schema.org/Number    
        type: Property    
        units: L/h
  required:    
    - id    
    - type    
  type: object    
  x-derived-from: ""    
  x-disclaimer: 'Redistribution and use in source and binary forms, with or without modification, are permitted  provided that the license conditions are met. Copyleft (c) 2021 Contributors to Smart Data Models Program'    
  x-license-url: https://github.com/smart-data-models/dataModel.Agrifood/blob/master/AgriMill/LICENSE.md    
  x-model-schema: https://smart-data-models.github.io/dataModel.Agrifood/AgriMill/schema.json    
  x-model-tags: ""    
  x-version: 0.0.2    
```  
</details>    
