Entité : AgriGreenhouse  
=======================  
[Licence ouverte](https://github.com/smart-data-models//dataModel.Agrifood/blob/master/AgriGreenhouse/LICENSE.md)  
Description globale : **Cette entité contient une description harmonisée des conditions enregistrées dans une serre générique, un type d'AgriParcel.**  

## Liste des biens  

- `alternateName`: Un autre nom pour cet article  - `belongsTo`: Entité à laquelle la serre appartient  - `co2`: La concentration intérieure de C02 mesurée nominalement en mg/L  - `dailyLight`: Lumière quotidienne accumulée mesurée en kW par mètre carré  - `dataProvider`: Une séquence de caractères identifiant le fournisseur de l'entité de données harmonisées.  - `dateCreated`: Horodatage de la création de l'entité. Il est généralement attribué par la plate-forme de stockage.  - `dateModified`: Horodatage de la dernière modification de l'entité. Il est généralement attribué par la plate-forme de stockage.  - `description`: Une description de cet article  - `drainFlow`: Le débit de drainage observé en litres par seconde  - `hasAgriParcelChildren`: Enregistrements sous-agricoles connexes auxquels cette entité se rapporte  - `hasAgriParcelParent`: Référence à l'entité AgriParcel à laquelle cette entité se rapporte  - `hasDevice`: Référence aux dispositifs IoT associés à cette serre, c'est-à-dire les capteurs, les commandes.  - `hasWaterQualityObserved`: Référence à un ou plusieurs enregistrements d'observation de la qualité de l'eau en cours pour cette entité  - `hasWeatherObserved`: Référence à l'enregistrement d'observation météorologique en cours pour cette entité  - `id`: Identifiant unique de l'entité  - `leafTemperature`: L'humidité relative intérieure exprimée par un nombre entre 0 et 1 représentant la plage de 0 à 100 (%).<br/><br/>0 ≤ relativeHumidité ≤ 1  - `name`: Le nom de cet article.  - `ownedBy`: Propriétaire (personne ou organisation) de l'Agri-serre  - `owner`: Une liste contenant une séquence de caractères codés en JSON faisant référence aux Ids uniques du ou des propriétaires  - `relatedSource`: Liste des identifiants que l'entité actuelle peut avoir dans les applications externes  - `relativeHumidity`: La température moyenne de l'air des serres, en degrés centigrades.  - `seeAlso`: liste d'uri pointant vers des ressources supplémentaires sur le sujet  - `source`: Une séquence de caractères donnant comme URL la source originale des données de l'entité. Il est recommandé d'utiliser le nom de domaine complet du fournisseur de la source, ou l'URL de l'objet source.  - `type`: Type d'entité NGSI. Il doit s'agir d'AgriGreenhouse    
Propriétés requises  
- `hasAgriParcelParent`  - `id`  - `type`    
Cette entité est principalement associée aux applications verticales agricoles et aux applications IdO connexes.  
## Modèle de données description des biens  
Classement par ordre alphabétique (cliquez pour plus de détails)  
<details><summary><strong>full yaml details</strong></summary>    
```yaml  
AgriGreenhouse:    
  description: 'This entity contains a harmonised description of the conditions recorded within a generic greenhouse, a type of AgriParcel.'    
  properties:    
    alternateName:    
      description: 'An alternative name for this item'    
      type: Property    
    belongsTo:    
      anyOf:    
        - description: 'Property. Identifier format of any NGSI entity'    
          maxLength: 256    
          minLength: 1    
          pattern: ^[\w\-\.\{\}\$\+\*\[\]`|~^@!,:\\]+$    
          type: string    
        - description: 'Property. Identifier format of any NGSI entity'    
          format: uri    
          type: string    
      description: 'Entity the Greenhouse belongs to'    
      type: Relationship    
    co2:    
      description: 'The measured interior C02 concentration nominally in mg/L'    
      type: Property    
      x-ngsi:    
        model: http://schema.org/Number    
        units: mg/L    
    dailyLight:    
      description: 'Daily Accumulated light measured in kW per square metre'    
      type: Property    
      x-ngsi:    
        model: http://schema.org/Number    
        units: kw/m2    
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
    description:    
      description: 'A description of this item'    
      type: Property    
    drainFlow:    
      description: 'The observed drain flow rate in litres per second'    
      type: Property    
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
        units: L/s    
    hasAgriParcelChildren:    
      description: 'Related sub AgriParcel records to which this entity relates'    
      items:    
        - anyOf: &anyof    
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
    hasAgriParcelParent:    
      anyOf:    
        - description: 'Property. Identifier format of any NGSI entity'    
          maxLength: 256    
          minLength: 1    
          pattern: ^[\w\-\.\{\}\$\+\*\[\]`|~^@!,:\\]+$    
          type: string    
        - description: 'Property. Identifier format of any NGSI entity'    
          format: uri    
          type: string    
      description: 'Reference to the AgriParcel entity to which this entity relates'    
      type: Relationship    
    hasDevice:    
      description: 'Reference to the IoT devices associated with this greenhouse i.e. sensors, controls.'    
      items:    
        - anyOf: *anyof    
          description: 'Property. Unique identifier of the entity'    
      type: Relationship    
      x-ngsi:    
        model: http://schema.org/URL    
    hasWaterQualityObserved:    
      description: 'Reference to one or more water quality observation records current for this entity'    
      items:    
        - anyOf: *anyof    
          description: 'Property. Unique identifier of the entity'    
      type: Relationship    
    hasWeatherObserved:    
      anyOf:    
        - description: 'Property. Identifier format of any NGSI entity'    
          maxLength: 256    
          minLength: 1    
          pattern: ^[\w\-\.\{\}\$\+\*\[\]`|~^@!,:\\]+$    
          type: string    
        - description: 'Property. Identifier format of any NGSI entity'    
          format: uri    
          type: string    
      description: 'Reference to the weather observation record current for this entity'    
      type: Relationship    
    id:    
      anyOf: *anyof    
      description: 'Unique identifier of the entity'    
      type: Property    
    leafTemperature:    
      description: 'The inside relative humidity expressed as a number between 0 and 1 representing the range 0% to 100 (%).<br/><br/>0 ≤ relativeHumidity ≤ 1'    
      type: Property    
      x-ngsi:    
        model: http://schema.org/Number    
    name:    
      description: 'The name of this item.'    
      type: Property    
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
      description: 'Owner (Person or Organization) of the AgriGreenhouse'    
      type: Relationship    
    owner:    
      description: 'A List containing a JSON encoded sequence of characters referencing the unique Ids of the owner(s)'    
      items:    
        anyOf: *anyof    
        description: 'Property. Unique identifier of the entity'    
      type: Property    
    relatedSource:    
      description: 'List of IDs the current entity may have in external applications'    
      items:    
        - type: object    
          values:    
            application:    
              anyOf: *anyof    
              description: 'Property. Unique identifier of the entity'    
            applicationEntityId:    
              type: string    
      type: Property    
    relativeHumidity:    
      description: 'The average greenhouse air temperature nominally in degrees centigrade.'    
      maximum: 1.0    
      minimum: 0.0    
      type: Property    
      x-ngsi:    
        model: http://schema.org/Number    
        units: 'Degrees centigrade'    
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
    source:    
      description: 'A sequence of characters giving the original source of the entity data as a URL. Recommended to be the fully qualified domain name of the source provider, or the URL to the source object.'    
      type: Property    
    type:    
      description: 'NGSI Entity Type. It has to be AgriGreenhouse'    
      enum:    
        - AgriGreenhouse    
      type: Property    
  required:    
    - id    
    - type    
    - hasAgriParcelParent    
  type: object    
```  
</details>    
## Exemples de charges utiles  
#### Exemple de valeurs clés de l'INSG V2  
Voici un exemple d'AgriGreenhouse en format JSON comme valeurs clés. Ce format est compatible avec NGSI V2 lorsqu'on utilise "options=keyValues" et renvoie les données de contexte d'une entité individuelle.  
```json  
{  
  "id": "urn:ngsi-ld:AgriGreenhouse:df72dc57-1eb9-42a3-88a9-8647ecc954b4",  
  "type": "AgriGreenhouse",  
  "dateCreated": "2017-01-01T01:20:00Z",  
  "dateModified": "2017-05-04T12:30:00Z",  
  "ownedBy": "urn:ngsi-ld:Person:fce9dcbc-4479-11e8-9de1-cb228de7a15c",  
  "relatedSource": [  
    {  
      "application": "urn:ngsi-ld:AgriApp:72d9fb43-53f8-4ec8-a33c-fa931360259a",  
      "applicationEntityId": "app:greenhouse1"  
    }  
  ],  
  "seeAlso": [  
    "https://example.org/concept/agrigreenhouse",  
    "https://datamodel.org/example/agrigreenhouse"  
  ],  
  "belongsTo": "urn:ngsi-ld:AgriFarm:f67adcbc-4479-22bc-9de1-cb228de7a765",  
  "hasAgriParcelParent": "urn:ngsi-ld:AgriParcel:c8b475e5-84a8-4346-ad79-cde1d2a4028b",  
  "hasAgriParcelChildren": [  
    "urn:ngsi-ld:AgriParcel:8c3a525d-b42e-4048-bcdd-a119d8ddb0a5",  
    "urn:ngsi-ld:AgriParcel:178d74c1-e6fe-4042-b955-2c164fc90b83"  
  ],  
  "hasWeatherObserved": "urn:ngsi-ld:WeatherObserved:c720cec5-ac6f-40b7-8e89-becb75702d0d",  
  "hasWaterQualityObserved": [  
    "urn:ngsi-ld:WaterQualityObserved:49f86e0b-bb90-4751-a1c3-d5a891920807",  
    "urn:ngsi-ld:WaterQualityObserved:853bf420-43fc-11e8-942f-6b7615517118"  
  ],  
  "relativeHumidity": 0.4,  
  "leafTemperature": 22,  
  "co2": 28,  
  "dailyLight": 24,  
  "drainFlow": {  
    "value": 33,  
    "maxValue": 50,  
    "minValue": 25,  
    "unitText": "Litre per second"  
  },  
  "hasDevice": [  
    "urn:ngsi-ld:Device:4a40aeba-4474-11e8-86bf-03d82e958ce6",  
    "urn:ngsi-ld:Device:63217d24-4474-11e8-9da2-c3dd3c36891b",  
    "urn:ngsi-ld:Device:68e091dc-4474-11e8-a398-df010c53b416",  
    "urn:ngsi-ld:6f44b54e-4474-11e8-8577-d7ff6a8ef551"  
  ]  
}  
```  
#### AgriGreenhouse NGSI V2 normalisé Exemple  
Voici un exemple de serre agricole au format JSON normalisé. Ce format est compatible avec NGSI V2 lorsqu'il n'utilise pas d'options et renvoie les données de contexte d'une entité individuelle.  
```json  
{  
  "id": "urn:ngsi-ld:AgriGreenhouse:df72dc57-1eb9-42a3-88a9-8647ecc954b4",  
  "type": "AgriGreenhouse",  
  "dateCreated": {  
    "type": "DateTime",  
    "value": "2017-01-01T01:20:00Z"  
  },  
  "dateModified": {  
    "type": "DateTime",  
    "value": "2017-05-04T12:30:00Z"  
  },  
  "ownedBy": {  
    "type": "Relationship",  
    "value": "urn:ngsi-ld:Person:fce9dcbc-4479-11e8-9de1-cb228de7a15c"  
  },  
  "relatedSource": {  
    "value": [  
      {  
        "application": "urn:ngsi-ld:AgriApp:72d9fb43-53f8-4ec8-a33c-fa931360259a",  
        "applicationEntityId": "app:greenhouse1"  
      }  
    ]  
  },  
  "seeAlso": {  
    "value": [  
      "https://example.org/concept/agrigreenhouse",  
      "https://datamodel.org/example/agrigreenhouse"  
    ]  
  },  
  "belongsTo": {  
    "type": "Relationship",  
    "value": "urn:ngsi-ld:AgriFarm:f67adcbc-4479-22bc-9de1-cb228de7a765"  
  },  
  "hasAgriParcelParent": {  
    "type": "Relationship",  
    "value": "urn:ngsi-ld:AgriParcel:c8b475e5-84a8-4346-ad79-cde1d2a4028b"  
  },  
  "hasAgriParcelChildren": {  
    "type": "Relationship",  
    "value": [  
      "urn:ngsi-ld:AgriParcel:8c3a525d-b42e-4048-bcdd-a119d8ddb0a5",  
      "urn:ngsi-ld:AgriParcel:178d74c1-e6fe-4042-b955-2c164fc90b83"  
    ]  
  },  
  "hasWeatherObserved": {  
    "type": "Relationship",  
    "value": "urn:ngsi-ld:WeatherObserved:c720cec5-ac6f-40b7-8e89-becb75702d0d"  
  },  
  "hasWaterQualityObserved": {  
    "type": "Relationship",  
    "value": [  
      "urn:ngsi-ld:WaterQualityObserved:49f86e0b-bb90-4751-a1c3-d5a891920807",  
      "urn:ngsi-ld:WaterQualityObserved:853bf420-43fc-11e8-942f-6b7615517118"  
    ]  
  },  
  "relativeHumidity": {  
    "type": "Property",  
    "value": 0.4  
  },  
  "leafTemperature": {  
    "type": "Property",  
    "value": 22  
  },  
  "co2": {  
    "type": "Property",  
    "value": 28  
  },  
  "dailyLight": {  
    "type": "Property",  
    "value": 24  
  },  
  "drainFlow": {  
    "type": "Property",  
    "value": {  
      "value": 33,  
      "maxValue": 50,  
      "minValue": 25,  
      "unitText": "Litre per second"  
    }  
  },  
  "hasDevice": {  
    "type": "Relationship",  
    "value": [  
      "urn:ngsi-ld:Device:4a40aeba-4474-11e8-86bf-03d82e958ce6",  
      "urn:ngsi-ld:Device:63217d24-4474-11e8-9da2-c3dd3c36891b",  
      "urn:ngsi-ld:Device:68e091dc-4474-11e8-a398-df010c53b416",  
      "urn:ngsi-ld:6f44b54e-4474-11e8-8577-d7ff6a8ef551"  
    ]  
  }  
}  
```  
#### Exemple de valeurs clés de l'INSG-LD pour les serres agricoles  
Voici un exemple d'AgriGreenhouse en format JSON-LD comme valeurs clés. Il est compatible avec le format NGSI-LD lorsqu'il utilise "options=keyValues" et renvoie les données de contexte d'une entité individuelle.  
```json  
{"@context": ["https://schema.lab.fiware.org/ld/context",  
              "https://uri.etsi.org/ngsi-ld/v1/ngsi-ld-core-context.jsonld"],  
 "belongsTo": "urn:ngsi-ld:AgriFarm:f67adcbc-4479-22bc-9de1-cb228de7a765",  
 "co2": 28,  
 "createdAt": "2017-01-01T01:20:00Z",  
 "dailyLight": 24,  
 "drainFlow": {"maxValue": 50,  
               "minValue": 25,  
               "unitText": "Litre per second",  
               "value": 33},  
 "hasAgriParcelChildren": ["urn:ngsi-ld:AgriParcel:8c3a525d-b42e-4048-bcdd-a119d8ddb0a5",  
                           "urn:ngsi-ld:AgriParcel:178d74c1-e6fe-4042-b955-2c164fc90b83"],  
 "hasAgriParcelParent": "urn:ngsi-ld:AgriParcel:c8b475e5-84a8-4346-ad79-cde1d2a4028b",  
 "hasDevice": ["urn:ngsi-ld:Device:4a40aeba-4474-11e8-86bf-03d82e958ce6",  
               "urn:ngsi-ld:Device:63217d24-4474-11e8-9da2-c3dd3c36891b",  
               "urn:ngsi-ld:Device:68e091dc-4474-11e8-a398-df010c53b416",  
               "urn:ngsi-ld:6f44b54e-4474-11e8-8577-d7ff6a8ef551"],  
 "hasWaterQualityObserved": ["urn:ngsi-ld:WaterQualityObserved:49f86e0b-bb90-4751-a1c3-d5a891920807",  
                             "urn:ngsi-ld:WaterQualityObserved:853bf420-43fc-11e8-942f-6b7615517118"],  
 "hasWeatherObserved": "urn:ngsi-ld:WeatherObserved:c720cec5-ac6f-40b7-8e89-becb75702d0d",  
 "id": "urn:ngsi-ld:AgriGreenhouse:df72dc57-1eb9-42a3-88a9-8647ecc954b4",  
 "leafTemperature": 22,  
 "modifiedAt": "2017-05-04T12:30:00Z",  
 "ownedBy": "urn:ngsi-ld:Person:fce9dcbc-4479-11e8-9de1-cb228de7a15c",  
 "relatedSource": [{"application": "urn:ngsi-ld:AgriApp:72d9fb43-53f8-4ec8-a33c-fa931360259a",  
                    "applicationEntityId": "app:greenhouse1"}],  
 "relativeHumidity": 0.4,  
 "seeAlso": ["https://example.org/concept/agrigreenhouse",  
             "https://datamodel.org/example/agrigreenhouse"],  
 "type": "AgriGreenhouse"}  
```  
#### AgriGreenhouse NGSI-LD normalisé Exemple  
Voici un exemple de serre agricole au format JSON-LD normalisé. Ce format est compatible avec JSON-LD lorsqu'il n'utilise pas d'options et renvoie les données de contexte d'une entité individuelle.  
```json  
{  
    "@context": [  
        "https://schema.lab.fiware.org/ld/context",  
        "https://uri.etsi.org/ngsi-ld/v1/ngsi-ld-core-context.jsonld"  
    ],  
    "id": "urn:ngsi-ld:AgriGreenhouse:df72dc57-1eb9-42a3-88a9-8647ecc954b4",  
    "type": "AgriGreenhouse",  
    "createdAt": "2017-01-01T01:20:00Z",  
    "modifiedAt": "2017-05-04T12:30:00Z",  
    "ownedBy": {  
        "type": "Relationship",  
        "object": "urn:ngsi-ld:Person:fce9dcbc-4479-11e8-9de1-cb228de7a15c"  
    },  
    "relatedSource": {  
        "type": "Property",  
        "value": [  
            {  
                "application": "urn:ngsi-ld:AgriApp:72d9fb43-53f8-4ec8-a33c-fa931360259a",  
                "applicationEntityId": "app:greenhouse1"  
            }  
        ]  
    },  
    "seeAlso": {  
        "type": "Property",  
        "value": [  
            "https://example.org/concept/agrigreenhouse",  
            "https://datamodel.org/example/agrigreenhouse"  
        ]  
    },  
    "belongsTo": {  
        "type": "Relationship",  
        "object": "urn:ngsi-ld:AgriFarm:f67adcbc-4479-22bc-9de1-cb228de7a765"  
    },  
    "hasAgriParcelParent": {  
        "type": "Relationship",  
        "object": "urn:ngsi-ld:AgriParcel:c8b475e5-84a8-4346-ad79-cde1d2a4028b"  
    },  
    "hasAgriParcelChildren": {  
        "type": "Relationship",  
        "object": [  
            "urn:ngsi-ld:AgriParcel:8c3a525d-b42e-4048-bcdd-a119d8ddb0a5",  
            "urn:ngsi-ld:AgriParcel:178d74c1-e6fe-4042-b955-2c164fc90b83"  
        ]  
    },  
    "hasWeatherObserved": {  
        "type": "Relationship",  
        "object": "urn:ngsi-ld:WeatherObserved:c720cec5-ac6f-40b7-8e89-becb75702d0d"  
    },  
    "hasWaterQualityObserved": {  
        "type": "Relationship",  
        "object": [  
            "urn:ngsi-ld:WaterQualityObserved:49f86e0b-bb90-4751-a1c3-d5a891920807",  
            "urn:ngsi-ld:WaterQualityObserved:853bf420-43fc-11e8-942f-6b7615517118"  
        ]  
    },  
    "relativeHumidity": {  
        "type": "Property",  
        "value": 0.4,  
        "unitCode": "C62",  
        "observedAt": "2016-08-22T19:20Z"  
    },  
    "leafTemperature": {  
        "type": "Property",  
        "value": 22,  
        "unitCode": "CEL",  
        "observedAt": "2016-08-22T19:20Z"  
    },  
    "co2": {  
        "type": "Property",  
        "value": 28,  
        "unitCode": "M1",  
        "observedAt": "2016-08-22T19:20Z"  
    },  
    "dailyLight": {  
        "type": "Property",  
        "value": 24,  
        "unitCode": "N78",  
        "observedAt": "2016-08-22T19:20Z"  
    },  
    "drainFlow": {  
        "type": "Property",  
        "value": {  
            "value": 33,  
            "maxValue": 50,  
            "minValue": 25,  
            "unitText": "Litre per second"  
        },  
        "unitCode": "G51",  
        "observedAt": "2016-08-22T19:20Z"  
    },  
    "hasDevice": {  
        "type": "Relationship",  
        "object": [  
            "urn:ngsi-ld:Device:4a40aeba-4474-11e8-86bf-03d82e958ce6",  
            "urn:ngsi-ld:Device:63217d24-4474-11e8-9da2-c3dd3c36891b",  
            "urn:ngsi-ld:Device:68e091dc-4474-11e8-a398-df010c53b416",  
            "urn:ngsi-ld:6f44b54e-4474-11e8-8577-d7ff6a8ef551"  
        ]  
    }  
}  
```  
