# Fares – How to Use FareZones

## Introduction to FareZones

FareZones define the geographic areas where a ticket is valid for use. They are also used to calculate the fare between two stops by counting the number of FareZones a journey passes through.  
>[!NOTE] 
>The number of FareZones a ticket is valid for may differ from the number used in fare calculation.

Each FareZone is managed by a transport authority, referenced in the `authorityRef` field. The valid area for a FareZone is described by a polygon in the `geometry` field.

FareZones must also define how they are connected using the `zoneTopology` field. Legal values is:

| ZoneTopology | Description |
|--------------|-------------|
| tiled        |             |

To calculate the price of a journey across multiple FareZones, each zone's neighbors must be specified. This is done in the `neighbours` field, which lists all neighboring FareZones separated by colons (`:`).

## Grouping of FareZones

In many cases, tickets are valid across a group of FareZones — for example, one county like **Buskerud** or a regional structure such as the **Kristiansand** area.

The FareZone owner can group these zones into a [GroupOfTariffZones](/10-Objects/GroupOfTariffZones.markdown). Sales and ticketing systems refer to the `GroupOfTariffZones` rather than to each individual FareZone. This setup allows FareZone owners to update the included zones without requiring changes from client systems.

## Object Descriptions

- [FareZone](/10-Objects/FareZone.markdown)
- [GroupOfTariffZones](/10-Objects/GroupOfTariffZones.markdown)

