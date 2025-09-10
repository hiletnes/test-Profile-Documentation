# Geographical Interval

A `GeographicalInterval` specifies the right to travel a distance that lies within the range of the interval. The distance is given in a specific unit, e.g. 0-5 km, 4-6 zones, etc. The price can be stated for the interval by use of a Cell in a FareTable, or be further adjusted by combining the interval with a `GeographicStructureFactor` to associate a price per unit with the interval, e.g. price per kilometer.

> [!Note] 
> In this profile, only the option of `GeographicalInterval` is available. The combination of `GeographicalInterval` with a `GeographicalStructureFactor` is left to an advanced profile.

The `GeographicalInterval`s that state the possible interval options for a fare product shall be included in a `FareStructureElement` with the correct typing `efp:access`.


| **Name**|**Type**|**Cardinality**|**Description** |
|-|-|-|-|
||GeographicalInterval inherits from FareInterval (abstract)||
|Id| GeographicalIntervalIdType | 1:1| Identifier of GeographicalInterval | 
|StartGeographicalValue|xsd:decimal|0:1|Start value for Geographical Interval|
|EndGeographicalValue|xsd:decimal|0:1|End value for Geographical Interval|
|NumberOfUnits|xsd:integer|0:1|Number of units in Interval|
|IntervalType|IntervalTypeEnum|***1***:1|Classification of interval type. Allowed values: stop, tariffZone, distance, section, coupon, other|
|GeographicalUnitRef|GeographicalUnitRef|0:1|The unit used in the interval|
|~~prices~~|~~GeographicalIntervalPrice~~|~~0:*~~|~~Prices for the geographical interval~~ as in EFIP, use FareTable and Cell Price only|


### Geographical Unit
A unit for calculating geographical graduated fares

| **Name**|**Type**|**Cardinality**|**Description** |
|-|-|-|-|
||GeographicalUnit inherits from FareUnit (abstract)||
|Id| GeographicalUnitIdType | 1:1| Identifier of GeographicalUnit |
|Distance|DistanceType|0:1|If distance-based, length of unit in SI metres, e.g 1 nautical mile is 1852 metres| 
|~~prices~~|~~GeographicalUnitPrice~~|~~0:*~~|~~Prices associated with the geographical unit~~|

### TODOs
- [ ] Describe FareInterval? Abstract, no attributes, ok to leave it out?
- [ ] Describe FareUnit and GeographicalUnitRef - if this is only used in combination with GeographicalStructureFacor, should we leave it out?
- [ ] State how prices should be given - use both Cell prices and GeographicalIntervalPrices or Cell prices only?