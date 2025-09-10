
# Zone to Zone fares

Prices are stated based on pairs of start zone and end zone, possibly with routing restrictions on the journey. The start-end pairs are described as DistanceMatrixElements, and the price can be given directly for each pair, regardless of the actual distance or zone traversals involved. If different routes between the same start and end zone use different prices, a routing constraint can be added as a SERIES CONSTRAINT to distinguish between the alternatives. If there are mulitiple alternative routes between start and end, where some are included in the same access right and some are not, a SERIES CONSTRAINT must be used in addition to the DistanceMatrixElement in order to achieve the required presicion in the access right description.

Required information for this use case:
- the FareZones (TransportOrganisation is required, neighbours is mandatory)
- DistanceMatrixElements, possibly with SERIES CONSTRAINTs
- A FareStructureElement type efp:access with the DistanceMAtrixElements
- A FareTable, either with DistanceMatrixElement prices, or if concessions are used, cells referencing the DistanceMatrixElement and UserProfile/GroupTicket
- Simple FareProduct and ValidableElement, and a Tariff

Variants: 
- using arbitrary distances for each origin-destination pair in the DistanceMatrixElement in combination with a stage count or distance based pricing strategy. See stage counting fares

How to buy: 
- An API should be able to give an offer based on a journey from a trip planner, start and end points from which the customer want to travel, or start and end zone from which the customer want to travel

# Zone counting fares 

(stage counting using zone as unit)


The number of zones traversed is used to determine the price. The prices are stated as intervals that each give a range of distances, so the price is independent of the specific zones travelled. To find the correct price, the distance has to be determined by examining the SERVICE PATTERN (or looking it up in a DISTANCE MATRIX ELEMENT) and then find the appropriate interval price that applies.

Must use FareZone (and not TariffZone)

TBD how to count zones, projecting a journey to the spatial layout of zones, or if only start and end of the journey is given, use the neighbour relations 
(Alternative: State the distance expressed as a GEOGRAPHICAL UNIT between the start zone and the end zone in a DistanceMatrixElement)

Required information elements for this use case:
- The zones. Must reference Authority (or Operator), and each zone must include references to its neighbour zones 
- Geographical Intervals
- A FareStructureElement with TypeOfFareStructureElement *efp:access* with the intervals
- A FareTable, either with GeographicalInterval prices, or if concessions are used, cells referencing the GeographicInterval and UserProfile/GroupTicket
- Simple FareProduct and ValidableElement, and a Tariff

The TariffType used with zone counting fares should be `unitSection`?

GEOGRAPHICAL INTERVAL, where the unit is zone. The fare is usually flat within each interval, this is what is described here. GEOGRAPHICAL INTERVAL PRICE for each interval
Often in combination with USER PROFILEs for concessions, if so use a FARE TABLE to combine the zone count and user profile to find the price.





# Flat fare for a GrupOfTariffZones

