Entidad: AgriMill
=======================
  
Descripción global: **Esta entidad contiene una descripción armonizada de las condiciones registradas dentro de una almazara genérica.  Esta entidad se ha diseñado para realizar un Trabajo de Fin de Máster asociado al Proyecto de Compra Pública INNOLIVAR de la Universidad de Córdoba.**


## Lista de propiedades    
  

Se van a almacenar datos de las principales variables de de una almazara genérica y operación de molienda:

- `address`: La dirección postal de la almazara.
- `alternateName`: Un nombre alternativo para este artículo  
- `dataProvider`: Una secuencia de caracteres que identifica al proveedor de la entidad de datos armonizada.  
- `dateCreated`: Marca de tiempo de creación de la entidad. Suele ser asignada por la plataforma de almacenamiento.  
- `dateModified`: Marca de tiempo de la última modificación de la entidad. Normalmente será asignada por la plataforma de almacenamiento.  
- `description`: Una descripción de este artículo.
- `drainFlowMill`: Caudal de masa de aceituna que sale del molino.
- `hasDevices`: Referencia a los dispositivos IoT asociados a esta parcela, es decir, sensores y controles. 
- `id`: Identificador único de la entidad.  
- `inputMillTemperature`: Temperatura de entrada aceituna a molino en grados centígrados
- `location`: Referencia Geojson al elemento. Puede ser Point, LineString, Polygon, MultiPoint, MultiLineString o MultiPolygon 
- `outputMillTemperature`: Temperatura de salida de masa de molino en grados centígrados
- `temperature`: Temperatura del patio de almazara, normalmente en grados centígrados.
- `ownedBy`: Propietario (persona u organización) de la almazara.
- `relativeHumidity`: Humedad relativa del patio de almazara un número entre 0 y 1 que representa el rango de 0% a 100%.
- `rpmMill`: Revoluciones por minuto del molino.
- `type`: Tipo de entidad NGSI. Tiene que ser AgriMill.
 

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
    description:    
      description: 'A description of this item'    
      type: string    
      x-ngsi:    
        type: Property    
    drainFlowmill:    
      description: 'The observed drain flow rate in litres per second at the input of the mill'    
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
        units: L/s    
    hasDevice:    
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
      maximum: 1.0    
      minimum: 0.0    
      type: number    
      x-ngsi:    
        model: http://schema.org/Number    
        type: Property    
        units: 'Degrees centigrade'       
    location:    
      description: 'Geojson reference to the item. It can be Point, LineString, Polygon, MultiPoint, MultiLineString or MultiPolygon'    
      oneOf: *agrifarm_-_properties_-_location_-_oneof    
      x-ngsi:    
        type: Geoproperty   
    outputMillTemperature:    
      description: 'The output mill temperature nominally in degrees centigrade.'    
      maximum: 1.0    
      minimum: 0.0    
      type: number    
      x-ngsi:    
        model: http://schema.org/Number    
        type: Property    
        units: 'Degrees centigrade'
    Temperature:    
      description: 'The average oil mill air temperature nominally in degrees centigrade.'    
      maximum: 1.0    
      minimum: 0.0    
      type: number    
      x-ngsi:    
        model: http://schema.org/Number    
        type: Property    
        units: 'Degrees centigrade'     
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
    realtiveHumidity:    
      description: 'The inside relative humidity expressed as a number between 0 and 1 representing the range 0% to 100 (%).<br/><br/>0 <= relativeHumidity <= 1'    
      type: integer    
      x-ngsi:    
        model: http://schema.org/Number    
        type: Property
    rpmMill:    
      description: 'Revolutions per minute of the oil mill.'    
      maximum: 3500.0    
      minimum: 1500.0  
      type: number    
      x-ngsi:    
        model: http://schema.org/Number    
        type: Property    
        units: 'revolutions per minute '           
    type:    
      description: 'NGSI Entity Type. It has to be AgriFarm'    
      enum:    
        - AgriFarm    
      type: string    
      x-ngsi:    
        type: Property    
  required:    
    - id    
    - type    
  type: object    
  x-derived-from: ""    
  x-disclaimer: 'Redistribution and use in source and binary forms, with or without modification, are permitted  provided that the license conditions are met. Copyleft (c) 2021 Contributors to Smart Data Models Program'    
  x-license-url: https://github.com/smart-data-models/dataModel.Agrifood/blob/master/AgriFarm/LICENSE.md    
  x-model-schema: https://smart-data-models.github.io/dataModel.Agrifood/AgriFarm/schema.json    
  x-model-tags: ""    
  x-version: 0.0.2    
```  
</details>    
