# GroupOfTariffZones

A grouping of TARIFF ZONEs dedicated to a functional purpose, e.g. all the zones in a
zonal network, or a set of zones that use a specific tariff. A GROUP OF TARIFF ZONES that comprise all the zones in a network can be particulary useful when describing access rights given by fare products, e.g. a fare product allowing travel in all the zones in the network of an operator.

Sales and ticketing systems can refer to the `GroupOfTariffZones` rather than to each individual FareZone. This setup allows FareZone owners to update the included zones without requiring changes from client systems.



<details open>
<summary>
  <b>Full overview</b>
</summary>

| **Name**|**Type**|**Cardinality**|**Description** |
|-|-|-|-|
||GroupOfEntities||GROUP OF TARIFF ZONES inherits from GROUP OF ENTITIES|
|id| GroupOfTariffZonesIdType| 1:1 |Identifier of a GroupOfTariffZones|
|name|MulitilingualString|1:1|Name of the group|
|description|MulitilingualString| 0:1| Description|
|purposeOfGrouping|PurposeOfGroupingRef|1:1|The functional purpose of the grouping. In this profile the allowed values are `zonalNetwork`, `tariff`.|
|members|TariffZoneRef|0:*|The TariffZones that are included in the group|
</details>

In order to use the GroupOfTariffZone to describe fare structure and access rigths, the name is considered mandatory so that it may be presented to travellers.

TBD: The allowed values for purposeOfGrouping are `zonalNetwork`, `tariff`. They should be encoded as instances of `TypeOfValue` in a `ValueSet` and exchanged along with the data that reference them.

## Example GroupOfTariffZones

Example of a zone group with purposeOfGrouping (not all zones are included and some fields are omitted for brevity):

    {

        "id": "RUT:GroupOfTariffZones:1",
        "validBetween": [
        {
            "fromDate": "2024-01-12T13:52:29.469+01:00"
        }
    ],
        "version": "4",
        "name": {
            "value": "Alle soner",
            "lang": "nor"
    },
        "description": {
            "value": "Alle soner i Oslo og Akershus",
            "lang": "nor"
    },
        "purposeOfGroupingRef": {
            "ref": "ENT:PurposeOfGrouping:zonalNetwork"
    },
        "members": {
            "tariffZoneRef": [
            {
                "ref": "RUT:FareZone:1"
            },
            {
                "ref": "RUT:FareZone:2"
            },
            {
                "ref": "RUT:FareZone:3"
            }
            ]
        }
    }
