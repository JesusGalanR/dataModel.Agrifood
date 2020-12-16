Entidad: AgriParcelRecord  
=========================  
[Licencia abierta](https://github.com/smart-data-models//dataModel.Agrifood/blob/master/AgriParcelRecord/LICENSE.md)  
Descripción global: **Esta entidad contiene una descripción armonizada de las condiciones registradas en una parcela de tierra. Esta entidad se asocia principalmente con las aplicaciones verticales agrícolas y las aplicaciones de IO conexas**.  

## Lista de propiedades  

- `address`: La dirección postal.  - `alternateName`: Un nombre alternativo para este artículo  - `areaServed`: La zona geográfica en la que se presta un servicio o se ofrece un artículo  - `atmosphericPressure`: La presión atmosférica nominalmente en unidades de hectopascales  - `dataProvider`: Una secuencia de caracteres que identifica al proveedor de la entidad de datos armonizada.  - `dateCreated`: Sello de tiempo de creación de la entidad. Normalmente será asignado por la plataforma de almacenamiento.  - `dateModified`: Sello de tiempo de la última modificación de la entidad. Normalmente será asignado por la plataforma de almacenamiento.  - `depth`: Metadatos para indicar la profundidad asociada donde se toman las mediciones del suelo  - `description`: Una descripción de este artículo  - `hasAgriParcel`: Referencia a la Agri-Partida  - `hasDevice`: Referencia a los dispositivos de IO asociados a este elemento, es decir, sensores, controles.  - `id`: Identificador único de la entidad  - `leafRelativeHumidity`: La humedad relativa en la superficie de las hojas  - `leafTemperature`: La temperatura de la hoja observada nominalmente en grados centígrados  - `leafWetness`: Es un parámetro meteorológico que describe la cantidad de rocío y precipitación que queda en las superficies.  - `location`:   - `name`: El nombre de este artículo.  - `owner`: Una lista que contiene una secuencia de caracteres codificados JSON que hace referencia a los Ids únicos de los propietarios  - `relatedSource`: Lista de identificaciones que la entidad actual puede tener en aplicaciones externas  - `relativeHumidity`: Humedad Relativa un número entre 0 y 1 que representa el rango de 0% a 100%.  - `seeAlso`: lista de uri que apunta a recursos adicionales sobre el tema  - `soilMoistureEC`: Medido como Conductividad Eléctrica, EC nominalmente en unidades de Siemens por metro  - `soilMoistureVwc`: Medido como contenido volumétrico de agua, VWC como porcentaje. 0 ≤soilMoistureVwc ≤ 1  - `soilSalinity`: Es el contenido de sal en el suelo  - `soilTemperature`: La temperatura del suelo observada nominalmente en grados centígrados  - `solarRadiaton`: La radiación solar instantánea medida en kW/m2  - `source`: Una secuencia de caracteres que da como URL la fuente original de los datos de la entidad. Se recomienda que sea el nombre de dominio completamente calificado del proveedor de la fuente, o la URL del objeto fuente.  - `type`: Tipo de entidad NGSI. Tiene que ser AgriParcelRecord    
Propiedades requeridas  
- `hasAgriParcel`  - `id`  - `location`  - `type`    
Esta entidad se asocia principalmente con las aplicaciones verticales agrícolas y las aplicaciones conexas de IO.  
## Modelo de datos Descripción de las propiedades  
Ordenados alfabéticamente (haga clic para ver los detalles)  
<details><summary><strong>full yaml details</strong></summary>    
```yaml  
AgriParcelRecord:    
  description: 'This entity contains a harmonised description of the conditions recorded on a parcel of land. This entity is primarily associated with the agricultural vertical and related IoT applications.'    
  properties:    
    address:    
      description: 'The mailing address.'    
      properties:    
        addressCountry:    
          description: 'Property. The country. For example, Spain. Model:''https://schema.org/Text'''    
          type: string    
        addressLocality:    
          description: 'Property. The locality in which the street address is, and which is in the region. Model:''https://schema.org/Text'''    
          type: string    
        addressRegion:    
          description: 'Property. The region in which the locality is, and which is in the country. Model:''https://schema.org/Text'''    
          type: string    
        areaServed:    
          description: 'Property. The geographic area where a service or offered item is provided. Model:''https://schema.org/Text'''    
          type: string    
        postOfficeBoxNumber:    
          description: 'Property. The post office box number for PO box addresses. For example, Spain. Model:''https://schema.org/Text'''    
          type: string    
        postalCode:    
          description: 'Property. The postal code. For example, Spain. Model:''https://schema.org/Text'''    
          type: string    
        streetAddress:    
          description: 'Property. The street address. Model:''https://schema.org/Text'''    
          type: string    
      type: Property    
    alternateName:    
      description: 'An alternative name for this item'    
      type: Property    
    areaServed:    
      description: 'The geographic area where a service or offered item is provided'    
      type: Property    
      x-ngsi:    
        model: https://schema.org/Text    
    atmosphericPressure:    
      description: 'Atmospheric Pressure nominally in units of hecto Pascals'    
      type: Property    
      x-ngsi:    
        model: http://schema.org/Number    
        units: 'hecto Pascals'    
    dataProvider:    
      description: 'A sequence of characters identifying the provider of the harmonised data entity.'    
      type: Property    
    dateCreated:    
      description: 'Entity creation timestamp. This will usually be allocated by the storage platform.'    
      format: date-time    
      type: Property    
    dateModified:    
      description: 'Timestamp of the last modification of the entity. This will usually be allocated by the storage platform.'    
      format: date-time    
      type: Property    
    depth:    
      description: 'Metadata to indicate the associated depth where soil measurements are taken'    
      minimum: 0.0    
      type: Property    
      x-ngsi:    
        model: http://schema.org/Number    
    description:    
      description: 'A description of this item'    
      type: Property    
    hasAgriParcel:    
      anyOf:    
        - description: 'Property. Identifier format of any NGSI entity'    
          maxLength: 256    
          minLength: 1    
          pattern: ^[\w\-\.\{\}\$\+\*\[\]`|~^@!,:\\]+$    
          type: string    
        - description: 'Property. Identifier format of any NGSI entity'    
          format: uri    
          type: string    
      description: 'Reference to the AgriParcel'    
      type: Relationship    
    hasDevice:    
      description: 'Reference to the IoT devices associated with this item i.e. sensors, controls.'    
      items:    
        - anyOf: &agriparcelrecord_-_properties_-_id_-_anyof    
            - description: 'Property. Identifier format of any NGSI entity'    
              maxLength: 256    
              minLength: 1    
              pattern: ^[\w\-\.\{\}\$\+\*\[\]`|~^@!,:\\]+$    
              type: string    
            - description: 'Property. Identifier format of any NGSI entity'    
              format: uri    
              type: string    
          description: 'Property. Unique identifier of the entity'    
      type: Relationship    
      x-ngsi:    
        model: http://schema.org/URL    
    id:    
      anyOf: *agriparcelrecord_-_properties_-_id_-_anyof    
      description: 'Unique identifier of the entity'    
      type: Property    
    leafRelativeHumidity:    
      description: 'Relative humidity on the surface of the leaves'    
      maximum: 1.0    
      minimum: 0.0    
      type: Property    
      x-ngsi:    
        model: http://schema.org/Number    
    leafTemperature:    
      description: 'The observed leaf temperature nominally in degrees centigrade'    
      type: Property    
      x-ngsi:    
        model: http://schema.org/Number    
        units: 'degrees centigrade'    
    leafWetness:    
      description: 'It is a meteorological parameter that describes the amount of dew and precipitation left on surfaces.'    
      maximum: 1.0    
      minimum: 0.0    
      type: Property    
      x-ngsi:    
        model: http://schema.org/Number    
    location:    
      $id: https://geojson.org/schema/Geometry.json    
      $schema: "http://json-schema.org/draft-07/schema#"    
      oneOf:    
        - properties:    
            bbox:    
              items:    
                type: number    
              minItems: 4    
              type: array    
            coordinates:    
              items:    
                type: number    
              minItems: 2    
              type: array    
            type:    
              enum:    
                - Point    
              type: string    
          required:    
            - type    
            - coordinates    
          title: 'GeoJSON Point'    
          type: object    
        - properties:    
            bbox:    
              items:    
                type: number    
              minItems: 4    
              type: array    
            coordinates:    
              items:    
                items:    
                  type: number    
                minItems: 2    
                type: array    
              minItems: 2    
              type: array    
            type:    
              enum:    
                - LineString    
              type: string    
          required:    
            - type    
            - coordinates    
          title: 'GeoJSON LineString'    
          type: object    
        - properties:    
            bbox:    
              items:    
                type: number    
              minItems: 4    
              type: array    
            coordinates:    
              items:    
                items:    
                  items:    
                    type: number    
                  minItems: 2    
                  type: array    
                minItems: 4    
                type: array    
              type: array    
            type:    
              enum:    
                - Polygon    
              type: string    
          required:    
            - type    
            - coordinates    
          title: 'GeoJSON Polygon'    
          type: object    
        - properties:    
            bbox:    
              items:    
                type: number    
              minItems: 4    
              type: array    
            coordinates:    
              items:    
                items:    
                  type: number    
                minItems: 2    
                type: array    
              type: array    
            type:    
              enum:    
                - MultiPoint    
              type: string    
          required:    
            - type    
            - coordinates    
          title: 'GeoJSON MultiPoint'    
          type: object    
        - properties:    
            bbox:    
              items:    
                type: number    
              minItems: 4    
              type: array    
            coordinates:    
              items:    
                items:    
                  items:    
                    type: number    
                  minItems: 2    
                  type: array    
                minItems: 2    
                type: array    
              type: array    
            type:    
              enum:    
                - MultiLineString    
              type: string    
          required:    
            - type    
            - coordinates    
          title: 'GeoJSON MultiLineString'    
          type: object    
        - properties:    
            bbox:    
              items:    
                type: number    
              minItems: 4    
              type: array    
            coordinates:    
              items:    
                items:    
                  items:    
                    items:    
                      type: number    
                    minItems: 2    
                    type: array    
                  minItems: 4    
                  type: array    
                type: array    
              type: array    
            type:    
              enum:    
                - MultiPolygon    
              type: string    
          required:    
            - type    
            - coordinates    
          title: 'GeoJSON MultiPolygon'    
          type: object    
      title: 'GeoJSON Geometry'    
    name:    
      description: 'The name of this item.'    
      type: Property    
    owner:    
      description: 'A List containing a JSON encoded sequence of characters referencing the unique Ids of the owner(s)'    
      items:    
        anyOf: *agriparcelrecord_-_properties_-_id_-_anyof    
        description: 'Property. Unique identifier of the entity'    
      type: Property    
    relatedSource:    
      description: 'List of IDs the current entity may have in external applications'    
      items:    
        - type: object    
          values:    
            application:    
              anyOf: *agriparcelrecord_-_properties_-_id_-_anyof    
              description: 'Property. Unique identifier of the entity'    
            applicationEntityId:    
              type: string    
      type: Property    
    relativeHumidity:    
      description: 'Relative Humidity a number between 0 and 1 representing the range of 0% to 100%.'    
      maximum: 1.0    
      minimum: 0.0    
      type: Property    
      x-ngsi:    
        model: http://schema.org/Number    
    seeAlso:    
      description: 'list of uri pointing to additional resources about the item'    
      oneOf:    
        - items:    
            - format: uri    
              type: string    
          minItems: 1    
          type: array    
        - format: uri    
          type: string    
      type: Property    
    soilMoistureEC:    
      description: 'Measured as Electrical Conductivity, EC nominally in units of Siemens per meter'    
      type: Property    
      x-ngsi:    
        model: http://schema.org/Number    
        units: 'siemens / m'    
    soilMoistureVwc:    
      description: 'Measured as Volumetric Water Content, VWC as a percentage. 0 ≤soilMoistureVwc ≤ 1 '    
      maximum: 1    
      minimum: 0    
      type: Property    
      x-ngsi:    
        model: http://schema.org/Number    
    soilSalinity:    
      description: 'It is the salt content in the soil'    
      type: Property    
      x-ngsi:    
        model: http://schema.org/Number    
    soilTemperature:    
      description: 'The observed soil temperature nominally in degrees centigrade'    
      type: Property    
      x-ngsi:    
        model: http://schema.org/Number    
        units: 'degrees centigrade'    
    solarRadiaton:    
      description: 'Instantaneous solar radiation measured in kW/m2'    
      type: Property    
      x-ngsi:    
        model: http://schema.org/Number    
        units: kW/m2    
    source:    
      description: 'A sequence of characters giving the original source of the entity data as a URL. Recommended to be the fully qualified domain name of the source provider, or the URL to the source object.'    
      type: Property    
    type:    
      description: 'NGSI Entity Type. It has to be AgriParcelRecord'    
      enum:    
        - AgriParcelRecord    
      type: Property    
  required:    
    - id    
    - type    
    - hasAgriParcel    
    - location    
  type: object    
```  
</details>    
## Ejemplo de cargas útiles  
#### Ejemplo de valores clave de AgriParcelRecord NGSI V2  
Aquí hay un ejemplo de un AgriParcelRecord en formato JSON como valores clave. Es compatible con NGSI V2 cuando se utiliza `opciones=valores-clave` y devuelve los datos de contexto de una entidad individual.  
```json  
{  
  "id": "urn:ngsi-ld:AgriParcelRecord:8f5445e6-f49b-496e-833b-e65fc97fcab7",  
  "type": "AgriParcelRecord",  
  "dateCreated": "2017-01-01T01:20:00Z",  
  "dateModified": "2017-05-04T12:30:00Z",  
  "relatedSource": [  
    {  
      "application": "urn:ngsi-ld:AgriApp:72d9fb43-53f8-4ec8-a33c-fa931360259a",  
      "applicationEntityId": "app:parcelrec1"  
    }  
  ],  
  "seeAlso": [  
    "https://example.org/concept/agriparcelrec",  
    "https://datamodel.org/example/agriparcelrec"  
  ],  
  "hasAgriParcel": "urn:ngsi-ld:AgriParcel:d3676010-d815-468c-9e01-25739c5a25ed",  
  "location": {  
    "type": "Polygon",  
    "coordinates": [[[100, 0], [101, 0], [101, 1], [100, 1], [100, 0]]]  
  },  
  "soilTemperature": 27,  
  "soilMoistureVwc": 0.08,  
  "soilMoistureEc": 17,  
  "soilSalinity": 1198.11,  
  "leafWetness": 1.0,  
  "leafRelativeHumidity": 0.25,  
  "leafTemperature": 25.1,  
  "airTemperature": 20,  
  "solarRadiation": 15,  
  "relativeHumidity": 0.15,  
  "atmosphericPressure": 1013.25,  
  "description": "Monthly fertiliser application",  
  "hasDevice": [  
    "urn:ngsi-ld:Device:4a40aeba-4474-11e8-86bf-03d82e958ce6",  
    "urn:ngsi-ld:Device:63217d24-4474-11e8-9da2-c3dd3c36891b",  
    "urn:ngsi-ld:Device:68e091dc-4474-11e8-a398-df010c53b416",  
    "urn:ngsi-ld:6f44b54e-4474-11e8-8577-d7ff6a8ef551"  
  ],  
  "observedAt": "2017-05-04T10:18:16Z"  
}  
```  
#### AgriParcelRecord NGSI V2 normalizado Ejemplo  
Aquí hay un ejemplo de un AgriParcelRecord en formato JSON como normalizado. Es compatible con NGSI V2 cuando no se utilizan opciones y devuelve los datos de contexto de una entidad individual.  
```json  
{  
  "id": "urn:ngsi-ld:AgriParcelRecord:8f5445e6-f49b-496e-833b-e65fc97fcab7",  
  "type": "AgriParcelRecord",  
  "dateCreated": {  
    "type": "DateTime",  
    "value": "2017-01-01T01:20:00Z"  
  },  
  "dateModified": {  
    "type": "DateTime",  
    "value": "2017-05-04T12:30:00Z"  
  },  
  "relatedSource": {  
    "value": [  
      {  
        "application": "urn:ngsi-ld:AgriApp:72d9fb43-53f8-4ec8-a33c-fa931360259a",  
        "applicationEntityId": "app:parcelrec1"  
      }  
    ]  
  },  
  "seeAlso": {  
    "value": [  
      "https://example.org/concept/agriparcelrec",  
      "https://datamodel.org/example/agriparcelrec"  
    ]  
  },  
  "hasAgriParcel": {  
    "type": "Relationship",  
    "value": "urn:ngsi-ld:AgriParcel:d3676010-d815-468c-9e01-25739c5a25ed"  
  },  
  "location": {  
    "type": "geo:json",  
    "value": {  
      "type": "Polygon",  
      "coordinates": [[[100, 0], [101, 0], [101, 1], [100, 1], [100, 0]]]  
    }  
  },  
  "soilTemperature": {  
    "value": 27,  
    "metadata": {  
      "unitCode": {  
        "value": "CEL"  
      },  
      "timestamp": {  
        "type": "DateTime",  
        "value": "2017-05-04T12:30:00Z"  
      },  
      "depth": {  
        "value": {  
          "value": 20,  
          "unitCode": "CMT"  
        }  
      }  
    }  
  },  
  "soilMoistureVwc": {  
    "value": 0.08,  
    "metadata": {  
      "unitCode": {  
        "value": "C62"  
      },  
      "timestamp": {  
        "type": "DateTime",  
        "value": "2017-05-04T12:30:00Z"  
      }  
    }  
  },  
  "soilMoistureEc": {  
    "value": 17,  
    "metadata": {  
      "unitCode": {  
        "value": "D10"  
      },  
      "timestamp": {  
        "type": "DateTime",  
        "value": "2017-05-04T12:30:00Z"  
      }  
    }  
  },  
  "soilSalinity": {  
    "value": 1198.11,  
    "metadata": {  
      "unitCode": {  
        "value": "D10"  
      },  
      "timestamp": {  
        "type": "DateTime",  
        "value": "2017-05-04T12:30:00Z"  
      }  
    }  
  },  
  "leafWetness": {  
    "value": 1.0,  
    "metadata": {  
      "unitCode": {  
        "value": "P1"  
      },  
      "timestamp": {  
        "type": "DateTime",  
        "value": "2017-05-04T12:30:00Z"  
      }  
    }  
  },  
  "leafRelativeHumidity": {  
    "value": 0.25,  
    "metadata": {  
      "unitCode": {  
        "value": "P1"  
      },  
      "timestamp": {  
        "type": "DateTime",  
        "value": "2017-05-04T12:30:00Z"  
      }  
    }  
  },  
  "leafTemperature": {  
    "value": 25.1,  
    "metadata": {  
      "unitCode": {  
        "value": "CEL"  
      },  
      "timestamp": {  
        "type": "DateTime",  
        "value": "2017-05-04T12:30:00Z"  
      }  
    }  
  },  
  "airTemperature": {  
    "value": 20,  
    "metadata": {  
      "unitCode": {  
        "value": "CEL"  
      },  
      "timestamp": {  
        "type": "DateTime",  
        "value": "2017-05-04T12:30:00Z"  
      }  
    }  
  },  
  "solarRadiation": {  
    "value": 15,  
    "metadata": {  
      "unitCode": {  
        "value": "CEL"  
      },  
      "timestamp": {  
        "type": "DateTime",  
        "value": "2017-05-04T12:30:00Z"  
      }  
    }  
  },  
  "relativeHumidity": {  
    "value": 0.15,  
    "metadata": {  
      "unitCode": {  
        "value": "C62"  
      },  
      "timestamp": {  
        "type": "DateTime",  
        "value": "2017-05-04T12:30:00Z"  
      }  
    }  
  },  
  "atmosphericPressure": {  
    "value": 1013.25,  
    "metadata": {  
      "unitCode": {  
        "value": "A97"  
      },  
      "timestamp": {  
        "type": "DateTime",  
        "value": "2017-05-04T12:30:00Z"  
      }  
    }  
  },  
  "description": {  
    "value": "Monthly fertiliser application"  
  },  
  "hasDevice": {  
    "type": "Relationship",  
    "value": [  
      "urn:ngsi-ld:Device:4a40aeba-4474-11e8-86bf-03d82e958ce6",  
      "urn:ngsi-ld:Device:63217d24-4474-11e8-9da2-c3dd3c36891b",  
      "urn:ngsi-ld:Device:68e091dc-4474-11e8-a398-df010c53b416",  
      "urn:ngsi-ld:Device:6f44b54e-4474-11e8-8577-d7ff6a8ef551"  
    ]  
  },  
  "observedAt": {  
    "type": "DateTime",  
    "value": "2017-05-04T10:18:16Z"  
  }  
}  
```  
#### Ejemplo de valores clave de AgriParcelRecord NGSI-LD  
Aquí hay un ejemplo de un AgriParcelRecord en formato JSON-LD como valores clave. Es compatible con NGSI-LD cuando se utiliza `opciones=valores-clave` y devuelve los datos de contexto de una entidad individual.  
```json  
{"@context": ["https://schema.lab.fiware.org/ld/context",  
              "https://uri.etsi.org/ngsi-ld/v1/ngsi-ld-core-context.jsonld"],  
 "airTemperature": 20,  
 "atmosphericPressure": 1013.25,  
 "createdAt": "2017-01-01T01:20:00Z",  
 "description": "Monthly fertiliser application",  
 "hasAgriParcel": "urn:ngsi-ld:AgriParcel:d3676010-d815-468c-9e01-25739c5a25ed",  
 "hasDevice": ["urn:ngsi-ld:Device:4a40aeba-4474-11e8-86bf-03d82e958ce6",  
               "urn:ngsi-ld:Device:63217d24-4474-11e8-9da2-c3dd3c36891b",  
               "urn:ngsi-ld:Device:68e091dc-4474-11e8-a398-df010c53b416",  
               "urn:ngsi-ld:6f44b54e-4474-11e8-8577-d7ff6a8ef551"],  
 "id": "urn:ngsi-ld:AgriParcelRecord:8f5445e6-f49b-496e-833b-e65fc97fcab7",  
 "leafRelativeHumidity": 0.25,  
 "leafTemperature": 25.1,  
 "leafWetness": 1.0,  
 "location": {"coordinates": [[100, 0], [101, 0], [101, 1], [100, 1], [100, 0]],  
              "type": "Polygon"},  
 "modifiedAt": "2017-05-04T12:30:00Z",  
 "observedAt": {"@type": "DateTime", "@value": "2017-05-04T12:30:00Z"},  
 "relatedSource": [{"application": "urn:ngsi-ld:AgriApp:72d9fb43-53f8-4ec8-a33c-fa931360259a",  
                    "applicationEntityId": "app:parcelrec1"}],  
 "relativeHumidity": 0.15,  
 "seeAlso": ["https://example.org/concept/agriparcelrec",  
             "https://datamodel.org/example/agriparcelrec"],  
 "soilMoistureEc": 17,  
 "soilMoistureVwc": 0.08,  
 "soilSalinity": 1198.11,  
 "soilTemperature": 27,  
 "solarRadiation": 15,  
 "type": "AgriParcelRecord"}  
```  
#### AgriParcelRecord NGSI-LD normalizado Ejemplo  
Aquí hay un ejemplo de un AgriParcelRecord en formato JSON-LD normalizado. Este es compatible con NGSI-LD cuando no se utilizan opciones y devuelve los datos de contexto de una entidad individual.  
```json  
{  
	"@context": [  
		"https://schema.lab.fiware.org/ld/context",  
		"https://uri.etsi.org/ngsi-ld/v1/ngsi-ld-core-context.jsonld"  
	],  
	"id": "urn:ngsi-ld:AgriParcelRecord:8f5445e6-f49b-496e-833b-e65fc97fcab7",  
	"type": "AgriParcelRecord",  
	"createdAt": "2017-01-01T01:20:00Z",  
	"modifiedAt": "2017-05-04T12:30:00Z",  
	"relatedSource": {  
		"type": "Property",  
		"value": [{  
			"application": "urn:ngsi-ld:AgriApp:72d9fb43-53f8-4ec8-a33c-fa931360259a",  
			"applicationEntityId": "app:parcelrec1"  
		}]  
	},  
	"seeAlso": {  
		"type": "Property",  
		"value": [  
			"https://example.org/concept/agriparcelrec",  
			"https://datamodel.org/example/agriparcelrec"  
		]  
	},  
	"hasAgriParcel": {  
		"type": "Relationship",  
		"object": "urn:ngsi-ld:AgriParcel:d3676010-d815-468c-9e01-25739c5a25ed"  
	},  
	"location": {  
		"type": "GeoProperty",  
		"value": {  
			"type": "Polygon",  
			"coordinates": [  
				[  
					100,  
					0  
				],  
				[  
					101,  
					0  
				],  
				[  
					101,  
					1  
				],  
				[  
					100,  
					1  
				],  
				[  
					100,  
					0  
				]  
			]  
		}  
	},  
	"soilTemperature": {  
		"type": "Property",  
		"value": 27,  
		"unitCode": "CEL",  
		"observedAt": "2017-05-04T12:30:00Z"  
	},  
	"soilMoistureVwc": {  
		"type": "Property",  
		"value": 0.08,  
		"unitCode": "C62",  
		"observedAt": "2017-05-04T12:30:00Z",  
		"depth": {  
			"type": "Property",  
			"value": 20,  
			"unitCode": "CMT"  
		}  
	},  
	"soilMoistureEc": {  
		"type": "Property",  
		"value": 17,  
		"unitCode": "D10",  
		"observedAt": "2017-05-04T12:30:00Z"  
	},  
	"airTemperature": {  
		"type": "Property",  
		"value": 20,  
		"unitCode": "CEL",  
		"observedAt": "2017-05-04T12:30:00Z"  
	},  
	"solarRadiation": {  
		"type": "Property",  
		"value": 15,  
		"unitCode": "N78",  
		"observedAt": "2017-05-04T12:30:00Z"  
	},  
	"relativeHumidity": {  
		"type": "Property",  
		"value": 0.15,  
		"unitCode": "C62",  
		"observedAt": "2017-05-04T12:30:00Z"  
	},  
	"atmosphericPressure": {  
		"type": "Property",  
		"value": 1013.25,  
		"unitCode": "A97",  
		"observedAt": "2017-05-04T12:30:00Z"  
	},  
	"soilSalinity": {  
		"type": "Property",  
		"value": 1198.11,  
		"unitCode": "D10",  
		"observedAt": "2017-05-04T12:30:00Z"  
	},  
	"leafWetness": {  
		"type": "Property",  
		"value": 1.0,  
		"unitCode": "P1",  
		"observedAt": "2017-05-04T12:30:00Z"  
	},  
	"leafRelativeHumidity": {  
		"type": "Property",  
		"value": 0.25,  
		"unitCode": "P1",  
		"observedAt": "2017-05-04T12:30:00Z"  
	},  
	"leafTemperature": {  
		"type": "Property",  
		"value": 25.1,  
		"unitCode": "CEL",  
		"observedAt": "2017-05-04T12:30:00Z"  
	},  
	"description": {  
		"type": "Property",  
		"value": "Monthly fertiliser application"  
	},  
	"hasDevice": {  
		"type": "Relationship",  
		"object": [  
			"urn:ngsi-ld:Device:4a40aeba-4474-11e8-86bf-03d82e958ce6",  
			"urn:ngsi-ld:Device:63217d24-4474-11e8-9da2-c3dd3c36891b",  
			"urn:ngsi-ld:Device:68e091dc-4474-11e8-a398-df010c53b416",  
			"urn:ngsi-ld:6f44b54e-4474-11e8-8577-d7ff6a8ef551"  
		]  
	},  
	"observedAt": {  
		"type": "Property",  
		"value": {  
			"@type": "DateTime",  
			"@value": "2017-05-04T12:30:00Z"  
		}  
	}  
}  
```  
