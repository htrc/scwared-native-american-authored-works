README for workset directory

# Introduction
The `workset` directory contains multiple data files with metadata about the workset and its volumes. Details about each file, its format, and structure are included below
explain:

# `native-authored-works.csv`

This is a simple CSV file listing the volume ID and some additional metadata for each volume in the workset.

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

This is a JSON file with some basic metadata about the workset itself, including the creators of and contributors to the workset. Also included is a list of workset IDs as persistent links to the item in the [HathiTrust Digital Library](https://hathitrust.org).


# Internal notes:

<https://worksets.htrc.illinois.edu/api/worksets/https://worksets.htrc.illinois.edu/wsid/87035b50-4186-11ec-a669-0be95049ec9a/volumes?page=1&per_page=1000>

- Need to set `per-page` parameter to high enough number to get complete workset.
- Still unsure about discrepancy in number of volumes listed in `.csv` and the two different `.json` files.

Ask about the following in JSON file:

```json
"intent": {"id": "http://example.org/htrc.algorithm"},
```

Are the JSON fields documented somewhere we can point to rather than including all details in README.