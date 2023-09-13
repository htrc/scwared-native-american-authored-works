README for workset directory

# Introduction
The public version of the workset is hosted by the [HathiTrust Research Center](http://analytics.hathitrust.org/) (HTRC) at <https://analytics.hathitrust.org/worksets/researcher806/Native-authored%20workset>.

The `workset` directory contains multiple data files with metadata about the workset and its volumes. Details about each file, its format, and structure are included below.



# `native-authored-works.csv`

This is a simple CSV file listing the volume ID and some additional metadata for each volume in the workset. The CSV file may be edited by removing and adding volume, and the edited file may used as the basis for a new workset. The full CSV file or simply a text file with a list of volume IDs may be uploaded to <https://analytics.hathitrust.org/uploadworkset> to create a new workset.

The columns in the CSV file are:

- id (volume identifier)
- title 
- year (year of publication)
- language (volume language represented as ISO-369-3 language code) <!-- is this correct? -->
- authors

Example:

| id | title | year | language | authors |
|:---|:---   |:---  |:---      |:---     |
| pst.000032468786 | The flight of Red Bird : the life of Zitkala-S?a / re-created from the writings of Zitkala-S?a and the research of Doreen Rappaport. | 1997 | eng | Rappaport, Doreen |
| mdp.49015000024167 | No turning back; a true account of a Hopi Indian girl's struggle to bridge the gap between the world of her people and the world of the White man, | 1964 | eng | Qoyawayma, Polingaysi; Carlson, Vada F |
| mdp.39015040730916 | Infidelities / Elise Paschen. | 1996 | eng | Paschen, Elise |
| mdp.39015042815426 | Androscoggin too : the Pejepscot poems / by Robert M. Chute. | 1997 | eng | Chute, Robert M. (Robert Maurice) 1926- |
| mdp.39015041788319 | The lasting of the Mohegans : Part I, the story of the wolf people / Melissa Jayne Fawcett. | 1995 | eng | Fawcett, Melissa Jayne 1960- |

# `native-authored-works.json`

This is a [JSON-LD](https://json-ld.org) file with some basic metadata about the workset itself, including `title`, `description`, `id`, creation date (`created`), `creator`, `contributor`, and number of volumes (`extent`). Also included is a list of workset volume IDs as persistent links to the item in the [HathiTrust Digital Library](https://hathitrust.org). Here is an example of the list of volumes:

```
"gathers": [
        {"id": "http://hdl.handle.net/2027/mdp.39015033145254"},
        {"id": "http://hdl.handle.net/2027/mdp.39015064106100"},
        {"id": "http://hdl.handle.net/2027/mdp.39015043277899"},
        {"id": "http://hdl.handle.net/2027/txu.059173004704054"},
        {"id": "http://hdl.handle.net/2027/mdp.39015046352020"},
        …
                {"id": "http://hdl.handle.net/2027/mdp.39015043371890"},
        {"id": "http://hdl.handle.net/2027/uc2.ark:/13960/fk7xk8557b"},
        {"id": "http://hdl.handle.net/2027/mdp.39015030746294"}
    ]
}
```
Here is detailed information about each field in the workset JSON-LD:

|property | range | type | cardinality | description |
|:--- |:--- |:---  |:--- |:--- |
id | rdfs:Resource | URL | 1 | The URL that resolves to this document |
type | rdfs:Resource | URL | 1 | The URL representing an HTRC Workset |
dcterms:created | xsd:date | date (YYYY-MM-DD) | 1 | The unary property describing the date on which the Collection was created. |
dcterms:extent | xsd:integer | integer > 0 | 1 | The unary property describing the amount of content gathered into a Collection. |
edm:gathers | rdfs:Resource | URL | 1 or more | The relationship between a Collection and an item (Handle URL) that has been gathered into it. |
dcterms:creator | dcterms:Agent | URL or string | 0 or more | The relationship between a Collection and one or more agents responsible for its creation. (New Worksets don't have this value because HT no longer includes this info when sending Collections, but some older Worksets were created when HT was still sending over the info. JSON-LD files for SCWAReD worksets have been edited to include creator details.) |
dcterms:contributor | dcterms:Agent | URL or string | 0 or more | The property naming non-creator agent(s) responsible for contributing to creation of the collection. (Some worksets don't have this value, as contributor is reserved for worksets created with HTRC collaborators) |
dcterms:title | xsd:string | string | 1 | The unary property that captures a string value that names the Collection. |
htrc:intendedForUse | rdfs:Resource | URL | 1 or more | This relationship captures the research context in which the creator(s) intend the Collection to be used in. A Workset MUST have at least one htrc:intendedForUse relation which names the HathiTrust Research Center as a research context. A Workset MAY have additional named research contexts through additional htrc:intendedForUse relations. These contexts may be as broad as other named research centers or as narrow as particular algorithms or machine workflows. However, current workset generation tools do not allow adding additional intendedForUse values, so you can expect this to only ever have the HTRC value. |
dcterms:abstract (description) | rdfs:Resource or rdfs:Literal | URL or string | 0 or 1 | The relationship between the Collection and another resource or string of text that describes the Collection in natural language. |
htrc:hasCriterion | rdfs:Resource or rdfs:Literal | URL or string | 0 or more | This relationship captures the criterion or criteria by which the Collection creator(s) slecected respurces to gather into it. |
htrc:hasResearchMotivation | rdfs:Resource or rdfs:Literal | URL or string | 0 or more | This relationship captures the motivating question(s) that the Collection's creator(s) inted the Workset to help answer. |
dcterms:modified | xsd:date | date (YYYY-MM-DD) | 0 or 1 | The unary property describing the date on which the Collection was most recently modified. A Workset MUST have exactly 1 dcterms:modified property with a range of xsd:date if and only if it has laste been modified on a different date than the one reflected by its created date. Otherwise, a Workset MAY have 0 dcterms:modified properties (reflecting the state of affairs of having not yet been modified). |
dcterms:publisher | dcterms:Agent | URL or string | 0 or more | The relationship between a Collection and an agent who publishes it in some context. In the case of publically shared Worksets in the HTRC context, this publisher will typically be HTRC. Private Worksets remain unpublished. A Workset MAY have 1 or more dcterms:publisher relationships, of which, at least one will typically be HTRC. |
htrc:hasVisibility |  | string | 1 | The unary property that sets a Worksets to be 'public' or 'private'. Only worksets htrc:where hasVisiblity is set to 'public' are available through the API. |

|prefix | base URL |
|:--- |:--- |
dcterms | http://purl.org/dc/terms/ |
edm | http://www.europeana.eu/schemas/edm/ |
htrc | http://wcsa.htrc.illinois.edu/ |
rdfs | http://www.w3.org/2000/01/rdf-schema# |
xsd | http://www.w3.org/2001/XMLSchema# |


Unlike the CSV file described above, the JSON file may not be uploaded directly in HTRC’s existing tools to create a new workset; however, the JSON file is the canonical source of metadata and volume IDs for the workset.







