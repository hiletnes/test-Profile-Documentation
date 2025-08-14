# Stop Place register

>[!TODO]
>
>**IMPORTANT TODOS: CHANGE ENTUR AND OTHER NORWEGIAN REFERANSES**
>**IMPORTANT NOTES: NOT ALL TEXT IS ADDED, AND ALL TEXT MUST BE CHECKED AND VERIFIED AS THIS IS TRANSLATED AND FORMATED BY USE OF AI**
>
>Validate if this i correct intro to StopPlace register, should it be changed or not?
>Add reference to objects and /or to [PublishStopPlace](/04-PublishData/10-PublishStopPlace.markdown) (Move to correct place)
>Add images where relevant


# Purpose of the Stop Register

- **Ensure that all existing stops are known and used consistently by all data providers.**
  - This will make it easier for operators working across regions to plan their routes.
  - It will ensure that all data providers use existing stops rather than creating their own.

- **Ensure that all data providers using the stop in their publications apply names, coordinates, and other public-facing information consistently.**
  - This is a prerequisite for calculating the shortest travel route for a traveller, as well as for calculating prices and issuing through-tickets.

- **Ensure that changes to stop data are only made by, or in agreement with, the person authorised to manage the stop.**

- **Ensure that all changes to stop information are communicated to all stakeholders.**

- **Ensure that a stop that has been closed, or for any reason cannot be served, is no longer used in route data.**

---

## 4.1 Responsibilities

The county authorities, either directly or through their administrative companies and/or licence holders, along with the Norwegian Railway Directorate, are responsible for reporting, modifying, and closing stops in Norway. This includes quays associated with the stop, coordinates, and information about the stop's design.

Their responsibilities also include ongoing maintenance of stop information in accordance with the requirements described in the profile document “stops” in the appendix *Nordic NeTEx Profile*, ensuring correct presentation in travel searches and other public-facing information.

**Entur** manages users of the register, including the assignment of relevant areas of responsibility with editing rights for stops within those areas.

Additional supplementary information regarding the stop’s connection to the road network and technical road matters, as well as relevant information related to universal design, can be found in the *National Road Data Bank (NVDB)*.

---

## 4.2 Ownership and Access

- All stops belong to a specific geographical area governed by a data provider.
- Only those with administrative responsibility may make changes to the stop.
- This typically applies per modality — for example, a data provider responsible for road-based stops will not be the same as one responsible for train or air stops.
- All users can view information stored about stops, but only edit data for stops they are responsible for.
- Certain stops or elements in the stop register may only be modified by **Entur**, typically in major city hubs where multiple transport modalities intersect.
- A stop cannot normally be closed without an explicit deadline (e.g. one calendar month) if other route operators are using the stop.

---

# 4.3 Administration of Stops

This chapter describes in more detail the administration of stops along roads, but the same process applies to other types of stops.

For stops, it is an absolute requirement that they are established in the National Stop Register before route data is allowed to use the stop. Whether a stop is served during a period is irrelevant to its status in the register, as long as the stop physically exists.

If a stop becomes practically inaccessible (e.g., the stop sign is permanently removed), it must be deactivated in the stop register so that it can no longer be used in route data.

A stop that is temporarily not served (e.g., used only by seasonal routes) does not need to be deactivated if the physical infrastructure remains permanently.

In cases where stops are established or discontinued without associated physical objects, it is still required that the stop is created/deactivated in the register according to the processes described in this chapter.

If the registered position does not match the physical position of the stop, it must be updated with correct coordinates based on official maps. This is not considered a relocation of the stop. Similarly, changing the coordinates of a Quay at a StopPlace is not considered a relocation/temporary relocation.

### General Rules for Relocation of Stops

- Correction of incorrect position for a StopPlace or Quay can be done without coordination with the road owner or triggering other information obligations.
- Temporary changes of coordinates over short distances due to roadwork or similar are not considered relocations. These should be explicitly handled in the stop register or as deviations to avoid unnecessary changes to affected route data.
  - A status or notice must be attached to the stop so the public can be informed. This is done via NeTEx Notice or SIRI SX messages.
- Temporary or permanent relocation of a stop over longer distances (each case must be individually assessed to determine if the new position is effectively a new stop) may require changes to route data for lines using the stop.

---

## 4.3.1 Establishment of Stops

New stops must correspond to physically existing infrastructure and must be established in consultation with the road owner to ensure the stop is legally and correctly placed, with naming and signage that matches the National Stop Register.

Further details on establishing stops can be found in the user manual for the National Stop Register.

---

## 4.3.2 Deactivation of Stops

A stop is deactivated if it is no longer possible for transport vehicles to serve it, and it should no longer be used in route data.

1. The stop administrator registers the end date for service in the stop register and informs the road owner.
2. From the end date, the stop is considered deactivated.
3. The road owner may physically remove the stop after the end date, including removing physical objects placed at the stop.

The stop should not be removed from the register due to historical data (e.g., statistics or ticket sales) that may still reference it. The stop may also be reinstated, such as seasonal stops where physical infrastructure is periodically removed or inaccessible. Instead, the stop should be marked with a validity date and condition information, as described for the StopPlace data object in the Nordic NeTEx Profile appendix.

After deactivation, no data providers may use the stop in their route data (until it is potentially reactivated).

---

## 4.3.3 Message Exchange

To keep stop information continuously updated, stop administrators must maintain data in the stop register. Changes should be made promptly as follows:

- All operations can be performed via a visual user interface to the stop register.
- Many operators use stops they do not administer, so they must be informed of changes. Reports of changed stops since the last report are regularly generated and distributed via email to interested parties.
  - Receipt of reports must be ordered by an administrator at Entur and can be limited to specific counties and/or municipalities.

Interested parties can also download more detailed exports from the stop register, specifying areas and types of stops. Information can also be retrieved via API or exported files published by Entur.

Messages can also be exchanged using “tags” in the stop register. These are registered by anyone with editing access and can be read by all. Tags are mainly used as notes, reminders, and change suggestions.

---

# 4.4 Naming Standard for Stops

To create a unified system where all Norwegian stops follow the same naming convention, specific requirements are set for naming.

The guidelines are based on an established convention where the owner determines the name based on rules for how it should be formulated and that it provides clear information in a national context.

---

## 4.4.1 Basic Rules

- The name of the stop is determined by the county municipality that owns the stop, in consultation with the road owner or by Bane NOR for train stations.
- The name should match the signage at the location but does not need to be written exactly the same. This allows for a harmonized register regardless of sign design.
  - Stop names in NSR may include additional words to improve the informational value of route data.
- When naming or changing names, it is generally recommended that the wording follows good language practices.
- Stop names may use local language forms and dialects, provided they comply with place naming rules (officially adopted names) from Kartverket. See also the Place Names Act §4, which public owners are required to follow. As a general rule, names with "adopted" or "approved and prioritized" status in the Central Place Name Register (SSR) should be used.
- Stop names must be unique and unambiguous in their context. Names should not be so similar that they can be confused. Context refers to stops in geographical proximity or within the same travel network.
  - There must not be two or more stops with identical names in the same municipality.
- Stop names should generally be in indefinite form (e.g., "school" instead of "the school").
- Generic stop names such as “The School,” “The Hospital,” “The Bus Station,” etc., are not allowed as they only make sense in a very local context and are not useful for national route data.

---

## 4.4.2 Structure

A stop name consists of one or more of the following elements:

| **Type** | **Code** | **Description** | **Examples** |
|----------|----------|-----------------|--------------|
| **Proper Name**<br>(Company or Institution Name) | R | The stop name is the same as the name of something nearby. The spelling is determined by the source (e.g., company or school name), but may be modified for use in stop names as long as the source remains clear (e.g., "AS" can be removed or a recognized abbreviation used). | - IKEA Ringsaker<br>- Marker Mekaniske Verksted<br>- Universitetet i Tromsø |
| **Street Name**<br>(Address Name) | V | The stop name is a street name, but not a road number (see P). | - Skredderveien<br>- E6<br>- rv. 15 |
| **Place Name** | S | The stop is named after a geographic location and must follow officially adopted or approved names. | - Pålerudfløyta<br>- Ødegårdsroa<br>- Buin |
| **Area Name** | O | A broader place name covering a larger area. Used together with Place Name (S) when more precision is needed, e.g., if several smaller places within a nearby area share the same name.<br>**Note:** Not used alone; use Place Name (S) instead when relevant. | - Drevjedalen<br>- Folldalen<br>- Stensengdalen |
| **Type Name**<br>(Functional Addition) | TF | Refers to a clear and known concept at/in a place (S). Not subject to proper name rules, but is a general type description.<br>**Note:** Not used alone.<br>Must be in indefinite form (e.g., "school", not "the school"). | - rutebilstasjon<br>- kai<br>- skole<br>- stasjon |
| **Positional Addition** | P | A name describing the location relative to a proper name or place.<br>**Note:** Not used alone. | - house number<br>- center<br>- east/west/south/north |

---

### Combinations

| **Combination** | **Description** | **Examples** |
|-----------------|-----------------|--------------|
| E | Company Name | IKEA Ringsaker |
| E + P | Specific location near a company | IKEA Ringsaker parkering |
| E + V | Specific road near a company | AMFI Narvik Markveien |
| S | Place Name | Pålerudfløyta |
| S + V | Specific road near a place | Skillebekk Trondheimsveien |
| S + O | A place within a larger area | Ødegårdsroa Snertingdalen |
| S + TF | Type of stop in a place | Stryn rutebilstasjon |
| S + P | Informal specification of location within a place | Uggdalsdalen vest |
| V | Street Name | Skredderveien |
| V + P | Specific house number along a street | Nesveien 62 |

---

### General Guidelines

- Stop names like **“Skolen”**, **“Sykehuset”**, **“Rutebilstasjonen”**, etc., should be avoided in their entirety. These must be fully named to prevent naming conflicts, as there are many schools, hospitals, and bus stations.
- It is also recommended to avoid company names as much as possible, as they may become outdated and require continuous monitoring for changes.

---

## 4.4.3 Geographical Reference

Names that relate to each other must be as specific as necessary to avoid confusion. Stops with general names (S) must not be mixed with more specific names (e.g., S+P, S+TF) in a way that causes geographical overlap with another stop.

**Example:**
In the first map excerpt, the general name “Vikersund” refers to the entire town, and the street name “Ringeriksvegen” covers a long stretch crossing the center and northern parts of the town. This causes significant overlap. In the following examples, the names are more specific and clearly indicate position.

Along roads, stop names should generally be based on intersecting roads across the driving direction, and not named after the road the route follows.

**Example:**
Stops along “Nannestadvegen” near the intersection with “Åsvegen” should be named after the intersecting road, as this provides more precise reference to the driving pattern.

If it is difficult to find a suitable name, the Language Council and the municipality should be involved.

---

## 4.4.4 Grouping of Stops

### Stops must share a common name when:
- All stops are within a clearly defined area, preferably with consistent accessibility.
- Stops are connected or otherwise arranged to support a natural cohesion in public transport context.

### Stops should share a common name when:
- All stops are physically close in a connected area or have an obvious relationship.
  - E.g., when stops are visible from each other.
- There is natural multimodality.
  - E.g., bus stops connected to an airport terminal or train station inherit the stop name from the main transport mode.

### Stops should **not** share a common name when:
- Nearby stops do not have a natural connection.
  - E.g., when it is not possible to move freely between them.
- There is a need to clearly distinguish between stops.

See also modeling examples for more details on stop structure.

---

### 4.4.4.1 Nested Stops

Larger areas where a shared stop name is desired can be nested using a parent **StopPlace** that carries the common name. Individual names can be assigned to the underlying stops. Alternatively, all stops in the nesting can have the same name, but a description text must be added.

---

## 4.4.5 Description Fields on StopPlace and Quay

The description field should always be considered a direct continuation of the stop name and must begin with a preposition and a description of the specific location. For example:

**Eidsvåg**

---

## 4.4.6 Information That Should Not Be Included in Stop Names

- Route information  
- Destination information  
- Municipality information  
- Contact information  

This type of data belongs in separate fields. The stop name should only contain the name designation for the stop.

---

## 4.4.7 Abbreviations

Abbreviations in stop names or other fields in the stop register should generally be avoided, except for the following:

- videregående skole → **vgs.** (optional)  
- riksveg → **rv.**  
- fylkesveg → **fv.**  
- kommuneveg → **kv.**

Defined abbreviations must be in lowercase and should never begin a sentence.

---

## 4.4.8 Special Characters

Allowed characters include:

- Letters  
- Numbers  
- Hyphen (-)  
- Slash (/)  
- Apostrophe (´)  
- Period (.) in abbreviations  

Other special characters such as comma, &, +, #, «», :, [ ], and ( ) are **not** allowed.

---

## 4.4.9 Road Intersections

Stops at road intersections use the following terms (other language forms are also allowed):

- **kryss**  
- **vegkryss**  
- **vegdele**

These rules do not apply to stops with proper names, such as **Sinsenkrysset**, **Gimlekrysset**, or **Madlakrossen**.

In densely built areas, intersecting street names should be used for naming whenever possible. If not feasible, use an area name (S, S+P) or describe the position with a house number (V+P). If that also fails, two street names separated by a slash (‘/’) may be used.

---

## 4.4.10 Border Crossings

### 4.4.10.1 County and Municipality Borders

Stops at county or municipal borders should not be named “County Border” unless the name is locally anchored. Instead, they should be named according to their geographical position (area name), like other stops.

### 4.4.10.2 National Borders

Stops referring to a national border must include additional information identifying the specific crossing:

- **Riksgrensen E12**  
- **Riksgrensen rv. 77**  
- **Lutnes riksgrense**

### 4.4.10.3 Stop Names in Other Languages

In NSR, all stops have a **main name field**, which is monolingual and must follow naming rules.

If a stop has a name in another language:

- If a Norwegian name exists, it must be used in the main name field.
- If no Norwegian name exists, the local name (regardless of language) is used.
- Exceptions may apply if the local name is not understandable to the general public (e.g., non-Latin script or unfamiliar terms).

**Examples:**
- Му́рманск  
- Rovaniemi linja-autoasema

Names in other languages where a Norwegian name also exists should be registered as **ALTERNATIVE NAMES**, coded as **TRANSLATION** with the appropriate language.

1. Only one translation per language is supported.  
2. Both Bokmål and Nynorsk are considered Norwegian.  
3. Unofficial non-Norwegian names should be registered as **ALIAS** with the relevant language.

Spelling of alternative names (alias, translations, etc.) should follow the same guidelines as the main name field. Local spelling should be preserved as much as possible, and the original name’s meaning or reference must be retained.

### 4.4.10.4 Sami and Kven Names in Administrative Areas

Stop names in Sami or Kven must always be registered as **alternative names** if a Norwegian name also exists. If the stop only has a non-Norwegian name, alternative names should **not** be used.

---

## 4.4.11 Name Conflicts

In cases of incompatible naming or reuse of names already assigned to existing stops, **Entur** has the authority to change the name and determine the final designation.

---

## 4.5 Stop Equipment

The administrator responsible for a stop in the register must ensure that the stop is enriched with correct information regarding:

- Universal design  
- Ticket machines  
- Information boards  
- Shelters  
- Waiting rooms, benches  
- Toilets  
- Other relevant attributes

---

## 4.6 Modeling Examples

This chapter presents different types of stops and how they should be modeled according to the structure and hierarchy guidelines in the **Nordic NeTEx Profile** appendix.

The examples are based on stops in Oslo and are sorted by complexity.

---

### 4.6.1 Stop for One Type of Transport

A common type of stop is one along a street serving a single transport mode (e.g., bus bays). These stops should be modeled as a **StopPlace** object with **two Quay** objects — one in each direction.

---
Certainly! Here's the translated and formatted version of sections **4.6.2 to 4.6.5** in **Markdown**:

---

## 4.6.2 Stop Along Street with Multiple Transport Modes

It is common for a stop to be shared by multiple transport modes, such as bus and tram, or for a bus to stop next to a metro station or a quay.

If nearby stops have the same name or can share a common overarching name, they should be nested under a parent object.

### 4.6.2.1 Example 1: Nesting of Objects – Solli plass

Modeling should be done as follows:

1. Two **StopPlace** objects, one for each transport mode (e.g., one for bus and one for tram).
2. Each transport mode has two **Quay** objects, one in each direction (total of four Quays).
   - If two transport modes stop at exactly the same position, the relevant Quays should be placed at the exact same coordinates.
3. A **parent StopPlace** to nest the two StopPlace objects. This is done technically by specifying `ParentSiteRef` for the underlying StopPlaces and pointing to the parent StopPlace. The stop register has functionality to perform this operation (see user guide).

---

## 4.6.3 Complex Stop with Multiple Transport Modes

A more complex example is **Nationaltheatret** in Oslo, which includes bus, tram, metro, and train.

Since a **StopPlace** can only have one modality, and a **Quay** can only be linked to one StopPlace, a **Multimodal StopPlace** is used.

### Example Model Structure:

- Two simple StopPlaces with two Quays each for bus and tram.
- One StopPlace with two Quays for metro.
- One StopPlace with four Quays for train tracks 1–4.
  - For trains, **BoardingPosition** can also be modeled where relevant (e.g., two positions per track, although Nationaltheatret actually has positions A–G per Quay).
- A **parent StopPlace** to combine all StopPlaces into a unified multimodal stop.

It is also possible to use a parent StopPlace to group stops with the same modality. This is useful when placing a modality icon at a location that represents all Quays is impractical, but all should share the same name.

The concept of **Adjacent Stops** is used in combined stops to link multimodal stop areas that physically overlap.

### Example:

- A tram stop with bus stops on either side may result in icons being placed at the same position, causing issues in map display. Linked stops can instead be shown with a combined icon.

---

### 4.6.3.1 Group of StopPlaces

StopPlaces can be referenced using **GroupOfStopPlaces**, which uses `StopPlaceRef` to point to stops (including parent stops). By combining this with `PurposeOfGrouping`, groupings with different use cases can be created, especially for geocoding.

---

## 4.6.4 Coordinate Placement

Coordinates for stops must be set in a standardized way to ensure consistent creation, maintenance, and error correction across all elements in the national stop register. This is done per **Quay**, so the public can see where the vehicle actually stops, according to the guidelines described here.

### 4.6.4.1 StopPlace

Generally, the **StopPlace** should be positioned midway between its underlying Quays, but adjustments are needed when:

- There are more or fewer than two Quays.
- The road is not straight, causing the center point to fall off the road.
- The stop is not a street stop (e.g., bus terminals).

For street stops, the StopPlace should be placed on the road’s centerline between the Quay positions.

- If only one Quay exists, place the StopPlace on the centerline at the Quay’s height.
- If Quays are located on different roads, place the StopPlace icon centrally (e.g., in an intersection or roundabout).
- If Quays are too spread out to define a useful midpoint, distribute them across multiple StopPlaces and combine them with a parent StopPlace.

---

### 4.6.4.2 Bus and Tram

Coordinates per Quay should match the position where the first tactile guiding line crosses the curb. If no guiding line exists, use the position of the front door of the vehicle where passengers typically board.

---

### 4.6.4.3 Air

When gates are fixed structures, coordinates per Quay should match their physical location. If gate positions are not specified, airport coordinates should be placed where they provide the most useful guidance to the public, e.g., centered on the main terminal building.

---

### 4.6.4.4 Boat

Coordinates per Quay should match the gangway/ramp where passengers or vehicles disembark.

---

### 4.6.4.5 Metro

Since most metro stops have multiple entrances, the coordinate should be placed in the middle of the platform along its length. If the platform serves two tracks, create one Quay per track/direction, even if both are served from the same platform.

---

### 4.6.4.6 Train

Railway stops generally follow the same coordinate rules per Quay as metro stops, but should be adjusted to indicate the midpoint of a typical train set when the platform is significantly longer than the train. Additionally, correct coordinates per **BoardingPosition** must be specified where marked or defined in the stop description for trains serving the stop.

---

## 4.6.5 Transfer Times and Walking Links

Data requirements for walking links, transfer rules, and similar are described in the **Nordic NeTEx Profile**, and these will be used to calculate transfer times for different passenger groups.

Note:
- Planned/guaranteed transfers must be delivered as part of route data per line-specific transfer.
- Other standard conditions used in travel time calculations and journey planner results (e.g., default transfer time or assumed walking speed) across provider data will be published.

---
