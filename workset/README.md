README for workset directory

# Introduction
The public version of the workset is hosted by the [HathiTrust Research Center](http://analytics.hathitrust.org/) (HTRC) at <insert-link-here>.

The `workset` directory contains multiple data files with metadata about the workset and its volumes. Details about each file, its format, and structure are included below.



# `native-authored-works.csv`

This is a simple CSV file listing the volume ID and some additional metadata for each volume in the workset. The CSV file may be edited by removing and adding volume, and the edited file may used as the basis for a new workset. The full CSV file or simply a text file with a list of volume IDs may be uploaded to <insert-link-here> to create a new workset.

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

Unlike the CSV file described above, the JSON file may not be used directly in <insert-link-here> to create a new workset; however, the JSON file is the canonical source of metadata and volume IDs for the workset.







