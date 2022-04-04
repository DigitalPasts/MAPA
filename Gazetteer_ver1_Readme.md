The “Mesopotamian Ancient Place-names Almanac” (MAPA) focuses on the southern
Mesopotamian city of Uruk ([modern
Warka](https://pleiades.stoa.org/places/912986)). It is one of the earliest
mega-cities in world history, with evidence of settlement as far back as the 4th
Millennium BCE. Uruk possesses some of the earliest attestations of the
cuneiform writing system, and boasts of being the royal seat of the legendary
king Gilgamesh. MAPA is a first step in integrating textual sources with remote
sensing data for reconstructing the social and physical geography of Mesopotamia
in the Age of Empires (first millennium BCE). The core of the project is a
gazetteer of place names in texts and surveys, both on the ground and via
satellite.

The dataset, presented here in CSV and JSON formats, is the presentation of a
gazetteer drawn from legal, economic and administrative texts from the
Neo-Babylonian and Achaemenid periods, issued in and around the Mesopotamian
city of Uruk. The listed toponyms were input manually from the books and
articles in the *bibliography*. The gazetteer follows the JSON-LD based [Linked
Places
format](https://github.com/LinkedPasts/linked-places/blob/master/tsv_0.3.md) of
the [World Historical Gazetteer](http://whgazetteer.org/). This readme contains
a key to the database’s fields, a few issues to be resolved in future
iterations, the next steps of the MAPA project and a bibliography.

### Field Title Key

`site_ID` A unique 4-digit durable numerical identifier, assigned to each unique
place.

`label` A four letter identifier, drawn from the document’s title. The letters
are drawn from the spelling of the *title*. The first letter indicates the type
of feature in question: *S* indicates a settlement, *W* indicates a hydrological
feature, *C* indicates a piece of urban infrastructure, *G* indicates an
agricultural floodplain, and *B* indicates a *Bāb* (gate, or lock connected to a
canal or river) or *Bīt* (estate, alternatively the settlement area of a tribal
group).

`title` The accepted normalised form of the ancient placename in contemporary
academic literature, i.e. the spelling used in reference materials. This is
taken as the “name” of the feature.

`variant_Akkadian` The syllabic Akkadian spelling of the toponym’s name, as
written in Babylonian texts. This accommodates further searches in the ancient
sources. There are often numerous spellings, which are listed here set off by
semi-colons.

`type` The type of feature under discussion. These are listed according to the
ontology of the Getty Art and Architecture Thesaurus or AAT
(getty.edu/research/tools/vocabularies/aat).

`sub_type` A more specific description of the feature, as much as is possible.
These are listed according to the hierarchies elucidated in AAT. Like “type,”
this section will expand and evolve as understanding of the region increases
through the project.

`title_source` The primary modern citation for the information in the document.
These are listed by citation key, referencing the BibTex and RIS files in this
release.

`t-s_pages` For ease of querying, the pages of the entry in the above source.

`Uruk_relation` A text field, with notes of the feature’s location in relation
to Uruk, as recorded in the title_source text.

`Uruk_probability` The probability of the location notes specifically, and the
information in the document generally, being correct. This is according to the
information in the title_source text.

`place_terms` This column records, for ease of use, the names of generic
geographic features included within the names of individual places. This
includes *Kār* (Quay), *Tīl* (Tell), among others.

`determinatives` This field records the determinatives from the ancient
Babylonian spelling of the placename, i.e. *d* (Dingir) preceding divine names.

`language` Records the linguistic background of the placename, using ISO
3-letter language codes. See links to SIL.org.

`language_prop` Records any uncertainty regarding the data in *langauge*.

`proper_nouns` Names of people, gods, and professions, primarily, contained
within the name of the place in question.

`p-n_type` Type of noun recorded in *proper_nouns*: Divine names, personal
names, professional names, or general appellatives.

`p-n_type_prop` Records any uncertainty regarding the data in *p-n_type*.

`variant_modern` The modern (usually Arabic) name given to the feature, if it is
known. It is recorded here both romanised and in the original Arabic.

`notes` A text field which contains information deemed important to the
gazetteer, but which did not neatly fit into the existing categories. This can
include variant spellings of the *title* among the various *title_sources*,
literature references, multiple iterations of an identical spelling, among
others. Context of the *LOC_details* is also recorded here.

`LOC_details` Records the way in which the title place connects to the places
recorded in the LOC fields. Each field is treated in turn, set off by
semicolons. These are intended to be direct and succinct; additional context,
such as directionality, is recorded in *Notes*.

`LOC-x` These fields, up to 5 at this point, are other toponyms in the gazetteer
which are connected by a text or texts to the feature in question. They are
recorded here by `site_ID`. Uncertainty is recorded in *LOC-1_probability*,
while other probabilities are recorded in *Notes*.

`ccode` The ISO two-letter country code of the location.

`CDLI` Where relevant, the CDLI [Cuneiform Digital Library
Initiative](https://cdli.ucla.edu/) provenance number.

`Pleiades` Where relevant, the Pleiades reference number
(<https://pleiades.stoa.org/>).

### Project Next Steps

We are continuing to enrich the gazetteer. Additional instances for each entry
are being added, according to the most up-to-date textual editions, as well as
unpublished references, and linking them to the gazetteer. We are also curating
site biographies for each of the ancient canals around Uruk. The biography
describes each settlement in both physical and social terms: what kinds of
social groups are active there, what are their main economic activities, and
what natural features, agricultural systems, and technologies are attested
there. Most interesting are the outgoing and incoming elements in each site
(documented e.g. in administrative texts or correspondence). As these
biographies are assembled, new information or connections that come to light
will likewise be added to subsequent iterations of the gazetteer.

### Acknowledgments

This research was supported by the the **Israel Science Foundation** (grant No.
457/19).

We would like to thank Ariel M. Bagg, Michael Jursa, Ran Zadok, Francis Joannès,
and the team at [Achemenet](http://www.achemenet.com/) for providing us with
text summaries and transliterations of texts from the relevant periods.

We would also like to extend our appreciation to our partners
at [Pelagios](https://pelagios.org/), especially Elton Barker, Gethin Rees, and
Simon Rainer, for their constant support and technical consultation.

Lastly, thanks to Karl Grossner from the World Historical Gazeetter, who
assisted us with conforming to the JSON-LD based Linked Places format.

### How to Cite

Gordin, Sh. and Clark, S. 2022. Mesopotamian Ancient Place-names Almanac 1.0
([https://github.com/DigitalPasts/MAPA](ttps://github.com/DigitalPasts/MAPA))

### Licensing

This repository is made freely available under the Attribution-ShareAlike 3.0
Unported (CC BY-SA 3.0) license. This means you are free to share and adapt the
repository, under the conditions that you cite the project appropriately, note
any changes you have made to the original repository, and if you are
redistributing the repository or a part thereof, you must release it under the
same license or a similar one.

For more information about the license,
see [here](https://creativecommons.org/licenses/by-sa/3.0/).

### Bibliography

Adams, Robert McC., and Hans J. Nissen. 1972. *The Uruk Countryside: The Natural
Setting of Urban Societies*. Chicago: University Press.

Bagg, Ariel M. 2020. *Die Orts- und Gewässernamen der neuassyrischen Zeit, Teil
3: Babylonien, Urartu und die östlichen Gebiete*. RGTC 7, Vol. 3. Weisbaden:
Reichert Verlag.

Cocquerillat, Denise. 1968. *Palmeraies et Cultures de l'Eanna d'Uruk
(559-520)*. Berlin: Mann Verlag.

Ermidoro, Stefania. 2016 “New Data on the Babylonian Hydraulic Landscape: An
Update to the Répertoire Géographique des Textes Cunéiformes Vol.
8.” *Kaskal* 13: 135–74.

Kleber, Kristen. 2008. *Tempel und Palast: die Beziehungen zwischen dem König
und dem Eanna-Tempel im spätbabylonischen Uruk*. Münster: Ugarit-Verlag.

Zadok, Ran. 1985. *Geographical Names According to New- and Late-Babylonian
Texts*. RGTC 8. Weisbaden: Reichert Verlag.

Zadok, Ran. 2020. “New Documents about Uruk, its Countryside and the Sealand”.
In: *Des polythéismes aux monothéismes. Mélanges d’assyriologie offerts à Marcel
Sigrist*. Ed. by Uri Gabbay and Jean Jacques Pérennès. Études Bibliques NS 82.
Leuven: Peeters, 491–534.
