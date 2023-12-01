# Extracted named entities
This directory contains the entities (or “named entities”) for 906 volumes of predominantly English-language fiction authored by Native Americans and First Nations authors, as identified by Dr. Raina Heaton, Dr. Kun Lu, and Dr. Raymond I. Orr. Titles were sourced from the Native American Authors collection provided by the Internet Public Library (https://www.ipl.org/div/natam/) and The Native American Languages (NAL) collection at the Sam Noble Museum at Oklahoma University, of which Dr. Heaton is Associate Curator. 

The entities are available as two zip archives:

- `history-of-black-writing-entities.zip` contains a single `.csv` file containing all the entities for all 1997 volumes.
- `history-of-black-writing-entities-by-volume.zip` includes the same data as a separate `.csv` file for each of the 1997 volumes.

## Entity files
The entity files for each English-language SCWAReD workset were generated using [spaCy's Transformer](https://spacy.io/api/transformer) implementation and their `en_core_web_trf` transformer model, version 3.6.1. This allows us to leverage a large language model to get state-of-the-art named entity recognition (NER) results that achieve a high level of accuracy. The data was accessed and the NER pipeline was implemented using [HTRC Data Capsule](https://htrc.atlassian.net/wiki/spaces/COM/pages/43286886/HTRC+Data+Capsule+Environment) environment, with many of the books being subject to copyright, which prevents their full text from being shared and accessed directly.

For more specific technical documentation, see the "Technical documentation and reproducibility" section below.

## How to read the entity files
Each entity file has the following columns:

| Column Label     | Description |
| ----------- | ----------- |
| vol_id    | The HathiTrust ID for the source volume      |
| page   | The page on which the entity appears       |
| sentence_id   | The ID for the sentence on that page in which the entity appears        |
| ent_id   | An ID given to each unique entity, per volume        |
| entity   | The entity string, as it appears in text      |
| entity_type   | The entity type (or tag) produced by our algorithm        |
| start_char   | The number, by page, of the first character in the entity string      |
| end_char  | The number, by page, of the last character in the entity string      |

The entity types produced are standard based on the NER implementation, with the `en_core_web_trf` model, upon which our custom model is based, producing the following tags:

| Entity Label    | Description |
| ----------- | ----------- |
| CARDINAL   | Numerals not covered by other labels |
| DATE   | Dates, absolute ("May 1") or relative ("tomorrow")|
| EVENT   | Named events, such as wars, natural disasters, or sporting events |
| FAC   | Facilities, such as buildings, ports, roads |
| GPE   | Geopolitical entities, such as countries, states |
| LANGUAGE   | Named languages, real or fictional |
| LAW   | Named laws and law documents |
| LOC   | Non-GPE locations, including natural locations (oceans, mountains) |
| MONEY   | Monetary values with units |
| NORP   | Nationalities, religious or political groups |
| ORDINAL   | A number defining a position in a series (such as "first" or "second" |
| ORG   | Organizations, like companies or agencies |
| PERCENT   | Percentages, with % |
| PERSON   | Named people, real or fictional |
| PRODUCT   | Non-service products, like objects, vehicles, etc. |
| QUANTITY   | Measurements (e.g. weight, distance) |
| TIME   | Times mentioned smaller than 1 day |
| WORK_OF_ART   | Titles of named works of art |

Entities are available per-volume (via files with an HTID as their filename) or via workset (via files with a fileame corresponding to a SCWAReD workset).


## Technical documentation and reproducibility
The pipeline was developed using (version 2020.07) on Linux (via HTRC Data Capsules) with Anaconda environment for Python library management. A full Anaconda environment setup file is available in `conda-env-cuda117.yml` with additional library requirements in `pip-env-cuda117.txt`. We separate these two requirements to avoid dependency conflicts and make sure the environment is consistent on different system

To reproduce these results exactly, download this repository, including the pipeline code (in the file `en-NER-spacy.py`), as well as the predictive model using `git lfs` to support large file download. More info about `git lfs ` is available at their website: https://git-lfs.com/.

To install git lfs and pull the large files
```
git lfs install
git lfs pull
```

1. If it doesn't exist yet, create anaconda environment tor run spacy transformers model using
```
conda env create -f conda-env-cuda117.yml
```
This will create a Python environment named spacy-cuda117 that will allow the extraction execution.
The environment will be perfectly running with NVIDIA GPU available and the cuda driver 11.7 installed to access the full power.
Otherwise, the environment should still be runnable with CPU only processing.

2. Activate  the environment
```
conda activate spacy-cuda117
```

3. Make sure the anaconda environment is active by looking at the bash prompt, it should mentioned the environment like this
```
(spacy-cuda117) [someuser@somesystem en_ner]$
```
In this activated cuda117 environment and install pip requirements by executing
```
pip install --no-deps -r pip-env-cuda117.txt
```
Make sure the --no-deps is included to force installation without looking at dependency since we are using a specific library required for cuda driver 11.7

4. The data should be placed on scwared_data folder. We used compressed zip format in this case as our input data. If one want to perform this pipeline on HTRC analytics data capsule, they can modified extraction scripts or compressed the volume folder into a zip where one zip represents one volume.

5. Run the extraction script using ipython for interactivity with the bash prompt, this will read all the zip files in the scwared_data folder and create a csv file in the result_output folder
```
ipython en-NER-Spacy.py
```
