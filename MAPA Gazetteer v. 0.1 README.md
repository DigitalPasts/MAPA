MAPA Gazetteer Version 0.1 - ReadMe
-----------------------------------

The “Mesopotamian Ancient Place-names Almanac” (MAPA) is planned as a long-term
project for the historical geography of Mesopotamia in the age of Empires,
aiming to incorporate both textual and remote-sensing data for large scale
relational mapping of the landscape. The core of the project is made up of a
gazetteer of place names in texts and surveys, both on the ground and via
satellite. Names in texts will be linked to thousands of Akkadian everyday
records, that are available in multiple formats: in transliteration, as
summaries in English and German, and in English translation.

The dataset presented here in TSV and JSON formats, is the preliminary
presentation of a gazetteer drawn from legal, economic and administrative texts
from the Neo-Babylonian and Achaemenid periods, issued in and around the
Mesopotamian city of Uruk. The listed toponyms were input manually from the
books and articles in the *bibliography*. The gazetteer follows the JSON-LD
based Linked Places format
[link][https://github.com/LinkedPasts/linked-places/blob/master/tsv_0.3.md] of
the World Historical Gazetteer [link](http://whgazetteer.org/). This readme
contains a key to the database’s fields, a few issues to be resolved in future
iterations, the next steps of the MAPA project and a bibliography.

### Field Title Key

`ID` A unique numerical identifier, assigned by MongoDB to each toponym’s
document.

`site_ID` A three or four letter identifier, drawn from the document’s title. It
is generally randomly drawn from the spelling, and occasionally references type
(Nxxx for rivers and canals, for example, drawn from the Akkadian word for the
same, Nāru).

`title` The accepted spelling in contemporary academic literature, i.e. the
spelling used in reference materials.

`variant_Akkadian` The un-normalized Akkadian spelling of the toponym’s name, as
written in Akkadian texts. Searches in novel texts will often use this spelling.
This field often has numerous spellings, see Version notes below.

`type` The general type of feature under discussion. At present, simply
“settlement,” “region,” or “water.” The terminology in this field may expand or
change as understanding of the specific geography of the region increases.

`sub_type` A more specific description of the feature, as much as is possible.
This allows water-type features to be sub-divided into river, canal, channel,
and sluice, or for settlement to be divided into city, town, neighbourhood. Like
“type,” this section will expand and evolve as understanding of the region
increases through the project.

`title_source` The primary modern citation for the information in the document.
These include the citations of the texts where the places are mentioned, which
will be incorporated in the gazeetter in future versions.

`t_s_pages` For ease of querying, the pages of the entry in the above source.

`Location Notes` A text field, with notes of the feature’s location in relation
to Uruk, as recorded in the title_source text.

`Probability` The probability of the location notes specifically, and the
information in the document generally, being correct. This is according to the
information in the title_source text.

`variant_Persian` The name given to the feature in Persian sources, if it
differs from the Akkadian name.

`variant_Aramaic` The name given to the feature in Aramaic sources, if it
differs from the Akkadian name.

`variant_Modern` The modern (usually Arabic) name given to the feature, if it is
known.

`Image(s)` Citations to aerial or satellite images in which the feature is
visible. This field is relevant in later parts of the project.

`Notes` A text field which contains two types of information: any relevant facts
about the feature which don’t neatly fit into the other fields, and the specific
ways in which the features connects to the `LOC - x` (see below).

`start` The date of the earliest attestation of the feature. BCE years are
represented by negative numbers (see Version notes below).

`end` The date of the latest attestation, it is not included in this version
(see Version Notes below).

`LOC - x` These fields, up to 7 at this point, are other toponyms in the
gazetteer which are connected by a text or texts to the feature in question. The
nature of the connection is recorded in `Notes`. They are recorded here by
`site_ID`.

`ccode` The two-letter ISO country code of the location.

`CDLI` Where relevant, the CDLI [Cuneiform Digital Library
Initiative](https://cdli.ucla.edu/) provenance number.

`Pleiades` Where relevant, the Pleiades reference number
(<https://pleiades.stoa.org/>).

### Version Notes

Version 0.2 will clarify fields that contain multiple values. At present, they
are copied directly from the listed TSV, making those fields difficult to query
in JSON.

The column (in TSV) and field (in JSON) “start” refers to the earliest
attestation of the title toponym, in accordance with WHG standards. At present,
they are listed at -721, (721 BCE) the year that Merodach-Baladan II took the
throne in Babylonia. These will be corrected and expanded upon with the “end”
value (the latest attestation) as the cited texts and their dates are read and
connected to relevant toponyms in the gazetteer.

Entries in \*variant_Akkadian\* listed as “Various,” refer to multiple spellings
with scant citation in the contemporaneous literature, while “Check RGTC” refers
to an unclear or incomplete citation on the listed page. Both will be clarified
and updated to a specific spelling when the text citation process is completed.

### Project Next Steps

The immediate next step of the project is to enrich the gazetteer with data
accumulated and tagged directly from texts or text summaries. This will be
achieved by two parallel pipelines: a manual and a semi-automatic pipeline.

The manual pipeline will involve digitizing texts. The texts are entered in ATF
format, the standard digital format for cuneiform text editions (see the
[eBL-ATF
standards](https://github.com/ElectronicBabylonianLiterature/ebl-api/blob/master/docs/ebl-atf.md))
using the online Markdown editor StackEdit. Then, the relevant information, text
id, date, places and people, will be tagged
using [Recogito](https://wiki.digitalclassicist.org/Recogito). Recogito produces
TEI/XML files which can later be incorporated into the gazetter.

The semi-automatic pipeline will use texts and text summaries which are already
available in some digitized format. It will detect dates, places and people
using NER and determinatives (which are used as part of the cuneiform script).
Then, we will explore methods for automatic disambiguation of people and places,
which is still a *desideratum* for cuneiform texts. Finally, these places and
dates will be added to relevant entries in the gazetteer.

### Acknowledgments

We would like to thank Michael Jursa, Ran Zadok, Francis Joannès, and the team
at [Achemenet](http://www.achemenet.com/) for providing us with text summaries
and transliterations of texts from the relevant periods.

We would also like to extend our appreciation to our partners at
[Pelagios](https://pelagios.org/), especially Elton Barker, Gethin Rees, and
Simon Rainer, for their constant technical support and consultation.

Lastly, thanks to Karl Grossner from the World Historical Gazeetter, who
assisted us with conforming to the JSON-LD based Linked Places format.

### How to cite

Gordin, Sh. and Clark, S. 2021. MAPA Gazetteer version 0.1.
(https://github.com/DHALab/MAPA)

### Licensing

This repository is made freely available under the Attribution-ShareAlike 3.0
Unported (CC BY-SA 3.0) license. This means you are free to share and adapt the
repository, under the conditions that you cite the project appropriately, note
any changes you have made to the original repository, and if you are
redistributing the repository or a part thereof, you must release it under the
same license or a similar one.

For more information about the license, see
[here](https://creativecommons.org/licenses/by-sa/3.0/).

### Bibliography

Adams, Robert McC., and Hans J. Nissen. 1972. *The Uruk Countryside: The Natural
Setting of Urban Societies*. Chicago: University of Chicago Press.

Bagg, Ariel M. 2020. *Die Orts- und Gewässernamen der neuassyrischen Zeit, Teil
3: Babylonien, Urartu und die östlichen Gebiete*. RGTC 7, Vol. 3. Weisbaden: Dr.
Ludwing Reichert Verlag.

Ermidoro, Stefania. 2016 “New Data on the Babylonian Hydraulic Landscape: An
Update to the Répertoire Géographique des Textes Cunéiformes Vol. 8.” *Kaskal*
13: 135–74.

Zadok, Ran. *Geographical Names According to New- and Late-Babylonian Texts*.
RGTC 8. Weisbaden: Dr. Ludwing Reichert Verlag, 1985.

Zadok, Ran. 2020. “New Documents about Uruk, Its Countryside and the Sealand.”
In *DES POLYTHEISMES AUX MONOTHEISMES: Melanges d’Assyriologie Offerts a Marcel
Sigrist*, Uri Gabbay & Jean Jacques Pérennés (Eds.). Leuven: Peeters.
