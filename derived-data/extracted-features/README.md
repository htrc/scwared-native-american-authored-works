This directory contains the HTRC Extracted Features files for 906 volumes of predominantly English-language fiction authored by Native Americans and First Nations authors, as identified by Dr. Raina Heaton, Dr. Kun Lu, and Dr. Raymond I. Orr. Titles were sourced from the Native American Authors collection provided by the Internet Public Library (https://www.ipl.org/div/natam/) and The Native American Languages (NAL) collection at the Sam Noble Museum at Oklahoma University, of which Dr. Heaton is Associate Curator. There is an separate JSON file for each file. 

The file name prefix is the “clean” HathiTrust ID for the volume. See “clean” HT IDs below. 

For example the HT volume ID for the Indiana University copy of Donald Goine’s _Eldorado Red_ is `inu.30000111164251` and the corresponding JSON file is `inu.30000111164251.json.`

Each json file is compressed with open source [bzip2](http://sourceware.org/bzip2/) compression and may be uncompressed with standard compression/archive utilities available on most operation systems.

Information about each volume is contained in the metadata section of each JSON file, and the HathiTrust IDs included in the metadata can be used to gather further information about each volume.

For more information on the HTRC Extracted Features Dataset, including detailed information on the data fields in each file, see <https://doi.org/10.13012/R2TE-C227>.

## Clean HT IDs

The “clean” version of a volume ID, replaces  the following characters `:`,`/`, and `.` with `+` , `=`, and `,` respectively. 

|original volume ID character | clean volume ID character |
|:---                         | :---                      |
| `:`                         | `+`                       |
| `/`                         | `=`                       |
| `.`                         | `,`                       |

Creation date: 10 October 2023
